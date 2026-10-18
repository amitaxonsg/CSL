# MVP Release and Deployment Handover

## Live environment facts
- Host: AXON GERMAN 161.97.137.234 (never Faith Develop).
- Existing NGINX reverse-proxy for CSL-only vhost; do not touch other client vhosts.
- CSL application systemd service executes `/opt/csl/staging/server.py`, on 127.0.0.1:3040.
- Data is private at `/opt/csl/data`. Secrets under `/etc/csl` / CSL-only systemd drop-ins, NOT Git.
- Updates so far installed using incremental ZIP patches via WinSCP into /root and scripts under /opt/csl.
- Current Git checkout at `/opt/csl/app` contains documentation and configuration, **NOT the running application source**.

## Critical next maintenance task: commit the ACTUAL tested source
1. Create verified backup/snapshot of `/opt/csl/staging`, private data, and CSL vhost settings.
2. Copy ONLY vetted source files (`server.py`, `templates/`, `static/`, safe docs, requirements, source knowledge), not database/uploads/backups.
3. Review for embedded credentials, unpublished artwork and private content. Scrub if necessary.
4. Commit application source into a new Git branch/PR, run syntax and integration tests, then merge.
5. Change systemd to a versioned release path after testing; do not blindly point to Git checkout.
6. Record rollback plan, commit ID and verification results.

## Reproducibility / security blockers
- The public repo cannot be considered a complete clone-and-deploy build until sources and dependency installation are committed.
- Do not automatically enable public registration or bootstrap admin.
- Hosted image provider remains disconnected pending Alibaba verification.
- Avoid changes to global NGINX, MariaDB, Redis, Docker and other clients.
- No GPU needed for current API/demo features. Specialized local reconstruction in later phase may need GPU.
