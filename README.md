# Ross Malcolm — Portfolio

Live at [rossmalcolm.ca](https://rossmalcolm.ca)

[![CI/CD](https://github.com/RossMalcolm/rossmalcolm-portfolio/actions/workflows/ci-cd.yml/badge.svg)](https://github.com/RossMalcolm/rossmalcolm-portfolio/actions/workflows/ci-cd.yml)

A single-page portfolio site summarizing my resume, deployed via GitHub Actions to GitHub Pages on a custom domain.

## Pipeline

Every push and pull request runs:

- **Build** — assembles the static site into `dist/`
- **HTML validation** ([html-validate](https://html-validate.org/)) — catches malformed or invalid markup
- **Broken link check** ([lychee](https://github.com/lycheeverse/lychee)) — verifies every link in the page actually resolves
- **Lighthouse CI** ([treosh/lighthouse-ci-action](https://github.com/treosh/lighthouse-ci-action)) — audits performance, accessibility, best practices, and SEO

`main` is protected: changes go through a pull request, and all checks above must pass before a merge is allowed. Merging to `main` then triggers an automatic deploy to GitHub Pages.

## Stack

Static HTML/CSS/JS, no build tooling or framework — deployed on GitHub Pages behind a custom domain (`rossmalcolm.ca`) with GitHub-issued TLS. Contact form submissions are handled by [Web3Forms](https://web3forms.com/); the GitHub activity graph is pulled live from the public GitHub contributions API.
