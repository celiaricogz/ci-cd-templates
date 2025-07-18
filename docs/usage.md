# 📖 Usage Guide – CI/CD Templates

This guide explains how to integrate the templates from this repository into your own projects, both for **GitLab CI** and **GitHub Actions**.

---

## 🔹 Using in GitLab CI

1. Add the template to your `.gitlab-ci.yml`:

```yaml
include:
  - project: 'celiaricogz/ci-cd-templates'
    ref: main
    file: '/gitlab/node.yml'
```

2. Optionally include common jobs:

```yaml
include:
  - project: 'celiaricogz/ci-cd-templates'
    ref: main
    file: '/gitlab/common.yml'
```

3. Commit and push. Your project will now run the predefined jobs.

---

## 🔹 Using in GitHub Actions

1. Create a workflow in `.github/workflows/ci.yml`:

```yaml
name: My Node CI

on:
  push:
    branches: [ main ]

jobs:
  node-ci:
    uses: celiaricogz/ci-cd-templates/.github/workflows/node.yml@main

  common:
    uses: celiaricogz/ci-cd-templates/.github/workflows/common.yml@main
```

2. Push your code and watch GitHub Actions run the jobs.

---

## 🔧 Variables & Customization

- These templates assume a default setup (npm, pip, Maven).  
- You can extend them by:
  - Adding extra jobs via `include:` (GitLab) or `uses:` (GitHub).
  - Modifying the common jobs in `common.yml` (for lint, notifications, etc.).
  - Passing environment variables like `PACKAGE_VERSION` or `NODE_ENV`.

---

## 🧩 Examples

Check the `examples/` folder for ready-to-use `.gitlab-ci.yml` and `.github/workflows/ci.yml` files.

- `examples/gitlab-node/.gitlab-ci.yml`
- `examples/github-node/ci.yml`
- Python and Java examples also available.

---

## 🛠 Requirements

- **GitLab CI** or **GitHub Actions** enabled on your repository.
- Access to this repo (public include).
- Runner or GitHub-hosted runner with `bash`, `git`, `zip`, `node`, `python`, or `maven`.

---

For advanced configurations (e.g., deploying, Docker builds, or parallelization), you can fork this repository and extend the templates.