# CSL Artwork Intelligence — Phase 1

Prepared build: CSL_Artwork_Intelligence_v1.zip. The ZIP contains artwork.html, artwork.js, artwork-worker.py, apply.py and README.md.

## Capabilities
Authenticated image upload (PNG/JPG, 2MB cap), basic image dimensions validation, VTracer raster-to-SVG conversion, original/vector comparison and SVG download.

## Deployment
App lives in /opt/csl/staging on AXON GERMAN (161.97.137.234). Existing NGINX, MariaDB, Redis, Docker apps and unrelated vhosts must not be modified.
1. Inspect and test runtime/venv dependencies.
2. Back up server.py.
3. Install isolated Python VTracer/Pillow worker in /opt/csl/artwork-venv.
4. Apply release installer, validate syntax.
5. Restart only csl.service, test /static/artwork.html and authenticated conversion.
6. Keep demo behind password protection.

## Limitations
This is **real vector tracing, not AI reconstruction of original layers**. SVG output needs CorelDRAW / Illustrator and CSL production review. The Add-to-Studio button currently stages artwork in localStorage; direct insertion into Studio Pro is pending. Advanced reconstruction, GPU models, image-generating APIs, ERPNext and NAS are NOT connected.
No confidential customer artwork or API keys belong in this public repo.

## Git state
Documentation committed. The original full app release source, and this standalone artwork ZIP, must still be committed into a tested application branch after verification. Do not confuse documentation-only Git with a runnable deployment.
