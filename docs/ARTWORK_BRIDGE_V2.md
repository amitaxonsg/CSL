# CSL Artwork Intelligence → Studio Pro Bridge v2

Prepared deliverable: CSL_Artwork_Bridge_v2.zip. Deploy only after confirming working Artwork v1 and Studio Pro v1 on AXON GERMAN.

- Fix PNG/JPG preview using FileReader data URL, image-load/error handling, actual dimensions, 2 MB/6MP limits.
- After VTracer conversion, show SVG preview and download.
- Add to Studio Pro transfers sanitized SVG to the existing movable logo artwork layer using same-origin localStorage, then navigates to Studio Pro.
- Add a direct Artwork Intelligence launch button inside Studio Pro.
- SVG imported as **one** scalable artwork object, NOT recovered original independent layers; CSL production review still required.
- Existing session required for backend vectorization; client-side demo link is not permanent project storage.
- The script changes only /opt/csl/staging/static/{artwork.js,studio-pro.js,studio-pro.html}, making timestamped backups. No system-wide or other-client changes.
- Before public use: sanitize rendered and stored SVG server-side, implement durable private asset records, robust tenant permissions, rate limits, and end-to-end user tests.
- Runtime deployment remains distinct from this Git documentation commit; full running app is not yet synchronized.
