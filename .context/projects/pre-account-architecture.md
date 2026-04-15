# Architecture: Pre-Account Creation Onboarding

> Source repos: `sqsp/acuity-pre-account-creation` (microfrontend), `sqsp/scheduling-acuity` (PHP monolith)  
> This flow is the **predecessor** to the post-trial wizard. It proved immersive onboarding works (+4.46pp Trial to Updating CSP, +18% directional Assign to Sub) but hurt trial volume due to pre-trial placement. The post-trial wizard reuses many of these patterns.

---

## Summary

- Microfrontend injected into a server-rendered PHP shell (Smarty template)
- State values bootstrapped via `window.PreAccountCreation` global
- User choices encoded as query parameters on `GET /signup.php` handoff
- PHP signup flow reads choices from session and applies them post-account-creation
- Independently deployable app in its own repo, built with [febs](https://github.com/sqsp/febs)
  - Primary challenge: configuring Drone CI build

---

## Request Flow

```
Browser
  │
  ▼
GET /get-started
  │
  ▼
PHP Monolith (Slim 3)
  └── PreAccountCreationController::renderInterstitial()
        │
        ├── Fetches: CSP variant (Statsig experiment)
        ├── Fetches: presetStyles (PHP fixtures)
        └── Renders: Smarty template (index.tpl)
              ├── <div id="preaccount-container" />   ← React mount point
              ├── window.PreAccountCreation = { variant, presetStyles }
              ├── <script> adminLivePreview.{locale}.js  (Pylon SAS)
              ├── <script> errorReporter.{locale}.js     (SAS)
              └── <script> main.{locale}.js              (SAS)

React App Hydrates
  ├── Redux store: reads window.PreAccountCreation
  ├── CSPStyleEditorStep: 8 preset buttons
  ├── PylonContainer: calls window.AdminLivePreview.renderLivePreview()
  │     └── Renders live scheduling page preview (iframe-like)
  ├── On submit → GET /signup.php?themePreset=N&industry=X&...
  │
  └── API calls during session:
        ├── GET /api/industry-fixture?industry=X   (PHP monolith)
        ├── POST /event                            (PHP monolith — internal tracking)
        └── GET insights.squarespace.com/...       (external DSML — analytics)

POST signup.php (action=signup)
  └── PreAccountCreationService::seedUserAppointmentTypes()
      └── Applies chosen preset → user.usedPresetAndHasNotCustomized = true
```

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Microfrontend | React 19 + TypeScript |
| State | Redux Toolkit (slices: app, survey, experiments, fixtures) |
| Build | FEBS (Squarespace) + Webpack 5, pnpm |
| Styling | Less + Rosetta design system |
| i18n | `@sqs/i18n-react` + YAML translation files (10 locales) |
| Monolith | PHP, Slim 3, Smarty templates |
| Experiments | Statsig (`PRE_ACCOUNT_CREATION_V2` flag) |
| Tracking | POST `/event` (internal) + `insights.squarespace.com` (DSML) |

---

## Key Implementation Details

### Window Global (PHP → React handoff)
```js
window.PreAccountCreation = {
  cspMarketingVariant: "generic" | "focused",  // Statsig experiment variant
  presetStyles: { "1": {...}, "2": {...}, ... "8": {...} }  // 8 theme presets
}
```

### Step Machine
Steps defined as a `STEP_ORDER` constant array. Currently only `"csp-marketing"` is active. A `SelectVerticalStep` (industry picker) exists in code but is disabled — this maps closely to Screen 1 (business type) of the post-trial wizard design.

### Signup Handoff
```
/signup.php?action=form&freeTrial=1&lite=1&themePreset=1&industry=X&click_location=...
```
PHP reads `$_SESSION['pac_theme_preset']` and `$_SESSION['user_industry']` post-creation to seed:
- `PreAccountCreationService::seedUserCSPStyles()` — applies theme colors + font
- `PreAccountCreationService::seedUserAppointmentTypes()` — creates sample appointment types
- Sets `user.usedPresetAndHasNotCustomized = true` on the user record

### Pylon Live Preview
`window.AdminLivePreview.renderLivePreview(selector, props)` — renders a live scheduling page preview. Props include business fixture (name, tagline, sample appointments) + selected theme. The business fixture is loaded from `/api/industry-fixture?industry={categoryId}` when an industry is selected.

---

## Relevance to Post-Trial Wizard

| Pre-Account (existing) | Post-Trial Wizard (to build) |
|------------------------|------------------------------|
| Triggers before signup at `/get-started` | Triggers after trial creation |
| Gates on Statsig flag + no session | Gates on new account + no prior setup |
| Seeds new account with theme + appt types | Writes to existing account |
| `SelectVerticalStep` disabled (industry picker) | Screen 1: business type (same concept) |
| Industry fixture API for Pylon preview | AI suggestions on Screen 3 (same data source) |
| `user.usedPresetAndHasNotCustomized = true` | Equivalent flag needed post-wizard |
| Single step: theme picker | 6-step wizard (business type → services → hours → live page) |
| Separate microfrontend repo | Likely same pattern: new repo or new route |
