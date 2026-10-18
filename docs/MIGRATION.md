# Migration from Excel + Synology NAS

1. Gather 10–20 anonymized orders, an example Excel workbook, NAS directory listing and 3 original editable artwork files.
2. Map customer IDs, original order number, date, product, sizes, quantities, proof revision, fabric, delivery notes and file paths.
3. Detect duplicate references and mismatched artwork; hold ambiguous records for manual approval.
4. Preserve original NAS files read-only; hash imported files; never overwrite source.
5. Batch import validated rows to staging before ERPNext, with reconciliation totals and rejection reports.
6. Index text and supported art previews in a separate background process, preserving customer/department permissions.
7. Test a pilot of 20–50 records and verify customer logins cannot access another customer's data.
8. Enable Synology snapshots plus independent backup: two-way sync is not backup.
9. Add customer acceptance sign-off and retained copy of source records before larger migration.