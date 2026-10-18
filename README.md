# CSL AI Manufacturing Platform

**Demo target:** https://csl.axon.com.sg — AXON GERMAN server (161.97.137.234). Not Faith Develop.

## Confirmed
- Existing orders: Excel spreadsheets and NAS folders
- File server: Synology NAS
- Pilot: customer ordering/artwork approval/shipment tracking PLUS staff AI/document search
- Website: customsportsandleisure.com
- Live AI: Kimi API; image API optional (Qwen/Gemini)

## Scope and integration honesty
The existing locally packaged Python demo is not yet in this repository. The GitHub files here are deployment and integration specifications until the full app source is uploaded. ERPNext, Synology, Google Drive, courier APIs, email and SMS are **not connected**. Never demo synthetic data as real production records.

See `docs/DEPLOY_GERMAN.md`, `docs/INTEGRATIONS.md`, `docs/MIGRATION.md`, and `docs/ACCEPTANCE.md`.

## Security
This repository is public. Do not commit .env, Kimi/API credentials, actual customer orders/artwork, databases, NAS passwords, backups, or secrets. Confirm permissions, backups and HTTPS prior to any public demo.
