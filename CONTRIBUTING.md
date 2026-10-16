# Contributing to ORYNTO

ORYNTO is in a founder-led foundation phase. Contributions should strengthen the product architecture rather than maximize surface area.

## Before opening a change

Read:

- `AGENTS.md`
- `docs/foundation/PRODUCT_THESIS.md`
- `docs/foundation/PRODUCT_PRINCIPLES.md`
- relevant entries in `docs/product/DECISIONS.md`
- relevant requirements in `docs/product/REQUIREMENTS.md`

If a product/architecture decision is open, do not code around it as though it were settled.

## Branches and commits

Use focused branches and conventional commit prefixes where practical:

- `feat:` new behavior
- `fix:` defect correction
- `docs:` documentation only
- `refactor:` structural change without intended behavior change
- `test:` test/evaluation work
- `chore:` tooling/repository maintenance

Avoid giant mixed-purpose PRs.

## Pull request contract

Every significant PR should state:

1. **Why** — user/product/architecture problem.
2. **Traceability** — requirement and decision IDs.
3. **What changed** — concise implementation summary.
4. **Data/API impact** — schema, migrations, contracts, compatibility.
5. **Trust impact** — auth, tenancy, privacy, secrets, external messages, financial mutations.
6. **Evidence** — tests, evals, screenshots, performance evidence as applicable.
7. **Known limitations** — mocks, deferred paths, operational assumptions.
8. **Rollback/migration** — when state or deployment changes.

## Testing expectations

Changes should use the appropriate combination of:

- unit tests for deterministic domain logic;
- contract tests for tools/adapters;
- integration tests for database/provider boundaries;
- tenant-isolation and authorization tests;
- end-to-end tests for important user loops;
- AI evaluation fixtures for interpretation/planning behavior;
- regression tests for every confirmed defect where reasonable.

LLM demonstrations are not substitutes for repeatable evaluation.

## Security

Never commit:

- API keys or credentials;
- `.env` files containing secrets;
- production/customer data;
- private message exports;
- payment/bank credentials;
- model-provider keys;
- personal access tokens.

Use synthetic or explicitly authorized test data.

## Dependency policy

Before introducing a material dependency, consider:

- license compatibility;
- maintenance/activity;
- security posture;
- whether it crosses BigCapital/open-core boundaries;
- whether a smaller standard solution is sufficient.

## Documentation

Documentation is part of the system contract. If code changes behavior, data ownership, architecture, or accepted user flow, update the relevant docs in the same PR.
