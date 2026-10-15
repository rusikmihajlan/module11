# Module 11 — Continuous Integration

This repository contains the UI and API automated tests and a local Jenkins setup. Jenkins provides two separate Pipeline jobs; each checks out this repository, installs the locked Node.js dependencies, and runs its test suite every two hours.

## Run the tests

Use Node.js 24 and npm:

```sh
npm ci
npm run lint
npm run test:api
npm run test:ui
```

The UI suite uses headless Chromium. Configure `CHROME_BIN` if Chromium is not available at the standard path. If the API is reached through a network proxy, Node.js 24 can use the standard proxy environment variables with `NODE_USE_ENV_PROXY=1`.

## Run Jenkins locally

See [`jenkins/README.md`](jenkins/README.md) for Jenkins LTS installation, automatic creation of the UI/API jobs, their two-hour schedule, and a mentor demonstration walkthrough.

## Repository layout

- `src/` contains the shared core and application-specific page objects and flows.
- `tests/api/` contains the API lifecycle checks.
- `tests/specs/` contains the WebdriverIO UI scenarios.
- `Jenkinsfile.ui` and `Jenkinsfile.api` define the scheduled Jenkins pipelines.
- `.github/workflows/ci.yml` runs the existing Prettier/ESLint gate before the test jobs.
