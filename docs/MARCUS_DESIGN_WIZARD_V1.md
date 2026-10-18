# CSL Create with Marcus AI — Wizard v1

Delivery archive: CSL_Marcus_Design_Wizard_v1.zip (download in the corresponding ChatGPT conversation).

## Working demo
- Customer enters apparel description, selects product, team, quantity, colors and fabric preference.
- “Ask Marcus for guidance” calls existing authenticated/customer Groq-backed /api/chat; text advice only.
- “Create editable jersey” transfers deterministic product choices to Studio Pro via sessionStorage and opens /static/studio-pro.html?from=marcus.
- Studio Pro applies color, name, number, quantity and project title to its existing editable SVG jersey.
- User may then upload artwork, export mockups and submit a quote via the existing order endpoint.
- Image generation is **NOT** included; Groq text API does not create images. Optional Qwen/Gemini image API is a separate future phase.

## Installation
Upload ZIP to AXON GERMAN /root, extract to /opt/csl/marcus-wizard and run install.py. Patch modifies only /opt/csl/staging/static/studio-pro.js and studio-pro.html and adds marcus-design.html/js. No NGINX/systemd restart. Backups made automatically.

## Important status
This document is committed to Git; the runnable application code and release ZIP remain separate until the full tested server source is synchronized. Do not claim repo itself is deployable. Do not commit customer artwork, secrets or database.
