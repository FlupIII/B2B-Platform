# B2B Platform Documentation

This directory is the working source of truth for product decisions and requirements.

## Structure

- `decisions/` — approved, rejected and superseded decisions.
- `requirements/` — business and product requirements derived from approved decisions.
- `business-rules/` — reusable domain rules and constraints.
- `processes/` — end-to-end process and scenario descriptions.
- `open-questions/` — unresolved questions and known conflicts.
- `glossary/` — shared domain terminology.

## Working rules

1. A proposal does not become authoritative until explicitly approved.
2. Every approved decision is checked against existing decisions, requirements, business rules and processes for conflicts.
3. Approved decisions are never silently overwritten; changed decisions are superseded with traceable history.
4. Requirements and process documents must reference the decisions that justify them where applicable.
5. Open conflicts remain visible until explicitly resolved.
6. Each substantial topic should be discussed in a separate ChatGPT project chat to reduce context mixing.

## Source precedence

When sources disagree, use this order unless an explicit newer approval says otherwise:

1. latest approved decision in this repository;
2. approved requirement or process aligned with that decision;
3. recorded stakeholder/meeting decision;
4. proposal or working draft;
5. raw notes.
