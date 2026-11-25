# FF E-Commerce documentation

Source of the documentation site for [ff-ecommerce](https://github.com/ffetih/ff-ecommerce),
published at https://ffetih.github.io/ff-ecommerce-docs.

Built with [Antora](https://antora.org); pages are AsciiDoc, diagrams are PlantUML rendered by
[Kroki](https://kroki.io).

## Layout

```
antora-playbook.yml          site: sources, UI, extensions
supplemental-ui/             header and footer
docs/antora.yml              the ff-ecommerce component
docs/modules/
  ROOT/                      overview, roadmap
  architecture/              architect: overview, saga, failure stories, security, ADRs
  business/                  business analyst: lifecycle, domain rules, glossary
  developer/                 developer: local run, codebase, API, UI integration, recipes, try-it
  operations/                operations: metrics, dead-letter runbook, configuration, Keycloak
```

## Build locally

Requires Node.js 22.

```bash
npm ci
npx antora antora-playbook.yml        # the site goes to build/site
xdg-open build/site/index.html        # or open it in the browser from Windows
```

Antora reads the content from this folder as a git repository (the working tree, so uncommitted pages
are included). Pushing to `main` publishes the site through GitHub Actions.
