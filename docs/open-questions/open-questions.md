# Open Questions

This file tracks unresolved questions that can affect approved decisions, requirements, processes, UX or integrations.

## Q-001 — Ordering above available stock

- **Status:** Open
- **Question:** Can a customer order a quantity greater than the available-to-order stock of the warehouse assigned to the selected trade point?
- **Impact:** Catalog, cart, order validation, statuses, account-manager workflow, 1C integration.
- **Options under consideration:**
  1. hard block;
  2. allow only available quantity;
  3. send for clarification/manual review;
  4. backorder / order under future supply;
  5. differentiated rule by product/customer.

## Q-002 — Select trade point before or after building the cart

- **Status:** Open
- **Question:** Should the customer be able to build a purchase draft before selecting a trade point?
- **Constraint:** Stock and possibly assortment/prices depend on the warehouse assigned to the trade point.
- **Current proposal:** Separate a pre-selection purchase draft from the validated cart. After selecting the trade point, resolve warehouse and revalidate stock, assortment, price and order constraints.

## Q-003 — Create a new trade point during checkout

- **Status:** Open
- **Question:** Can the customer start creating a new trade point from checkout without creating an order before moderation is complete?
- **Current proposal:** Preserve the purchase draft, moderate the trade point, assign the warehouse, then revalidate the draft and require customer confirmation before order creation.

## Q-004 — Final order status model

- **Status:** Open
- **Question:** What is the final set of order statuses and allowed transitions?
- **Current recommendation:** Distinguish recoverable validation states from final outcomes. Use `Requires correction` for fixable validation failures, `Rejected` for final refusal, and `Cancelled` for a valid order deliberately cancelled by an authorized actor. Do not use `Deactivated` for orders.

## Conflict handling rule

If an open question is resolved in a way that conflicts with an approved decision, the conflict must be recorded before any affected decision is superseded.
