# BigCapital Capability Extraction Runbook

## Purpose

BigCapital is a source of starting capability and implementation acceleration. This runbook ensures ORYNTO extracts useful product/domain knowledge **once, systematically, and with traceability** without turning upstream code into a permanent product authority.

## Owner

Primary: **Source Capability Analyst**  
Partners: Product Ideation Lead, Books & Business Domain Lead, Chief Architect, UX Lead, QA Lead as needed.

## Output

The canonical output is:

`docs/product/BIGCAPITAL_CAPABILITY_INVENTORY.md`

Each capability must receive a stable extraction ID:

`BCAP-###`

## Extraction scope

Review the BigCapital repository for:

- user-facing features;
- business workflows;
- accounting/inventory/payment/reporting behavior;
- permissions and tenancy behavior;
- document lifecycle;
- imports/exports;
- notifications and communication behavior;
- configuration/settings;
- reports and operational views;
- background jobs;
- integrations;
- important domain rules and invariants;
- tests that reveal intended behavior;
- implementation constraints that matter for migration.

Do not treat current screen/module boundaries as product requirements.

## Capability record

For each capability record:

```md
## BCAP-### — <neutral capability name>

### Source behavior
What BigCapital objectively supports.

### User job
What business job this capability serves.

### Domain facts / invariants
Rules that appear important to correctness.

### Source dependencies
Important modules, data, APIs, jobs, permissions, or services.

### Evidence
Paths/tests/components that establish the source facts.

### ORYNTO opportunity
Initial product opportunity; not yet the final design.

### Proposed disposition
- Adopt
- Reframe
- Combine
- Replace
- Reject

### Risks if omitted
What business correctness or expected functionality could be lost.
```

## Product ideation handoff

The Product Ideation Lead receives extracted capabilities, not raw upstream UX as instructions.

For each BCAP item, ideation asks:

1. What user job is actually being solved?
2. Would an AI-native/business-context-first product solve it differently?
3. Should the capability be visible, automatic, conversational, sheet-driven, classic, or background-only?
4. Can several old modules collapse into one user outcome?
5. Does the capability belong in global core or a country capability?
6. Which parts are deterministic and which may use AI?
7. What must remain auditable and reversible?
8. Is the feature worth carrying into ORYNTO at all?

The resulting ORYNTO requirement must reference the relevant `BCAP-*` ID(s) for traceability.

## One-way completion rule

A BCAP item becomes **MIGRATED** when:

- source behavior is sufficiently documented;
- ORYNTO disposition is accepted;
- an ORYNTO requirement/decision covers the intended outcome;
- correctness-sensitive invariants are captured in tests/contracts where needed.

After `MIGRATED`:

- upstream UI is not a design reference;
- upstream naming is not a naming reference;
- upstream roadmap is irrelevant;
- feature parity is not required;
- future ORYNTO changes are driven by ORYNTO product evidence and strategy.

Upstream may only be revisited through an explicit source-research task when a concrete factual gap remains.

## Extraction phases

### Pass A — Inventory
Enumerate capabilities broadly. Optimize for coverage, not product redesign.

### Pass B — Domain depth
Deep-review correctness-sensitive areas such as posting, payments, inventory, taxes, reports, reversals, tenancy, and permissions.

### Pass C — Product disposition
Product Ideation + Product Lead classify every BCAP item.

### Pass D — Coverage freeze
Verify there are no unexplained source capabilities and no ORYNTO requirement without clear product ownership.

### Pass E — Upstream dependency reduction
As ORYNTO areas are redesigned/rewritten, record where inherited implementation remains versus ORYNTO-owned implementation.

## Success condition

The extraction succeeds when the ORYNTO team can plan and develop the product using its own requirement, architecture, and test corpus **without needing routine knowledge of BigCapital's repository**.
