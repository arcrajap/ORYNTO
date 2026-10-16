# Requirements Baseline

**Status:** Foundation migration baseline

ORYNTO inherits useful product learning from the predecessor Duora concept, but requirements are being migrated deliberately into ORYNTO's stronger product/architecture thesis.

## Migration policy

1. Existing requirement IDs remain valuable traceability anchors and should not be discarded casually.
2. A predecessor requirement is not automatically accepted unchanged; it may be **Adopted**, **Reframed**, **Superseded**, **Deferred**, or **Rejected**.
3. Every migrated requirement must map to ORYNTO's product thesis and architecture.
4. New infrastructure requirements may be added where the predecessor backlog lacked foundational concepts such as business context, communication normalization, action contracts, evaluation, and model/runtime governance.
5. Sequencing is not scope deletion.

## Legacy backlog coverage to preserve

The predecessor product covered these major families:

- `PLAT-*` — platform, tenancy, auth
- `BOOK-*` — deterministic accounting/business books
- `AI-*` — assistant and action flows
- `SHEET-*` — Excel-like operating surface
- `CH-*` — WhatsApp/email/Telegram and messaging
- `WF-*` — named business playbooks/automations
- `LANG-*` — language and voice
- `TRUST-*` — trust/security/compliance
- `NFR-*` — non-functional requirements
- `TAX-*` — country/tax capabilities
- `UX-*` — anti-ERP user experience
- future-year proof and expansion themes

These should be imported into a future `coverage-matrix.md` only after re-evaluation against ORYNTO.

## New ORYNTO foundation requirement families

### CTX — Business Context

- **CTX-01 Must** — canonical business-context primitives for party, communication, document, event, file, commitment, activity, relationship, and provenance.
- **CTX-02 Must** — context links reference canonical domain records rather than duplicating posted accounting truth.
- **CTX-03 Must** — every derived context object carries tenant scope and provenance.
- **CTX-04 Must** — commitments/promises can be extracted as proposals and confirmed/managed without altering financial truth.
- **CTX-05 Should** — customer/supplier timeline unifies communications, documents, payments, promises, and activities.

### COMMS — Communication Runtime

- **COMMS-01 Must** — normalized inbound/outbound `CommunicationEvent` contract.
- **COMMS-02 Must** — official-provider adapters only for regulated messaging channels.
- **COMMS-03 Must** — external identity resolution and channel/thread correlation.
- **COMMS-04 Must** — attachments/media referenced with provenance and tenant-safe access.
- **COMMS-05 Must** — delivery/window/template policy enforced outside the LLM.
- **COMMS-06 Should** — provider-independent conversation timeline and resend/error state.

### ACT — Business Action Layer

- **ACT-01 Must** — typed tool contracts between AI and deterministic domain services.
- **ACT-02 Must** — authorization and tenant checks execute outside model reasoning.
- **ACT-03 Must** — consequential actions classified by READ/DRAFT/CONFIRM/POLICY_AUTO/FORBIDDEN or equivalent policy.
- **ACT-04 Must** — idempotency and audit records for externally visible/financial mutations.
- **ACT-05 Must** — reversible/compensating behavior defined where domain allows it.
- **ACT-06 Must** — no unrestricted model database writes.

### AIR — AI Runtime

- **AIR-01 Must** — model/provider abstraction with structured outputs and validation.
- **AIR-02 Must** — grounded retrieval with source/provenance references for business-fact answers.
- **AIR-03 Must** — model/tool/prompt execution metadata sufficient for audit/debug/evaluation without leaking secrets.
- **AIR-04 Must** — AI outage does not prevent deterministic core business work.
- **AIR-05 Must** — evaluation harness for intent/entity/action-plan accuracy before autonomy increases.
- **AIR-06 Should** — cost/latency/model-routing controls.
- **AIR-07 Should** — bounded proactive exception ranking with explicit suppression/noise metrics.

### CAP — Country Capability Platform

- **CAP-01 Must** — country-specific tax/payment/banking/document rules behind capability contracts.
- **CAP-02 Must** — shared core avoids hard-coded India-specific assumptions.
- **CAP-03 Should** — capability discovery/versioning supports multiple country packs.

### GOV — Product/Engineering Governance

- **GOV-01 Must** — accepted product and architecture decisions recorded before implementation guesses.
- **GOV-02 Must** — every significant PR traces to requirement/decision IDs.
- **GOV-03 Must** — predecessor backlog receives a formal migration coverage matrix with no silent loss.
- **GOV-04 Must** — BigCapital upstream license/adoption decision closed before source import.

## Founding proof milestone

ORYNTO's first architecture proof should demonstrate one complete trusted loop:

1. business input arrives through a real or production-faithful communication surface;
2. external identity is resolved under the correct tenant;
3. ORYNTO derives grounded business context;
4. AI produces a typed proposal, not a direct mutation;
5. the user reviews/authorizes the consequential action;
6. a deterministic domain service performs the action;
7. the resulting business document/state is canonical;
8. communication/delivery state and audit trail are attached to the same context;
9. the same result is visible from classic/professional UI.

A sales invoice is the preferred first proof unless an ADR changes it.

## Next artifact

Create `docs/product/coverage-matrix.md` during backlog migration. It must map every predecessor requirement/decision/future theme to an ORYNTO disposition and map every new ORYNTO requirement to delivery ownership and evidence.
