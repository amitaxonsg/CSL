# German deployment runbook

**Target only AXON GERMAN 161.97.137.234**. Never Faith Develop 147.93.173.184. Never install NGINX or change unrelated sites.

Before running anything:
1. Check OS, memory, disk, existing web server, Python, Docker, ports, DNS and firewall **read-only**.
2. Snapshot and establish rollback plan; verify free RAM/disk before choosing ERPNext hosting.
3. Confirm csl.axon.com.sg DNS and HTTPS route.
4. Deploy full application source (not only these documents) to isolated service directory and dedicated non-root user.
5. Create private .env with strong session secret and Kimi key. Bind app to loopback only; reverse proxy using **existing** web server.
6. Provision demo users via secure one-time admin mechanism; remove default passwords; set rate limits, secure cookies, CSRF, upload checks and role permissions.
7. Test user isolation, save/restore design revisions, order updates and shipment fields.
8. Configure backups, logging, monitoring and HTTPS; test restore before client data.
9. Rollback stops only CSL service and CSL-specific vhost; never restart unrelated production applications.

## Open-source installations
ERPNext: separate isolated stack (MariaDB, Redis, workers, scheduler), ideally separate VM if shared host cannot safely support it. Evaluate official Frappe Docker deployment and pinned versions. Do not install globally.
VTracer/Inkscape: dedicated file-processing worker with resource limits.
n8n: optional service only if licensing, isolation and worker capacity checked.
RAG index: PostgreSQL pgvector or Qdrant; index only approved material, preserve ACLs.
Synology Cloud Sync is installed on NAS, NOT on German VPS. Google Drive connection requires authorized service and tenant permissions.
No installation on the German server has occurred.