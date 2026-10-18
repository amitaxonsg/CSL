# CSL technical blueprint

## Modules
Customer: login/company users, design studio, uploads, quotation/order submit, review proof, approve exact version, production timeline, shipping, reorders.
Staff: inbox, customer records, artwork revisions, manufacturing milestones, shipment updates, Kimi agent.
Admin: users/roles, product catalogue, AI API settings, integration health, audit logs.
ERPNext: Customer, Item, Quotation, Sales Order, Work Order, Delivery Note and Sales Invoice mapped by immutable external IDs.

## Status workflow
Draft -> Submitted -> Quoted -> Proof pending -> Changes requested or Approved -> Scheduled -> In production -> QC -> Packing -> Partially shipped or Shipped -> Delivered -> Closed. Exceptions: On hold, delayed, cancelled.
Timeline event: actor ID, timestamp, status, notes, optional attachments. Estimated date must be marked as an estimate.

## Shipping
Order has multiple shipments, each with packages, carrier, tracking number, tracking URL, ETA, dispatch date, delivered date, proof of delivery and quantities. Supports partial shipment. Tracking data manually entered until verified courier connector.

## Files and search
Synology NAS is source; stage read-only pilot folder and approved Google Shared Drive synchronization. Search index stores ACLs and document provenance. Customer can only read their own organization's artifacts; staff can read only authorized departments.

## AI
Kimi server-side key only. Retrieval augmented answers cite actual source. AI actions use explicit authorized tools and confirmation before email, edits, approval or status updates. Qwen/Gemini image API optional; output is a concept only, never automatically print-ready.

## Notifications
Configurable later: email via SMTP/API, SMS via provider API. Use durable outbox, retries, opt-in and logs. Disable when provider unconfigured.

## Important pending
No active ERPNext/NAS/Drive/SMS/courier integration or production import currently deployed.