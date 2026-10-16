# Product Principles

These principles are product constraints, not slogans. If a design violates one, it requires an explicit recorded decision.

## P1 — Conversation is an input surface, not the database

Messages, email, voice, and documents are evidence of business activity. They may create context and proposals, but canonical business records live in deterministic domain systems.

## P2 — One business truth

Every surface—web, mobile web, sheet, WhatsApp, Telegram, email, API, or future native app—must converge on the same customers, documents, payments, inventory, permissions, and audit history.

## P3 — AI at the edge; deterministic systems at the core

Use models for interpretation, extraction, ranking, summarization, planning, and communication. Use typed domain logic for authorization, accounting, tax rules, financial posting, irreversible state transitions, and invariants.

## P4 — Explain before automating

The user should be able to see what ORYNTO understood, the evidence used, the proposed action, and the meaningful consequence. Increased autonomy is earned through policy and evidence, not assumed because a model is confident.

## P5 — Context beats chat history

Durable business memory must be structured around business entities, relationships, events, commitments, documents, and provenance. A long transcript is not a business memory system.

## P6 — Channels are adapters

Official WhatsApp, Telegram, email, voice, SMS/RCS, web, and future channels normalize into common communication primitives. Business logic must not be duplicated per channel.

## P7 — Actions are tools with contracts

AI does not directly "do accounting." It calls versioned, authorized business capabilities with typed inputs/outputs, validations, idempotency, and audit events.

## P8 — Proactivity is selective

ORYNTO should surface the few things that genuinely need attention, not generate another notification feed. Prefer ranked exceptions and actionable briefs over dashboard noise.

## P9 — Anti-ERP by design

Organize the product around jobs and outcomes, not internal modules. Hide power features until needed. Use normal business language. Never make setup complexity a prerequisite for a basic task.

## P10 — Professional escape hatches remain

Accountants, finance teams, and power users need deterministic screens, journals, reports, exports, reconciliation, and exact records. AI-first must not mean precision-last.

## P11 — Global core, local capabilities

Do not bake one country's tax, banking, payment, language, or compliance assumptions into shared business primitives.

## P12 — Trust is product functionality

Tenancy, permissions, provenance, audit history, reversals, retention, privacy, safe external messaging, and model-data boundaries are visible product requirements, not infrastructure cleanup.

## P13 — No fake agent autonomy

An agent that cannot prove its inputs, authorization, and result is a demo. ORYNTO must distinguish suggestion, draft, confirmed action, automated policy action, and failed action in the product and audit log.

## P14 — Build leverage, not inheritance

Reuse BigCapital where it gives ORYNTO reliable accounting/business primitives. Do not inherit its UX, module structure, terminology, or architectural limitations merely because they already exist.

## P15 — Complete product, sequenced delivery

Sequencing is allowed; silent scope loss is not. Requirements stay traceable until delivered, consciously replaced, or explicitly rejected with a recorded reason.
