# DALTOOL v132 — isolated test

This branch is an isolated preparation area. The current production DALTOOL site does **not** reference this branch and is not changed by these files.

## Goal
Move only embedded product/technical images out of Google Apps Script while preserving Google Sheets, Code.gs business logic, cart, filters, search, orders, and current production deployment.

## Safety rules
1. Do not change the current production deployment while this branch is being tested.
2. Keep `Code_v131.gs + Index_v130.html` as rollback baseline.
3. Upload externalized image assets under `/assets/` and verify every direct URL.
4. Test v132 in a separate Apps Script copy/deployment first.
5. Promote only after desktop + mobile smoke tests pass.

## v132 analysis
- 55 embedded image occurrences found across the current files.
- 48 unique embedded images.
- All 48 extracted image files validate successfully.
- Test build shrinks `Index` from about 1.5 MB to about 272 KB.
- Test build shrinks `Code.gs` from about 480 KB to about 172 KB.
- No Google Sheet schema, stock logic, cart logic, or order logic is intentionally changed in this step.

The production site remains independent from GitHub until an explicitly tested production switch is made.