# AGENTS.md

## Purpose

This repository is developed by a virtual product/engineering organization using humans, ChatGPT, Cursor, and other coding agents. This file is the operating contract for every contributor.

## Product authority

The Founder/Product Owner owns product intent, scope, and irreversible product decisions. Agents may propose; they must not silently redefine the product.

The authoritative product hierarchy is:

1. `docs/foundation/PRODUCT_THESIS.md`
2. `docs/foundation/PRODUCT_PRINCIPLES.md`
3. `docs/product/DECISIONS.md`
4. `docs/product/REQUIREMENTS.md`
5. architecture decision records and accepted implementation plans
6. code

When code conflicts with an accepted product/architecture decision, treat the conflict as a defect or raise a decision change explicitly.

## Non-negotiable engineering rules

1. **AI is not the ledger.** LLM output never directly mutates accounting truth.
2. **One canonical business truth.** No shadow ledger, shadow customer store, or channel-only business record.
3. **Consequential actions are explicit.** Actions affecting money, accounting, external communications, permissions, tax, or irreversible state require an authorized policy path and audit record.
4. **Channels normalize inward.** WhatsApp, Telegram, email, web, voice, and future channels must normalize into shared communication/business primitives rather than creating channel-specific business logic.
5. **Domain actions normalize outward.** Invoice, bill, payment, stock, reminder, and related actions must flow through stable domain/tool contracts.
6. **Tenant isolation is structural.** Never rely on prompt instructions for tenancy or authorization.
7. **No secrets in model context.** Model prompts receive handles or sanitized values only where possible.
8. **No fake completeness.** Placeholder integrations, mocked compliance, fake financial correctness, or demo-only behavior must be labeled.
9. **Auditability beats magic.** Users must be able to understand what happened, why, from which source, and who/what authorized it.
10. **BigCapital is a core candidate, not the product shell.** Reuse its deterministic accounting/domain strengths without inheriting its UX, information architecture, or module boundaries by default.

## Product UX rules

- Never design ORYNTO as an ERP module wall.
- Do not expose internal architecture or agent jargon to normal users.
- Prefer intent → proposal → review/confirm → result over navigate → configure → form → save.
- Classic deterministic screens remain available where precision, audit, or professional workflows require them.
- Mobile communication/business actions and desktop-class sheets/reports may have different optimized surfaces while sharing the same truth.
- Do not create a workflow-canvas product unless the Founder explicitly reverses the non-goal.

## How agents should work

Before coding:

1. identify the requirement/decision being implemented;
2. read the relevant architecture contract;
3. state assumptions that could change behavior or data ownership;
4. prefer a small coherent vertical slice over speculative framework code;
5. define tests before claiming completion.

For every meaningful PR:

- link requirement or decision IDs;
- explain data model/API changes;
- include security/tenancy implications;
- include migrations and rollback notes where applicable;
- include tests and evidence;
- distinguish mocked paths from production-capable paths;
- update docs if the implementation changes an accepted contract.

## Definition of done

A story is not done because code compiles. Done means its acceptance contract is satisfied, tests are green, observability/audit implications are handled, documentation remains true, and no unresolved product decision was guessed.

## Repository hygiene

- Never commit credentials, tokens, local `.env` files, production data, or customer content.
- Keep generated artifacts and dependency caches out of git.
- Prefer conventional commits: `feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`.
- Do not introduce a second backlog without preserving requirement IDs.
- Decisions that change architecture or product behavior belong in `docs/product/DECISIONS.md` and, when technical enough, an ADR.

## Current phase

The repository is in **FOUNDATION / PRE-IMPLEMENTATION** until the ORYNTO architecture baseline and BigCapital technical adoption topology are accepted. Licensing is not an implementation gate; the Founder has already reviewed it.
