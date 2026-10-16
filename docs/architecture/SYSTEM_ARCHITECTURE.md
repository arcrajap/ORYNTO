# System Architecture

**Status:** Foundation baseline — implementation must validate and refine this design through ADRs.

## 1. Architectural objective

ORYNTO must accept messy human business activity from many surfaces, convert it into durable business context, reason over that context, and execute safe business actions without allowing probabilistic AI to become the source of financial or operational truth.

## 2. Logical architecture

```text
 Human / external world
 ─────────────────────────────────────────────────────
 WhatsApp · Email · Telegram · Voice · Docs · Sheets
 Web · Payments · Bank events · APIs
                         │
                         ▼
                COMMUNICATION RUNTIME
        adapters · identity · media · threading
        normalization · delivery · provenance
                         │
                         ▼
                 BUSINESS CONTEXT GRAPH
  parties · relationships · documents · events · files
  commitments · communications · activities · references
                         │
             ┌───────────┴───────────┐
             ▼                       ▼
         AI RUNTIME             QUERY / VIEWS
 interpretation · retrieval      web · sheet · reports
 planning · composition          timeline · search
 evaluation · policy hints
             │
             ▼
                 BUSINESS ACTION LAYER
 typed tools · authorization · validation · idempotency
 confirmation policy · audit · reversals · orchestration
             │
             ▼
              DETERMINISTIC DOMAIN SERVICES
 books · invoices · bills · payments · inventory · contacts
 reporting · tax capabilities · country capabilities
             │
             ▼
                   SYSTEMS OF RECORD
          accounting DB · operational stores · files
```

## 3. Architectural boundaries

### 3.1 Communication Runtime

Responsibilities:

- official channel adapters;
- inbound/outbound normalization;
- external identity resolution;
- message/thread correlation;
- media ingestion and references;
- channel-policy enforcement such as WhatsApp windows/templates;
- delivery state and provenance.

It must not own invoice/payment/accounting logic.

Canonical conceptual event:

```text
CommunicationEvent
- organization_id
- channel
- direction
- external_thread_id
- external_message_id
- participants
- occurred_at
- content_type
- content_reference
- attachments[]
- reply_context
- provenance
```

### 3.2 Business Context Graph

This is a pragmatic domain context model, not a graph-database mandate.

It connects:

- Person / Organization / Customer / Supplier
- Communication / Thread
- File / Attachment
- Business Document
- Payment / financial reference
- Commitment / Promise
- Task / Activity
- Event
- Relationship
- Provenance / evidence

Storage technology must be chosen from access patterns and operational constraints. Do not adopt a graph database merely because the model is called a graph.

### 3.3 AI Runtime

Responsibilities:

- intent/entity interpretation;
- grounded retrieval;
- document understanding;
- action planning;
- business-language generation;
- anomaly/exceptions assistance;
- model routing and fallbacks;
- structured output validation;
- prompt/tool/model audit metadata;
- offline/evaluation harnesses.

AI output is untrusted until validated by policy/domain contracts.

### 3.4 Business Action Layer

The action layer is the trust boundary between probabilistic intelligence and deterministic business state.

Every consequential tool should define:

- typed input/output;
- actor and tenant context;
- permission check;
- preconditions;
- validation;
- idempotency behavior;
- confirmation/automation policy;
- resulting domain events;
- error contract;
- audit record;
- reversal/compensation behavior where relevant.

Example capabilities:

```text
sales.create_invoice_draft
sales.post_invoice
payments.record_receipt
purchases.create_bill_draft
inventory.get_availability
communications.send_message
receivables.schedule_followup
reports.query_grounded_metric
```

The model must not receive direct unrestricted database mutation access.

### 3.5 Deterministic Domain Services

BigCapital is the leading candidate for accelerating accounting, contacts, inventory, documents, and reports. Before adoption we must audit:

- upstream license and derivative obligations;
- tenancy model;
- domain/service boundaries;
- data model quality;
- auth/permissions;
- migration strategy;
- API suitability;
- test coverage;
- upgrade/rebase feasibility;
- security posture;
- areas to fork versus wrap.

No assumption in this document pre-approves a blind fork.

## 4. Data ownership rules

1. Communication providers own external delivery state; ORYNTO persists normalized business-relevant provenance.
2. The context layer owns links/meaning between business events but does not duplicate canonical financial balances.
3. Deterministic domain services own posted accounting and inventory truth.
4. AI runtime owns no canonical business truth.
5. Search/vector indexes are derived projections and rebuildable.
6. Sheets are views/input surfaces; posting must create legal domain documents rather than mutate accounting balances directly.

## 5. Identity and tenancy

Every request/action must carry explicit organization/tenant and actor context outside the model prompt. Retrieval, tool execution, logs, media access, and derived indexes must be tenant-scoped structurally.

External identities (phone/email/channel account) must map through verified/controlled organization relationships. A phone number in a prompt is not authorization.

## 6. Confirmation and autonomy

Actions should be classified at least as:

- **READ** — grounded lookup, no mutation;
- **DRAFT** — create non-posted proposal/draft;
- **CONFIRM** — user approval required before consequential mutation/send;
- **POLICY_AUTO** — automation explicitly enabled by an authorized user within bounded policy;
- **FORBIDDEN** — action not permitted to AI/automation.

The classification is policy, not model confidence.

## 7. Event and audit model

ORYNTO should be able to answer:

- what happened?
- which business object changed?
- who/what initiated it?
- from which channel/source?
- what evidence was used?
- what model/tool version participated?
- what authorization/confirmation applied?
- what external delivery/result occurred?
- can it be reversed or compensated?

## 8. Surfaces

### Owner/mobile-first

Home attention brief, customer/supplier context, invoices, payments, confirmations, messages, simple reports and settings.

### Desktop-class

Sheet, detailed reports, accountant tools, imports/exports, configuration, audit and reconciliation.

### Conversational

WhatsApp, Telegram, email, web ask bar, voice, future supported channels.

All surfaces share domain services and context.

## 9. Country capability model

Country-specific capabilities include tax schema, invoice requirements, payment rails, banking connectors, filing/export formats, identity/registration fields, localization, and compliance policy.

The shared core should consume capability interfaces rather than branching globally on country everywhere.

## 10. Initial implementation sequence

The first engineering phase is not feature coding. It is **foundation validation**:

1. close BigCapital licensing/adoption decision;
2. audit upstream architecture and select fork/wrap boundaries;
3. define monorepo/package topology;
4. define tenancy/auth boundary;
5. define canonical communication event and business context primitives;
6. define the first typed AI action contract;
7. establish CI, tests, migrations, observability, and security baseline;
8. build one end-to-end vertical slice proving conversation → context → proposal → confirmed deterministic action → audit trail.

The recommended proof slice is a customer invoice because it touches identity, context, accounting, confirmation, delivery, and audit without requiring broad automation.
