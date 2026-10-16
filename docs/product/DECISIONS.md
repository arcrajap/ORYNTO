# Product & Architecture Decisions

This is the authoritative decision ledger for product/architecture choices that materially shape ORYNTO. Decisions may be refined by ADRs, but they must not be silently changed in code.

## Status values

- **Proposed** — needs explicit closure.
- **Accepted** — current product/architecture contract.
- **Superseded** — replaced by a later decision.
- **Rejected** — considered and intentionally not chosen.

## DEC-001 — Product name and category

**Status:** Accepted  
**Date:** 2026-10-16  
**Choice:** Product/company working brand is **ORYNTO**. Working category is **AI Business Operator**. Duora is a predecessor concept and is not the active product name.  
**Why:** ORYNTO is intended to be broader than accounting while still supporting trusted financial operations. The name must not constrain the company to ERP/accounting terminology.

## DEC-002 — Product center of gravity

**Status:** Accepted  
**Date:** 2026-10-16  
**Choice:** ORYNTO is centered on business context + trusted action across conversations, documents, voice, sheets, payments, and deterministic domain systems. Accounting is a foundational truth system, not the entire product experience.  
**Why:** Real business activity begins outside modules; ORYNTO's differentiation is translating that activity into structured, auditable operation.

## DEC-003 — AI authority boundary

**Status:** Accepted  
**Date:** 2026-10-16  
**Choice:** AI may interpret, retrieve, compose, plan, rank, and propose. Deterministic domain/action services own authorization, invariants, posting, and canonical state mutation.  
**Rule:** No unrestricted LLM database writes. Model confidence does not substitute for authorization policy.

## DEC-004 — Communication architecture

**Status:** Accepted  
**Date:** 2026-10-16  
**Choice:** WhatsApp, Telegram, email, web, voice, and future channels are provider adapters into shared communication/context primitives. Channel-specific business logic is prohibited unless the behavior is inherently provider-policy-specific.  
**Why:** One business must not fragment into separate bots/records by channel.

## DEC-005 — Business Context Graph

**Status:** Accepted in principle; storage implementation open  
**Date:** 2026-10-16  
**Choice:** ORYNTO needs a durable business-context model linking parties, communications, documents, files, activities, commitments, events, relationships, and provenance.  
**Non-choice:** The term "graph" does not mandate a graph database.

## DEC-006 — Workflow product stance

**Status:** Accepted  
**Date:** 2026-10-16  
**Choice:** ORYNTO ships named business jobs/playbooks and bounded automations rather than a general tenant-facing node/canvas workflow builder.  
**Why:** The product should hide implementation complexity and remain outcome-oriented. Reversal requires Founder/Product Owner decision.

## DEC-007 — Global core, country capabilities

**Status:** Accepted  
**Date:** 2026-10-16  
**Choice:** Core architecture is global. Country tax, banking, payment, language, document, identity, and compliance capabilities are modularized behind country/capability contracts. India remains the preferred first pack unless sequencing changes.  
**Why:** Avoid expensive later extraction of India assumptions from the core.

## DEC-008 — BigCapital adoption model

**Status:** Proposed / TECHNICAL  
**Founder decision:** Licensing has already been reviewed by the Founder and is **not an ORYNTO implementation blocker**. Do not reopen licensing as a gating question unless the Founder explicitly asks to revisit it.  
**Question remaining:** Do we fork BigCapital as the accounting/domain core, wrap selected services, or adopt a hybrid?  
**Required technical evidence:**

- exact upstream repository/version we will base from;
- architecture/domain/service audit;
- tenant model and isolation audit;
- auth/permissions model;
- accounting, inventory, document, and reporting boundaries worth reusing;
- test/security posture;
- upgrade/upstream-sync strategy;
- fork-vs-wrapper-vs-hybrid recommendation;
- concrete list of upstream UI/architecture concepts ORYNTO will not inherit.

**Implementation rule:** BigCapital adoption may proceed once the technical topology is clear enough for a reversible first import. Licensing review is not a prerequisite.

## DEC-009 — Repository topology

**Status:** Proposed  
**Question:** Choose the topology that best supports BigCapital reuse while keeping ORYNTO runtime layers independently governed.  
**Preferred direction:** product apps + platform/runtime packages + deterministic core/adapters in one governed repository unless the technical audit shows a cleaner boundary.

## DEC-010 — First architecture proof

**Status:** Accepted  
**Date:** 2026-10-16  
**Choice:** First end-to-end proof is **conversation/context → invoice proposal → explicit authorization → deterministic invoice post → delivery/audit/timeline**, visible through both AI-first and classic/professional surfaces.  
**Why:** It exercises the architecture without prematurely building broad automation.

## DEC-011 — External messaging providers

**Status:** Accepted  
**Date:** 2026-10-16  
**Choice:** Official provider APIs only. Unofficial/grey WhatsApp or similar automation is a non-goal. Provider window/template rules are enforced deterministically outside the model.

## DEC-012 — Autonomy progression

**Status:** Accepted  
**Date:** 2026-10-16  
**Choice:** Start with read/draft/confirm flows. Bounded auto-actions require explicit owner policy, auditability, domain-specific safety checks, and evaluation evidence. No general autonomous posting default.

## Open decisions before implementation acceleration

1. **DEC-008 BigCapital technical adoption model** — technical decision, not license gate.
2. **DEC-009 repository topology** — depends on enough of DEC-008 being understood.
3. Authentication/identity provider architecture.
4. Primary database and context projection strategy after upstream audit.
5. Model-provider baseline and data-handling policy.
6. Official WhatsApp provider path (Cloud API direct vs BSP) when channel implementation begins.
7. Open-core/cloud SKU boundaries if/when commercially relevant.
