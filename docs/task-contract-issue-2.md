**Goal:** Ensure `POST /orders/{id}/cancel` refuses to cancel a `DELIVERED` order with HTTP 400.
**Context:** Issue #2, "Delivered orders can be cancelled." `cancel_order` currently only rejects already-cancelled orders, and the cancel route maps `OrderOwnershipError` to HTTP 400.
**In scope:** `app/modules/orders/service.py`, `app/modules/orders/routes.py`, and relevant order unit and integration tests.
**Out of scope:** `alembic/`, `.github/`, `pyproject.toml`, and any new dependency.
**Acceptance:**
- An authenticated request to cancel an owned `DELIVERED` order returns HTTP 400.
- The delivered order remains `DELIVERED` after the rejected request.
- Existing allowed order cancellations continue to work, and existing tests pass.
**Stop and ask a human if:** The requested behavior conflicts with established order-cancellation or invoice semantics, or a proposed change requires modifying an out-of-scope path.
**Reviewer:** Unassigned
