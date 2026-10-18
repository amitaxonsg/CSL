# CSL AI Platform — MVP Demo Status (19 Oct 2026)

**Target:** https://csl.axon.com.sg — AXON GERMAN 161.97.137.234
**Scope:** Private, password-protected demonstration. Not production-ready.
**Repository:** amitaxonsg/CSL (public); **do not commit secrets/customer data**.

## Confirmed working by server/browser evidence
- HTTPS / Let's Encrypt issued, DNS resolves to target, website visible behind Basic Auth.
- Python CSL application as systemd service `csl.service`, non-root `csl` user, localhost-only `127.0.0.1:3040`.
- Private SQLite runtime database `/opt/csl/data/csl.db` with restricted permissions.
- Modern landing/marketing site with CSL logo and homepage hub entry points (user reports all working).
- Design Studio Pro loads with front/back sample jersey, color/text editor, logo upload, local project save and mockup exports.
- Marcus customer and staff/admin screen separation; HTTP 200 on their static pages and anonymous staff chat request returned HTTP 403.
- Groq GPT-OSS 20B works from Germany via compatible API headers; browser feedback confirms fast Marcus replies. Kimi remains available for manual fallback.
- CSL public product/fabrics/business knowledge curated for Marcus; NOT yet live NAS/Drive retrieval.
- Artwork Intelligence image-upload preview and processing page loads. Authenticated conversion backend uses VTracer; vector quality and full end-to-end import not yet verified for representative CSL production artwork.
- Artwork Bridge v2 installed according to user; both artwork and Studio pages return HTTP 200.

## Partially implemented / acceptance not confirmed
- Marcus Design Wizard v2 compatibility patch provided; installation success and end-to-end design handoff **not confirmed**.
- Customer order creation, proof approval, manual shipping/status and reorders exist in demo code; full authenticated end-to-end tests not yet confirmed.
- Artwork conversion to SVG may fail on complex photos/posters with 'Vector output too large'; simple-logo sample test required.
- Role separation has one negative anonymous test but needs positive staff/admin and cross-customer isolation tests.
- Chat speed improved, but structured response formatting and resilient timeout/error handling need further browser QA.
- New homepage's source running under `/opt/csl/staging`, outside git checkout; no verified deployment reproducibility.

## Pending / not installed
- ERPNext actual manufacturing, quotations, sales order and invoice synchronization.
- Synology Cloud Sync / Google Drive connectors and indexed staff RAG.
- n8n workflow automation and transactional email/SMS.
- Stripe or PH-supported payment provider checkout.
- AI-generated **new** image artwork from prompts (Groq handles text, not images).
- AI image editing / segmentation / accurate independent layer reconstruction and possible Phase 2 GPU.
- Factory-approved templates, vector print-preflight, CDR/AI validation, original-order historical import.
- Upload security hardening, admin bootstrap restriction, rate limits, API key isolation audit, CSP/SVG sanitization, backups and restore test.

## Alibaba image API blocker
Alibaba Model Studio / image API account enrollment requires account documents/identity verification before generating a key. **No API key has been issued**, and no hosted image-generation model is connected. Do not claim images can be created by the platform; Marcus wizard currently guides an editable jersey template. Resume after user completes verification and confirms model, region, pricing and quota.

## Presentation guidance
Demo only verified parts: website, fast Marcus business guidance, sample Design Studio editor and saved mockups, role-separated launch points. Label other screens 'Prototype / Pending integration'. Do not show fake ERP/Drive/payment/shipment integrations as active.
