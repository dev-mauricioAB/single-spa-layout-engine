# single-spa-layout-engine

This repository showcases a microfrontend architecture built with single-spa and the Layout Engine, enabling multiple independent applications to be orchestrated within a unified layout.
The goal is to provide a scalable, modular, and maintainable structure where each micro-application can be developed, versioned, and deployed independently — without losing visual consistency or seamless integration across the system.

## 🚀 Table of Contents

* [What is this project?](#what-is-this-project)
* [Key Features](#key-features)
* [Why use this approach?](#why-use-this-approach)
* [Project Structure](#project-structure)
* [Getting Started](#getting-started)
* [Usage](#usage)
* [Configuration & Conventions](#configuration--conventions)
* [Development Workflow](#development-workflow)
* [Building & Deployment](#building--deployment)
* [Contributing](#contributing)
* [License](#license)
* [Acknowledgements](#acknowledgements)


## What is this project?

This repository provides a root **common‐workspace** and multiple applications built using the micro-frontend framework single‑spa, alongside a **Layout Engine** approach to orchestrate multiple sub-apps into a cohesive user interface.
It allows each micro‐frontend to coexist independently (in terms of build, deploy, version) while sharing layout, nav, and shell infrastructure.


## Key Features

* Micro-frontend architecture powered by single-spa (multiple “apps” mounted in same page)
* A shared layout engine (shell) that manages navigation, header/footer, and container(s) for child apps
* Common workspace for shared code, libraries or utilities
* Modular structure: each app can be built, deployed, versioned separately
* Technologies in the repo include JavaScript, TypeScript, Vue (per language breakdown) ([GitHub][1])


## Why use this approach?

* **Scalability**: As your product grows, you can split functionality into separate micro‐apps without huge monoliths
* **Team independence**: Different teams can work on distinct apps, deploy individually
* **Shared layout & cohesion**: Even with separate apps, the user experience remains consistent via the layout engine
* **Tech heterogeneity**: You could have different frameworks for each app, while the shell handles integration


## Project Structure

Here’s an overview of how the repository is organized:

```
/common-workspace        ← shared libraries, utilities
/app-header             ← layout shell header app (example)
/app-body               ← main “body” or container app
/app-footer             ← layout shell footer app
/app-modulo-x           ← one of the micro-frontend apps
...
```

You’ll find folders like `z-body`, `z-header`, `z-modulo-x` in the root. ([GitHub][1])
Each folder corresponds to an independent module/app, plus the common workspace.


## Getting Started

Here’s how to get the project up and running locally.

1. Clone the repo:

   ```bash
   git clone https://github.com/dev-mauricioAB/single‐spa‐layout‐engine.git
   cd single‐spa‐layout‐engine
   ```

2. Install dependencies:

   ```bash
   # depending on workspace manager (yarn / npm / pnpm)
   yarn install
   # or
   npm install
   ```

3. Start in development mode:

   ```bash
   yarn start
   # or
   npm run start
   ```

   This should launch the layout shell and mount each micro‐app.

4. Build for production:

   ```bash
   yarn build
   # or
   npm run build
   ```

   The bundled output for each app will be generated, ready for deployment.


## Usage

* Use the layout shell to define where each micro‐frontend mounts (e.g., via `<div id="app-header"></div>`, `<div id="app-body"></div>`)
* In each micro-frontend, register with single-spa (e.g., `registerApplication('module-x', …)`)
* Navigation changes (e.g., route changes) trigger mounting/unmounting of apps
* Shared modules live in the `common-workspace` and can be imported by any micro-app


## Configuration & Conventions

* **Naming convention**: Folders prefixed with `z-` denote micro-apps/modules
* **Routing**: Please ensure each micro‐frontend uses the agreed routing schema so the shell knows when to mount/unmount them
* **Shared library versioning**: When changing shared code in `common-workspace`, bump version and publish (or link) accordingly
* **Deployment**: Each micro‐frontend can be deployed to its own domain or CDN; the shell loads them via import maps or dynamic script tags


## Development Workflow

* Branch from `main` for each new feature or micro‐frontend
* Commit clearly: e.g., `feat(z-modulo-x): add new widget`
* Write meaningful README inside each micro-app folder if needed
* Run unit / integration tests in each app
* Ensure linting / formatting rules are adhered to across the workspace


## Building & Deployment

* Use CI (e.g., GitHub Actions) to build each micro‐app when changes are pushed
* Deploy built assets to static hosting / CDN
* Update the shell import map (if used) to point to latest versions of each micro‐app
* Versioning strategy: semantic versioning for each micro‐app + shared workspace


## Contributing

Thanks for your interest in contributing!
Here’s how you can help:

* Submit issues for bugs or feature requests
* Fork the repo and make changes, then issue a pull request (PR)
* Ensure your changes include tests (where appropriate) and documentation updates
* Follow the existing code style and architecture conventions


## License

This project is (choose license) – e.g., MIT License.
*Add the license file to the repository if not already present.*


## Acknowledgements

Thanks to the authors and community behind single‐spa and micro-frontend architectures for ideas and best practices.


