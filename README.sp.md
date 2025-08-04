# Plantillas CI/CD – Pipelines Listos para Usar en GitLab & GitHub

**Plantillas CI/CD** es una colección de **pipelines listos para producción** para los stacks más comunes (Node.js, Python, Java), compatibles tanto con **GitLab CI** como con **GitHub Actions**.

Deja de perder tiempo escribiendo archivos `.yml` de boilerplate. Estas plantillas son **optimizadas, reutilizables y fáciles de integrar**, para que puedas centrarte en desarrollar funcionalidades en vez de pipelines.

---

## Características

- **Multiplataforma**: Funciona con **GitLab CI** (`include:`) y **GitHub Actions** (`uses:`).
- **Tres lenguajes soportados** (y creciendo):  
    - Node.js (proyectos npm/yarn)  
    - Python (pytest & flake8)  
    - Java (Maven)
- **Optimizado** con caché para builds más rápidos.
- **Diseño modular**: Trabajos comunes (lint, test dummy, notificaciones) reutilizables entre stacks.
- **Plug-and-play**: Solo incluye la plantilla – sin copiar y pegar.
- **Ejemplos incluidos** para pruebas rápidas.

---

## Estructura del repositorio

```
.
├── gitlab/                  # Plantillas GitLab CI
│   ├── node.yml
│   ├── python.yml
│   ├── java.yml
│   └── common.yml
├── github/                  # Workflows GitHub Actions
│   ├── node.yml
│   ├── python.yml
│   ├── java.yml
│   └── common.yml
├── examples/                # Ejemplos funcionales para ambas plataformas
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

## Inicio Rápido

### **Para GitLab CI**

Incluye la plantilla de Node.js en tu `.gitlab-ci.yml`:

```yaml
include:
    - project: 'celiaricogz/ci-cd-templates'
        ref: main
        file: '/gitlab/node.yml'

# Opcional: añade trabajos comunes (lint, test dummy, notificaciones)
include:
    - project: 'celiaricogz/ci-cd-templates'
        ref: main
        file: '/gitlab/common.yml'
```

### **Para GitHub Actions**

Usa el workflow de Node.js como trabajo reutilizable en tu `.github/workflows/ci.yml`:

```yaml
name: Mi CI Node.js

on:
    push:
        branches: [ main ]

jobs:
    node-ci:
        uses: celiaricogz/ci-cd-templates/.github/workflows/node.yml@main

    common-jobs:
        uses: celiaricogz/ci-cd-templates/.github/workflows/common.yml@main
```

*Ejemplos para Python y Java están en la carpeta `examples/`.*

---

## Stacks Soportados

- **Node.js**: `npm ci`, linting, testing, build y subida de artefactos.
- **Python**: `pip` con caché, linting con flake8, pytest con reportes de tests.
- **Java (Maven)**: Caché de `.m2/`, etapas de build y test con reportes JUnit.

---

## ¿Por qué usar estas plantillas?

- **Ahorra tiempo** – no necesitas escribir pipelines desde cero.
- **Builds más rápidos** – caché y trabajos optimizados.
- **Estandarización** – todos tus proyectos siguen la misma estructura.
- **Flexibilidad** – ampliable vía `common.yml`.

Tanto si eres una **startup** que necesita CI/CD rápido como un **equipo sin DevOps dedicado**, esta colección te ayuda a entregar **más rápido y de forma fiable**.

---

## Capturas & Demos

Próximamente: capturas de pipelines en acción y enlaces a repos de demo.

---

## Licencia

Licenciado bajo la **Licencia MIT**.  
Consulta el archivo [LICENSE](LICENSE) para más detalles.

---

## Autora

**Celia Rico Gutiérrez**  
Ingeniera DevOps — Automatización CI/CD, modularización, empaquetado reproducible  

[<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" alt="LinkedIn Logo" width="35" style="vertical-align:middle; margin-right:8px;"/>](https://www.linkedin.com/in/celiaricogutierrez)
[<img src="https://play-lh.googleusercontent.com/1r1DdWXDT9K7D2yBwPkVyXQFEjLL0cMrR6SxBvcNXXwpi8aZN0ZKS61CVdtvK6pmpg" alt="Malt Logo" width="35" style="vertical-align:middle; margin-right:8px;"/>](https://www.malt.es/profile/celiaricogutierrez)
[<img src="https://images.icon-icons.com/3781/PNG/512/upwork_icon_231982.png" alt="Malt Logo" width="35" style="vertical-align:middle;"/>](https://www.upwork.com/freelancers/~01898dfb872ff48b7a?mp_source=share)

---

_\~Última actualización: julio 2025\~_
