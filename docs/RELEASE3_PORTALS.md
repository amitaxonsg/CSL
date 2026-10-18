# CSL Release 3 — Separated Marcus and Administration

## Deliverables
- Customer Marcus: /static/customer-marcus.html
- Staff Marcus: /static/staff-marcus.html (staff/admin account required, API verifies channel permissions)
- Admin Console: /static/csl-admin.html (admin-only display; protected APIs)
- Artwork roadmap and AI API estimates in administrator console

## Operational constraints
The tested application is still deployed from /opt/csl/staging on AXON GERMAN (161.97.137.234). Do not change global NGINX, Docker or other site services.
The downloadable CSL_Portal_Separation_v3.zip supplies the installer and portal pages; documentation commit DOES NOT install that code automatically. Deploy the ZIP and test first, then commit the verified full source.
Existing private API credentials remain in /etc/csl and never belong in Git.
Do not expose unrestricted admin setup or production data. Keep outer demo HTTP Basic Authentication until security audit completion.

## AI cost references (Oct 2026)
Qwen Image 2.0 approximately USD 0.035/output; Qwen Image Edit Plus USD 0.03/output in Singapore; Qwen Image Layered via fal.ai USD 0.05/output; verify before invoicing. Groq free tier subject to rate caps.
Image layer reconstruction remains experimental. Phase 2 could require a GPU if CSL chooses local specialized models; hosted APIs do not need a local GPU.

## Pending services
ERPNext, Google Drive/Synology indexed search, VTracer processing, Qwen image generator, payments and SMS are NOT installed.
