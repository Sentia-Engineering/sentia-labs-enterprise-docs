# Sentia Labs Enterprise — Documentation

Customer-facing documentation for the Sentia Labs Enterprise platform, built with [Mintlify](https://mintlify.com).

Production: [docs.sentialabs.ai](https://docs.sentialabs.ai)

## Structure

```
.
├── docs.json                 # Mintlify config — navigation, branding, contextual menus
├── favicon.svg
├── logo/                     # Light + dark logos (white-fill variant for dark mode)
├── index.mdx                 # Welcome page
├── quickstart.mdx            # 10-minute first-simulation guide
├── concepts/                 # Core concepts — primitives, lifecycle, glossary
├── onboarding/               # Week-one checklist + per-step guides
├── simulations/              # Wizard, inputs, modes, convergence, results, triggers, best-practices
├── populations/              # Build, interview grounding, validation
├── decisions/                # Log + lifecycle
├── integrations/             # Per-category guides (15 integrations)
├── calibration/              # Flywheel, ship detection, accuracy, drift
├── admin/                    # Workspaces, members/roles, SSO/SCIM, billing, audit
├── security/                 # SOC 2 posture, data handling, sub-processors, GDPR, LLM safety
├── reference/                # Keyboard shortcuts, limits, release notes, support
└── api-reference/            # REST API reference + per-endpoint pages + OpenAPI spec
```

## Local preview

```bash
npm i -g mint
mint dev
```

Opens at `http://localhost:3000`.

## Source of truth

This repo is the **customer-facing** documentation. The product source-of-truth lives in the [`sentia-labs-enterprise`](../sentia-labs-enterprise) repo at `docs/`:

- `docs/api-reference.yaml` — canonical OpenAPI spec (mirrored to `api-reference/openapi.yaml` here)
- `docs/integration-guides.md` — internal integration architecture
- `docs/simulation-best-practices.md` — internal best-practices reference
- `docs/incident-playbook.md` — internal SRE runbooks (NOT for customer docs)
- `docs/render-production.md` — internal deployment notes

When something material changes in the product, update the relevant page here. The OpenAPI spec is hand-mirrored to keep API reference in sync.

## Publishing

The Mintlify GitHub App deploys this repo automatically on push to `main`. See the [Mintlify dashboard](https://dashboard.mintlify.com).

## Conventions

- Customer-facing language. Avoid internal jargon. Avoid links to `apps/...` or `packages/...` paths.
- One `<h1>` per page (via the frontmatter `title`).
- Always include a "Next" card group at the bottom for navigability.
- Code blocks: use real-shaped examples, not placeholders like `<your-api-key>`. Always show a curl example for API endpoints.
- Tables for structured comparisons, not bullet lists.
- Keep page-length under ~800 lines. If longer, split.
