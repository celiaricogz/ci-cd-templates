# 🚀 CI/CD Templates – Ready-to-Use Pipelines for GitLab & GitHub

**CI/CD Templates** is a collection of **production-ready pipelines** for the most common stacks (Node.js, Python, Java), compatible with both **GitLab CI** and **GitHub Actions**.  

Stop wasting time writing boilerplate `.yml` files. These templates are **optimized, reusable, and easy to integrate**, so you can focus on building features instead of pipelines.

---

## ✨ Features

- **Multi-platform**: Works with both **GitLab CI** (`include:`) and **GitHub Actions** (`uses:`).
- **Three languages supported** (and growing):  
  - Node.js (npm/yarn projects)  
  - Python (pytest & flake8)  
  - Java (Maven)
- **Optimized** with caching for faster builds.
- **Modular design**: Common jobs (lint, dummy test, notifications) can be reused across stacks.
- **Plug-and-play**: Just include the template – no copy-paste needed.
- **Examples included** for quick testing.

---

## 📂 Repository Structure

```
.
├── gitlab/                  # GitLab CI templates
│   ├── node.yml
│   ├── python.yml
│   ├── java.yml
│   └── common.yml
├── github/                  # GitHub Actions workflows
│   ├── node.yml
│   ├── python.yml
│   ├── java.yml
│   └── common.yml
├── examples/                # Working examples for both platforms
│   ├── gitlab/
│   │   ├── gitlab-node/.gitlab-ci.yml
│   │   ├── gitlab-python/.gitlab-ci.yml
│   │   └── gitlab-java/.gitlab-ci.yml
│   └──github/
│       ├── github-node/ci.yml
│       ├── github-python/ci.yml
│       └── github-java/ci.yml
├── docs/
│   └── usage.md
├── README.sp.md
├── README.md
└── LICENSE
```

---

## 🚀 Quick Start

### **For GitLab CI**

Include the Node.js template in your `.gitlab-ci.yml`:

```yaml
include:
  - project: 'celiaricogz/ci-cd-templates'
    ref: main
    file: '/gitlab/node.yml'

# Optional: add common jobs (lint, dummy test, notifications)
include:
  - project: 'celiaricogz/ci-cd-templates'
    ref: main
    file: '/gitlab/common.yml'
```

### **For GitHub Actions**

Use the Node.js workflow as a reusable job in your `.github/workflows/ci.yml`:

```yaml
name: My Node.js CI

on:
  push:
    branches: [ main ]

jobs:
  node-ci:
    uses: celiaricogz/ci-cd-templates/.github/workflows/node.yml@main

  common-jobs:
    uses: celiaricogz/ci-cd-templates/.github/workflows/common.yml@main
```

*Examples for Python and Java are in the `examples/` folder.*

---

## 🛠 Supported Stacks

- **Node.js**: `npm ci`, linting, testing, build, and artifact upload.
- **Python**: `pip` with cache, flake8 linting, pytest with test reports.
- **Java (Maven)**: Cached `.m2/`, build, and test stages with JUnit reports.

---

## 🧩 Why Use These Templates?

- **Save time** – no need to write pipelines from scratch.
- **Faster builds** – caching and optimized job definitions.
- **Standardization** – all your projects follow the same structure.
- **Flexibility** – extendable via `common.yml`.

Whether you're a **startup** needing fast CI/CD setup or a **team without dedicated DevOps**, this collection helps you deliver **faster and more reliably**.

---

## 📸 Screenshots & Demos

Coming soon: screenshots of pipelines in action and links to demo repos.

---

## 📄 License

Licensed under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.

---

## 👩‍💻 Author

**Celia Rico Gutiérrez**  
DevOps Engineer — CI/CD automation, modularization, reproducible packaging  
🔗 [LinkedIn](https://www.linkedin.com/in/celiaricogutierrez)  
🔗 [Malt](https://www.malt.es/profile/celiaricogutierrez)
🔗 [UpWork](https://www.upwork.com/freelancers/~01898dfb872ff48b7a?mp_source=share)

---

📅 _Last updated: July 2025_