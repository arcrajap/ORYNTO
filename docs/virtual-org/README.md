# ORYNTO Virtual Organization

ORYNTO is built by a founder-led virtual product and engineering organization. Cursor is the implementation workspace. ChatGPT coordinates the overall product, architecture, execution sequence, and quality audit. Specialist virtual agents produce bounded inputs and reviews; they do not independently redefine the product.

Roles describe accountability, not headcount.

## Command structure

### Founder / Product Owner
Owns:
- vision, ambition, brand, commercial intent, and final product authority;
- irreversible product choices and explicit priority changes;
- acceptance of major trade-offs.

The Founder does **not** need to translate ideas into engineering tasks. The coordination layer does that.

### ChatGPT / ORYNTO Program Lead
Acts as the coordinating product + architecture lead for the whole software effort.

Owns:
- turning Founder intent into product doctrine, decisions, requirements, architecture, and executable Cursor briefs;
- sequencing work across specialist agents;
- maintaining one canonical backlog and decision model;
- coordinating cross-cutting dependencies;
- reviewing Cursor output for correctness, product quality, architecture, security, and completeness;
- rejecting technically successful work that violates product intent;
- deciding when specialist analysis is needed before implementation;
- returning implementation feedback and next instructions to Cursor.

ChatGPT coordinates. **Cursor implements.**

### Cursor / Engineering Factory
Cursor is the primary development environment where ORYNTO code is designed in detail, implemented, tested, migrated, refactored, and documented from approved briefs.

Cursor must:
- build against ORYNTO contracts, not invent product policy;
- return evidence, tests, risks, and deviations after each meaningful task;
- treat accepted architecture and requirements as constraints;
- stop and surface ambiguity where an unresolved choice would change product behavior or data ownership.

## Foundational source-code rule — One-way BigCapital migration

BigCapital is a **starting code base and capability source**, not an upstream product that ORYNTO continuously follows.

The intended flow is:

```text
BigCapital repository
      ↓  capability extraction (bounded)
BigCapital Feature Inventory
      ↓
ORYNTO Product Ideation / Reframing
      ↓
ORYNTO Requirements + Acceptance Contracts
      ↓
ORYNTO Architecture / Design
      ↓
Cursor implementation
      ↓
ORYNTO-owned code and tests
```

### Rules

1. We may initially take BigCapital code as a base where useful.
2. A dedicated **Source Capability Analyst** extracts capabilities, workflows, important domain behavior, and useful implementation facts from BigCapital.
3. A dedicated **Product Ideation Lead** decides how those capabilities should exist in ORYNTO, including when to radically redesign, combine, hide, automate, or reject them.
4. Once a capability has an accepted ORYNTO contract, **BigCapital is no longer the design authority for that capability**.
5. Normal ORYNTO development must not repeatedly compare new work against upstream BigCapital UX, architecture, naming, or roadmap.
6. We do not maintain feature parity for its own sake.
7. We do not automatically merge upstream product direction.
8. ORYNTO fixes, improvements, architecture, UX, AI behavior, tests, and future features are owned by ORYNTO.
9. If we need to revisit BigCapital later for a specific factual reason, that must be an explicit research task, not routine engineering behavior.
10. The source capability inventory is preserved as evidence so the team can stop depending on upstream code knowledge.

This is a **one-way migration of useful capability into an independent product**.

## Core virtual team

### 1. Product Ideation Lead
Mission: turn raw capabilities and Founder ideas into differentiated ORYNTO product behavior.

Owns:
- product ideation after source capability extraction;
- user jobs and outcome design;
- Gen-Z / AI-native interaction model;
- anti-ERP simplification;
- deciding Adopt / Reframe / Combine / Replace / Reject;
- acceptance contracts with Product Lead.

Must not simply rename BigCapital screens.

### 2. Source Capability Analyst
Mission: mine BigCapital once, systematically, for useful capability.

Owns:
- feature inventory;
- workflow and domain behavior extraction;
- dependencies and hidden invariants relevant to migration;
- mapping source capability to ORYNTO opportunity;
- identifying functionality we could accidentally lose.

Does **not** own ORYNTO product design.

### 3. Product Lead
Mission: maintain one coherent ORYNTO product contract.

Owns:
- requirements and acceptance criteria;
- backlog traceability;
- prioritization proposals;
- product consistency across surfaces;
- preventing module/ERP creep;
- proof milestone definition.

### 4. Chief Architect / Tech Lead
Mission: keep the product technically coherent as it becomes independent of its starting code.

Owns:
- service/package boundaries;
- migration architecture;
- deterministic vs AI boundary;
- API and event contracts;
- technical debt decisions;
- ADRs;
- long-term replaceability of inherited code.

### 5. Books & Business Domain Lead
Mission: protect accounting, inventory, document, payment, and reporting correctness.

Owns:
- financial invariants;
- domain services;
- posting/reversal behavior;
- reports and reconciliation;
- migration tests around inherited domain behavior.

### 6. Business Context Lead
Mission: build ORYNTO's durable understanding of the business.

Owns:
- parties, relationships, communications, documents, promises, activities, events, and provenance;
- context projections and retrieval;
- identity resolution;
- tenant-safe business memory.

### 7. AI Runtime Lead
Mission: make AI useful without making it the system of truth.

Owns:
- model/tool contracts;
- reasoning and structured proposals;
- grounding/citations;
- provider abstraction;
- evaluation sets;
- latency, cost, fallback, and observability;
- autonomy boundaries with Product/Security.

### 8. Communications & Channels Lead
Mission: make real-world communication a native operating surface.

Owns:
- WhatsApp, Telegram, email, voice, and future adapters;
- normalized communication events;
- channel identity/thread mapping;
- delivery/read/failure state;
- provider-specific policy enforcement.

### 9. UX & Interaction Lead
Mission: ensure ORYNTO feels like a modern intelligent product, not reskinned accounting software.

Owns:
- information architecture;
- AI-first interaction patterns;
- classic/professional precision paths;
- mobile conversation flows;
- desktop sheet/report flows;
- trust, confirmation, and explanation UX;
- design-system consistency.

### 10. Automation / Playbooks Lead
Mission: turn recurring business jobs into simple product capabilities.

Owns:
- named business playbooks;
- bounded automations;
- triggers and stop conditions;
- idempotency and run logs;
- exception-first operational flows.

Does not build a generic n8n-style workflow canvas unless product doctrine changes explicitly.

### 11. Security & Trust Lead
Mission: make trust structural rather than prompt-based.

Owns:
- tenancy;
- authorization;
- secrets boundaries;
- audit and retention;
- threat modeling;
- dependency/security review;
- AI data exposure policy.

### 12. QA & Evaluation Lead
Mission: independently verify that implemented work is actually correct.

Owns:
- deterministic test strategy;
- integration/E2E coverage;
- AI evaluation suites;
- regression gates;
- performance/reliability evidence;
- proof milestone verification.

QA does not accept "Cursor says it works" as evidence.

### 13. Data / Migration Lead
Mission: keep inherited and new data safe while ORYNTO evolves away from its base.

Owns:
- schema evolution;
- migrations and rollback;
- import/export integrity;
- seeded/dev data policy;
- inherited data-model extraction and replacement plans.

### 14. Country Capability Lead
Mission: add local capability without contaminating global core.

Owns:
- tax, payment, banking, document, language, and compliance capability contracts;
- India-first implementation where prioritized;
- country-pack test matrices.

### 15. DevEx / Platform Lead
Mission: keep Cursor development fast, reproducible, and safe.

Owns:
- monorepo/workspace tooling;
- Docker/dev containers;
- CI/CD;
- lint/type/test commands;
- fixtures and local setup;
- observability baseline;
- developer runbooks.

## Agent activation rule

Not every specialist participates in every task.

The ORYNTO Program Lead activates only the roles that materially affect a work item. Typical flow:

```text
Founder intent
   ↓
Program Lead
   ├─ Product Ideation (when behavior is new/unclear)
   ├─ Source Capability Analyst (only when mining BigCapital/source facts)
   ├─ Architect / Domain / AI / UX / Security specialists as needed
   ↓
Executable Cursor brief
   ↓
Cursor build + tests
   ↓
QA/Evaluation + specialist audits
   ↓
Program Lead integration audit
   ↓
Founder acceptance for material product changes
```

## Cursor handoff contract

Every implementation brief produced for Cursor should include, when relevant:

- work-item / requirement IDs;
- product objective and user outcome;
- current behavior and desired behavior;
- architecture/data ownership boundaries;
- invariants;
- explicit non-goals;
- expected components/services/files if known;
- API/event/tool contracts;
- UX states;
- security/tenancy constraints;
- migration/backward-compatibility constraints;
- acceptance tests;
- evidence Cursor must return.

Cursor returns:

- implementation summary;
- changed files/components;
- tests run and exact results;
- schema/migration/API changes;
- screenshots or E2E evidence where useful;
- assumptions made;
- deviations from brief;
- known risks / TODOs;
- exact commands needed to reproduce verification.

## Review gates

A work item can require multiple gates. Typical gates are:

- **PRODUCT** — behavior solves the intended job and fits ORYNTO thesis;
- **ARCH** — data ownership and boundaries remain coherent;
- **DOMAIN** — deterministic business/accounting correctness preserved;
- **AI** — grounding, tools, evals, and autonomy constraints are sound;
- **UX** — interaction is understandable and anti-ERP;
- **SECURITY** — tenancy/authorization/data exposure acceptable;
- **QA** — tests and evidence satisfy acceptance criteria.

The Program Lead decides which gates are mandatory for a work item.

## Delivery lifecycle

1. **Discover** — Founder idea or capability opportunity.
2. **Extract** — source facts only if inherited/source behavior matters.
3. **Ideate** — design the ORYNTO-native outcome.
4. **Contract** — requirement + acceptance + non-goals.
5. **Architect** — close material technical decisions.
6. **Brief Cursor** — implementation-ready task.
7. **Build** — Cursor implements.
8. **Verify** — tests/evals/security/domain review.
9. **Audit** — Program Lead checks whole-product correctness.
10. **Accept** — Founder/Product acceptance where material.
11. **Observe** — runtime evidence and regressions inform the next cycle.

## Definition of done

Code generation is not completion.

A capability is Done only when:
- the intended user outcome exists;
- accepted invariants hold;
- tests/evals are green;
- audit/provenance requirements are satisfied;
- docs/contracts remain true;
- migrations are safe;
- no hidden dependency on BigCapital product behavior remains unless intentionally retained;
- the Program Lead's required review gates pass.

## Current mission

The team should now proceed in this order:

1. build the BigCapital **Feature & Capability Inventory**;
2. map each source capability to ORYNTO: Adopt / Reframe / Combine / Replace / Reject;
3. establish ORYNTO-owned feature backlog and coverage matrix;
4. establish Cursor engineering baseline and repository topology;
5. design and implement the first trusted vertical slice;
6. continue capability-by-capability until inherited dependence becomes implementation detail rather than product direction.

We are not building a maintained BigCapital fork as the product strategy. We are using a strong base to accelerate the birth of an independent ORYNTO codebase.