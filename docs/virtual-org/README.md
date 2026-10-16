# Virtual Organization

ORYNTO is built by a small founder-led virtual organization where AI coding/research agents amplify specialist roles. Roles describe accountability, not headcount.

## Operating model

**Founder / Product Owner** owns vision, product decisions, priorities, scope, brand, and acceptance of irreversible tradeoffs.

**ChatGPT / Product & Architecture Lead** converts founder intent into coherent product contracts, architecture, requirements, delivery plans, review criteria, and audits implementation quality. It must challenge incoherent design rather than merely translate requests into code tasks.

**Cursor / Implementation Team** executes approved slices, tests, migrations, refactors, and documentation inside the repository contract. Cursor does not invent product policy when a decision is open.

## Virtual specialist roles

### Product Lead
- preserves product thesis;
- owns requirement traceability and acceptance contracts;
- prevents ERP/module creep;
- evaluates user value before implementation volume.

### Tech Lead / Architect
- owns service/package boundaries;
- protects deterministic-vs-AI boundary;
- reviews upstream adoption and dependencies;
- owns ADR quality and migration safety.

### AI Runtime Lead
- structured model/tool contracts;
- grounding and evaluation;
- provider abstraction;
- cost/latency/fallbacks;
- prompt/model auditability.

### Context & Data Lead
- canonical context model;
- provenance;
- projections/indexes;
- tenant-safe retrieval;
- data lifecycle/migrations.

### Channels Lead
- official provider adapters;
- normalized communication runtime;
- identity/thread mapping;
- channel policy and delivery state.

### Books / Domain Lead
- accounting/inventory correctness;
- BigCapital adoption boundary;
- domain APIs;
- reports, documents, reconciliation;
- reversal and invariants.

### UX / Product Design Lead
- anti-ERP information architecture;
- AI-first and classic dual-path coherence;
- mobile communication flows;
- desktop sheet/report workflows;
- trust/explanation UX.

### Security & Trust Lead
- tenancy and authorization;
- secrets/model-data boundaries;
- audit and retention;
- threat modeling;
- dependency/supply-chain review.

### QA / Evaluation Lead
- deterministic test pyramid;
- AI eval sets;
- end-to-end proof evidence;
- regression gates;
- performance/reliability criteria.

### Country Pack Lead
- tax/payment/banking/document capability interfaces;
- India pack first;
- ensures local needs do not contaminate global core.

## Delivery lifecycle

Every meaningful capability moves through:

1. **Intent** — founder/product problem and desired outcome.
2. **Decision** — unresolved architecture/product choices closed or explicitly deferred.
3. **Contract** — requirement ID + acceptance + data/action boundary.
4. **Design** — architecture/ADR when needed.
5. **Build** — implementation behind tests.
6. **Verify** — QA + AI eval + security/tenancy where applicable.
7. **Audit** — ChatGPT/product-architecture review against contract, not just diff aesthetics.
8. **Accept** — Product Owner acceptance when user behavior/scope changes materially.
9. **Observe** — production/shadow metrics and regressions.

## Handoff contract to Cursor

A Cursor implementation brief should contain:

- objective and user outcome;
- requirement/decision IDs;
- files/services expected to change, if known;
- invariants and non-goals;
- data ownership and tenancy rules;
- API/tool contract;
- acceptance tests;
- migration/rollback constraints;
- evidence to return.

Cursor should return:

- implementation summary;
- changed files;
- tests and results;
- migrations/schema/API changes;
- assumptions/deviations;
- screenshots/eval evidence where relevant;
- remaining risks.

## Quality rule

Agents are not rewarded for writing more code. They are rewarded for making the repository more correct, coherent, testable, secure, understandable, and aligned with ORYNTO's product thesis.

## Current mission

Before product feature acceleration, the virtual team must complete:

1. BigCapital license/adoption audit;
2. predecessor Duora requirement migration matrix;
3. repository/monorepo topology decision;
4. architecture proof design;
5. engineering quality baseline (CI, lint, type checks, tests, migrations, security/dependency checks);
6. first vertical slice only after those boundaries are sufficiently closed.
