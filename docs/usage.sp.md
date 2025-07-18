# 📖 Guía de Uso – Plantillas CI/CD

Esta guía explica cómo integrar las plantillas de este repositorio en tus propios proyectos, tanto para **GitLab CI** como para **GitHub Actions**.

---

## 🔹 Uso en GitLab CI

1. Añade la plantilla a tu archivo `.gitlab-ci.yml`:

```yaml
include:
    - project: 'celiaricogz/ci-cd-templates'
        ref: main
        file: '/gitlab/node.yml'
```

2. Opcionalmente incluye trabajos comunes:

```yaml
include:
    - project: 'celiaricogz/ci-cd-templates'
        ref: main
        file: '/gitlab/common.yml'
```

3. Haz commit y push. Tu proyecto ahora ejecutará los trabajos predefinidos.

---

## 🔹 Uso en GitHub Actions

1. Crea un flujo de trabajo en `.github/workflows/ci.yml`:

```yaml
name: Mi Node CI

on:
    push:
        branches: [ main ]

jobs:
    node-ci:
        uses: celiaricogz/ci-cd-templates/.github/workflows/node.yml@main

    common:
        uses: celiaricogz/ci-cd-templates/.github/workflows/common.yml@main
```

2. Haz push de tu código y observa cómo GitHub Actions ejecuta los trabajos.

---

## 🔧 Variables y Personalización

- Estas plantillas asumen una configuración por defecto (npm, pip, Maven).  
- Puedes extenderlas:
    - Añadiendo trabajos extra mediante `include:` (GitLab) o `uses:` (GitHub).
    - Modificando los trabajos comunes en `common.yml` (para lint, notificaciones, etc.).
    - Pasando variables de entorno como `PACKAGE_VERSION` o `NODE_ENV`.

---

## 🧩 Ejemplos

Consulta la carpeta `examples/` para archivos listos para usar `.gitlab-ci.yml` y `.github/workflows/ci.yml`.

- `examples/gitlab-node/.gitlab-ci.yml`
- `examples/github-node/ci.yml`
- También disponibles ejemplos para Python y Java.

---

## 🛠 Requisitos

- **GitLab CI** o **GitHub Actions** habilitados en tu repositorio.
- Acceso a este repositorio (include público).
- Runner o runner de GitHub con `bash`, `git`, `zip`, `node`, `python` o `maven`.

---

Para configuraciones avanzadas (por ejemplo, despliegue, builds con Docker o paralelización), puedes bifurcar este repositorio y extender las plantillas.