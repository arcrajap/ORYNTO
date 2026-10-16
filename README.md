# ORYNTO

> **Your business already talks. Now it can think and act.**

ORYNTO is an **AI Business Operator**: an AI-native operating layer for businesses where work arrives through conversations, documents, voice, email, sheets, payments, and messaging, and is converted into trusted business actions.

## Founding idea

Businesses do not naturally operate in software modules. They operate through customers, suppliers, employees, conversations, promises, documents, money, and decisions.

ORYNTO connects those realities into one operating context.

It should be possible to:

- forward a supplier bill and receive a correctly grounded draft;
- ask what a customer owes and receive cited business facts;
- turn a WhatsApp or Telegram conversation into an order or invoice proposal;
- interpret voice, documents, spreadsheets, and messages as business intent;
- detect promises, exceptions, missing payments, stock risks, and follow-ups;
- act from the same business context regardless of where the request originated;
- keep deterministic accounting and operational systems as the source of truth underneath AI.

## Product doctrine

**ORYNTO sees.** Conversations, email, voice, documents, payments, sheets, and events.

**ORYNTO remembers.** Customers, suppliers, relationships, documents, commitments, history, and context.

**ORYNTO understands.** Intent, entities, relationships, exceptions, and likely next actions.

**ORYNTO acts.** It proposes and executes authorized business actions through deterministic domain services.

**The system of truth proves.** AI never becomes the ledger.

## Architecture stance

BigCapital is expected to provide a substantial part of ORYNTO's accounting kernel, subject to upstream-license review and architectural validation. It is **infrastructure, not ORYNTO's product architecture or user experience**.

ORYNTO's differentiated layers are expected to include:

1. Business Context Graph
2. Communication Runtime
3. AI Runtime
4. Business Action Layer
5. Modern web / sheet / conversational surfaces
6. Deterministic accounting, inventory, document, and reporting services underneath

See [`docs/architecture/SYSTEM_ARCHITECTURE.md`](docs/architecture/SYSTEM_ARCHITECTURE.md).

## Repository status

**FOUNDATION / PRE-IMPLEMENTATION**

The repository is intentionally beginning with product and engineering contracts before importing or modifying the BigCapital codebase.

No production claims should be inferred from this repository yet.

## Start here

- [`AGENTS.md`](AGENTS.md) — operating contract for Cursor/AI/human contributors
- [`docs/foundation/PRODUCT_THESIS.md`](docs/foundation/PRODUCT_THESIS.md) — what ORYNTO is and is not
- [`docs/foundation/PRODUCT_PRINCIPLES.md`](docs/foundation/PRODUCT_PRINCIPLES.md) — non-negotiable design principles
- [`docs/architecture/SYSTEM_ARCHITECTURE.md`](docs/architecture/SYSTEM_ARCHITECTURE.md) — target architecture
- [`docs/product/REQUIREMENTS.md`](docs/product/REQUIREMENTS.md) — requirements baseline and migration policy
- [`docs/product/DECISIONS.md`](docs/product/DECISIONS.md) — product/architecture decision ledger
- [`docs/virtual-org/README.md`](docs/virtual-org/README.md) — virtual team and delivery model

## Brand

**Name:** ORYNTO  
**Category:** AI Business Operator  
**Working promise:** Your business already talks. Now it can think and act.

The product name is **ORYNTO**, not Duora. Duora is a predecessor concept whose useful requirements and decisions are being re-evaluated and migrated with traceability rather than copied blindly.

## Licensing

No project license has been selected yet. Before importing or modifying upstream BigCapital code, the project must complete and record the upstream-license and derivative-work decision in `docs/product/DECISIONS.md`.

Do not add proprietary assumptions, incompatible dependencies, or a license file until that decision is closed.
