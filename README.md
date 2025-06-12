# 🚀 WackyFlip-CI

Continuous Integration & Deployment
This repository houses all automation workflows, CI/CD pipelines, GitHub Actions, and deployment scripts powering [Wacky Flip](https://wackyflip.com)’s development and release lifecycle.

---

## 📦 Overview

`WackyFlip-CI` is the automation backbone of the entire Wacky Flip ecosystem. It ensures every commit, pull request, and release follows a reliable, secure, and testable delivery process across multiple environments (dev, staging, production).

From unit testing and linting to building Docker images and deploying to the cloud—this repo manages it all.

---

## 🧰 Features

* ✅ **Automated Testing**
  Runs unit, integration, and end-to-end tests on push and PRs using GitHub Actions and custom runners.

* 🧪 **Linting & Static Analysis**
  Ensures code quality across all major [Wacky Flip](https://wackyflip.com) repos with ESLint, Prettier, and type checks.

* 🛠️ **Build Pipelines**
  Automates frontend builds, mobile packaging, and backend service containers.

* 🚢 **Staging & Production Deployment**
  GitHub Actions workflows deploy to respective environments using secrets and infrastructure configs.

* 📦 **Artifact Management**
  Stores and versions build outputs, Docker images, and game asset bundles.

* 🧼 **Preview Deployments**
  Automatically creates preview environments for PRs (Netlify for Web, Firebase for Mobile, etc.)

* 🔐 **Secrets & Environment Isolation**
  Uses GitHub Secrets and environment-specific configs to securely manage tokens, keys, and deployment targets.

---

## 🗂️ Directory Structure

```
WackyFlip-CI/
├── .github/
│   └── workflows/
│       ├── web-build.yml             # CI for WackyFlip-Web
│       ├── api-test-deploy.yml       # Tests + deploy for WackyFlip-API
│       ├── mobile-ci.yml             # Build pipeline for WackyFlip-Mobile
│       ├── core-unit-tests.yml       # Test logic for WackyFlip-Core
│       └── docs-deploy.yml           # Auto-deploy docs site from WackyFlip-Docs
├── scripts/
│   ├── deploy.sh                     # Bash deployment script
│   ├── build-core-assets.js         # Script to compile core game assets
│   └── purge-cache.js               # Utility to clear CDN or API caches
├── environments/
│   ├── staging.env
│   └── production.env
├── README.md
└── LICENSE
```

---

## 🔄 Workflow Examples

### 🔹 `web-build.yml`

* Runs on push to `main`
* Installs dependencies → runs lint/tests → builds frontend → deploys to Netlify

### 🔹 `api-test-deploy.yml`

* Triggers on merged PRs to `main` of `WackyFlip-API`
* Executes unit tests → builds Docker container → deploys to staging (via SSH/Cloud Build)

### 🔹 `core-unit-tests.yml`

* Executes tests from `WackyFlip-Core` on every PR
* Reports coverage to Codecov

### 🔹 `mobile-ci.yml`

* Builds Android/iOS packages using EAS Build or custom Expo pipeline

---

## 🧪 Supported Projects

The following repos are integrated with `WackyFlip-CI`:

* [`WackyFlip-Web`](https://github.com/wackyflipgame/WackyFlip-Web)
* [`WackyFlip-Mobile`](https://github.com/wackyflipgame/WackyFlip-Mobile)
* [`WackyFlip-API`](https://github.com/wackyflipgame/WackyFlip-API)
* [`WackyFlip-Core`](https://github.com/wackyflipgame/WackyFlip-Core)
* [`WackyFlip-Docs`](https://github.com/wackyflipgame/WackyFlip-Docs)

---

## 🔐 Security & Secrets

All deployment credentials, API tokens, and environment variables are securely stored using **GitHub Environments** and **GitHub Secrets**.

* Never commit secrets to the repo
* Rotate credentials regularly
* Use `.env.template` to share variable structure without leaking content

---

## 📖 Getting Started

If you’re modifying or adding a CI workflow:

1. Create or modify a workflow YAML in `.github/workflows/`
2. Commit and push to a feature branch
3. Monitor workflow results via the **Actions** tab
4. Merge to `main` after tests pass

---

## 👷 Contributing

We welcome CI/CD improvements, performance optimizations, and support for new environments!

* Keep scripts modular and reusable
* Follow existing naming conventions
* Ensure workflow readability and proper job isolation

---

## 🧭 Roadmap

* [ ] Add Canary/Blue-Green deployment support
* [ ] Integrate Slack & Discord build notifications
* [ ] Add rollback logic and version tagging
* [ ] Implement UI Test Bots for visual regression

---

## 🧾 License

MIT License © Wacky Flip Studios
