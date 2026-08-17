[update-readmes]   Mode: rewrite — migrating to template structure...
# infra-dashboard

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/infra-dashboard) [![KDE Eco](https://img.shields.io/badge/KDE%20Eco-certified-brightgreen?logo=kde&logoColor=white&style=flat-square)](https://eco.kde.org/) [![Blue Angel](https://img.shields.io/badge/Blue%20Angel-DE--UZ%20215-0055a4?style=flat-square)](https://www.blauer-engel.de/en/certification/criteria) [![Energy](https://api.green-coding.io/v1/ci/badge/get?repo=Interested-Deving-1896%2Finfra-dashboard&branch=main&workflow=eco-audit.yml)](https://metrics.green-coding.io/ci-index.html)


<!-- AI:start:what-it-does -->
This project provides a unified dashboard for managing and monitoring infrastructure components. It consolidates tools like status pages, public dashboards, builder dashboards, rate mirrors, mirror list proxies, and a binary pastebin into a single monorepo. It is designed for infrastructure operators and developers who need centralized visibility and control over distributed systems.
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
The `infra-dashboard` repository is a monorepo containing multiple Rust-based services for managing and displaying infrastructure status. Each service operates independently but interacts through shared APIs and configurations. Key components include:

- `statuspage`: Provides a status monitoring interface for infrastructure components.
- `public-dashboard`: Serves a public-facing dashboard for infrastructure metrics.
- `builder-dashboard`: Manages build-related data and displays build statuses.
- `rate-mirrors`: Handles mirror rate-limiting and performance metrics.
- `mirrorlist-proxy`: Acts as a proxy for mirror selection and redirection.
- `bin-pastebin`: Implements a pastebin service for sharing logs or text snippets.

Services communicate via HTTP APIs and share configuration through `.env` files. Docker Compose is used for local orchestration. The directory structure is as follows:

```plaintext
.
├── README.md
├── bin-pastebin/
├── builder-dashboard/
├── config.example.env
├── docker-compose.yml
├── mirrorlist-proxy/
├── public-dashboard/
├── rate-mirrors/
└── statuspage/
```
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/infra-dashboard.git
cd infra-dashboard
```

## Usage

<!-- Add usage examples here. This section is yours — the AI will not modify it. -->

## Configuration


All org/distro-specific values live in `config/infra.toml`. See `config/infra.example.toml` for a full reference.

## CI

<!-- AI:start:ci -->
The repository uses GitHub Actions for continuous integration. The workflows are:

- **`build.yml`**: Builds and tests all Rust-based components. Runs on push and pull request events. No secrets required.
- **`docker-compose.yml`**: Validates the `docker-compose.yml` file and ensures all services can start. Runs on push events. No secrets required.
- **`lint.yml`**: Runs linters for Rust code and YAML files. Executes on push and pull request events. No secrets required.
- **`release.yml`**: Builds and publishes Docker images for all services to a container registry. Triggers on tagged commits. Requires the `DOCKER_USERNAME` and `DOCKER_PASSWORD` secrets.

All workflows are defined in the `.github/workflows` directory.
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/infra-dashboard`](https://github.com/Interested-Deving-1896/infra-dashboard) and mirrored through:

```
Interested-Deving-1896/infra-dashboard  ──►  OpenOS-Project-OSP/infra-dashboard  ──►  OpenOS-Project-Ecosystem-OOC/infra-dashboard
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
[@Interested-Deving-1896](https://github.com/Interested-Deving-1896): 28 commits

*Note: This repository is a mirror. Please refer to the upstream source for additional details.*
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream influences recorded._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

<!-- AI:start:accessibility -->
This repo uses automated accessibility auditing via `check-accessibility.yml`.

Checks include: CODEOWNERS ownership coverage, README screen-reader compatibility,
WCAG 2.1 AA HTML compliance, audio overview (espeak-ng), and Braille output (liblouis).




Run the [Check Accessibility](https://github.com/Interested-Deving-1896/infra-dashboard/actions/workflows/check-accessibility.yml)
workflow to generate the first report and accessibility artifacts.
See [DOCS/accessibility.md](https://github.com/Interested-Deving-1896/infra-dashboard/blob/main/DOCS/accessibility.md) for the full reference.
<!-- AI:end:accessibility -->

## License

<!-- AI:start:license -->
<!-- License not detected — add a LICENSE file to this repo. -->
<!-- AI:end:license -->
