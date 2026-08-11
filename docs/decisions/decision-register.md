# Decision Register

This register is the canonical list of approved and superseded product decisions for B2B Platform.

## Status model

- `Approved` — authoritative decision.
- `Proposal` — working option, not authoritative.
- `Needs clarification` — unresolved and requires input.
- `Rejected` — explicitly rejected option.
- `Superseded` — replaced by a newer decision.

## Decisions

### DEC-001 — Warehouse is assigned to a trade point

- **Status:** Approved
- **Decision:** A warehouse is assigned to each trade point (ТТ), not to the customer as a whole.
- **Implication:** Warehouse-dependent catalog, stock and order checks must resolve the selected trade point first.

### DEC-002 — One trade point has one warehouse

- **Status:** Approved
- **Decision:** A trade point cannot have multiple fulfillment warehouses at the same time.
- **Implication:** Warehouse selection is not performed per line item or per order.

### DEC-003 — One order is fulfilled from one warehouse

- **Status:** Approved
- **Decision:** An order belongs to one trade point and therefore one warehouse.
- **Implication:** Multi-warehouse orders are out of scope for the current model.
- **Implementation note:** The order should persist the warehouse identifier used at creation time so a later reassignment of the trade point does not mutate historical orders.

### DEC-004 — Use available-to-order stock

- **Status:** Approved
- **Decision:** The stock value relevant to the customer is the quantity currently allowed to be ordered from the warehouse assigned to the selected trade point.
- **Open detail:** The exact calculation of available-to-order stock remains to be confirmed with the inventory/1C process owner.

### DEC-005 — Stock is shown for the selected trade point warehouse

- **Status:** Approved
- **Decision:** Stock displayed to the customer is sourced only from the warehouse assigned to the selected trade point.
- **Implication:** Stock from all three warehouses must not be aggregated for customer display under the current fulfillment model.

## Change rule

Approved decisions are never silently overwritten. If an approved decision changes:

1. create a new decision;
2. mark the old decision `Superseded`;
3. link the replacement decision;
4. record the reason and affected requirements/processes.
