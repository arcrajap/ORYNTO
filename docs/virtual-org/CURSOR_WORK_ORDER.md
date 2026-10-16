# Cursor Work Order Protocol

This protocol defines how ORYNTO work is handed from the Program Lead and specialist agents into Cursor.

## Principle

Cursor is the engineering factory. It receives bounded work orders and returns implementation evidence.

It does not own product direction, roadmap interpretation, or unresolved architecture policy.

## Work order template

Each meaningful Cursor task should use this structure.

```md
# WORK ORDER: <ID> — <title>

## Objective
<user/business outcome>

## Why this matters
<product rationale>

## Source inputs
- Requirement IDs:
- Decision IDs:
- Relevant docs:
- Relevant extracted BigCapital capability, if any:

## Current behavior
<what exists now>

## Desired ORYNTO behavior
<what should exist after implementation>

## Invariants
- ...

## Non-goals
- ...

## Architecture boundaries
- canonical data owner:
- read path:
- write path:
- events/tools/APIs:
- tenancy/authorization:

## UX contract
<states/interactions/copy expectations>

## Implementation guidance
<known files/modules/components or constraints; not an invitation to redesign product policy>

## Tests / acceptance
- ...

## Evidence required from Cursor
- implementation summary
- changed files/components
- exact test commands and outputs
- migrations/schema/API changes
- screenshots/E2E evidence where relevant
- assumptions/deviations
- known risks/TODOs
```

## Cursor completion response

Cursor should respond with evidence, not only a summary.

Minimum response:

```md
# IMPLEMENTATION RETURN: <ID>

## Summary

## Changed files

## Behavior implemented

## Tests run
<commands + results>

## Schema / migrations / APIs

## Evidence

## Deviations from work order

## Assumptions

## Known risks / follow-ups
```

## Stop conditions

Cursor must stop and surface the issue rather than guess if:

1. the requested change requires redefining canonical data ownership;
2. an accepted decision conflicts with the work order;
3. accounting/business invariants are unclear;
4. tenant isolation or authorization behavior is ambiguous;
5. a consequential AI action lacks an authorization contract;
6. a migration could lose or reinterpret existing data;
7. product behavior has multiple materially different interpretations not resolved by the brief.

## Review routing

After Cursor returns work, the Program Lead routes it through the necessary specialist gates:

- PRODUCT
- ARCH
- DOMAIN
- AI
- UX
- SECURITY
- QA

Only applicable gates are activated.

## Rule against upstream drift

For a migrated capability, the accepted ORYNTO requirement/work order is the implementation authority.

Cursor should not go back to BigCapital to answer product-design questions unless the work order explicitly asks for source-fact research. BigCapital is not a standing design reference after capability extraction.
