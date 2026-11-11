# PocketPlan — Offline-first MVP

PocketPlan is a mobile-first personal money and shopping planner.


## Project structure
- `index.html` — page structure and content.
- `css/style.css` — all visual styling and responsive layouts.
- `js/app.js` — application logic and delegated interactions.
- `sw.js` — offline app-shell caching; the cache version is updated with this release.

Keep future CSS in `css/style.css` and JavaScript in `js/app.js` (or dedicated files under those folders). Do not add inline `<style>` / `<script>` blocks, `style` attributes, or inline event handlers to HTML or generated markup.

## Included
- Appearance settings with Light / Dark / System choices; system mode follows device appearance changes.
- Automatic allocation of each income using editable percentage rules.
- Five default buckets: Essentials 55%, Guilt-Free Spending 5%, Debt/Investment 10%, Short-Term Savings 15%, Long-Term Investment 15%.
- Existing balances carry forward; new income adds to them. Editing rules affects future income only.
- Priority Memory list for needs/tasks captured before money arrives.
- Shopping list with estimated and actual prices; recording a purchase updates the selected bucket.
- Manual payment tracking, separate debt/investment/savings transaction types.
- Short-term savings goals.
- Primary-currency selection with 40+ currencies and locale-aware amount formatting. Currency changes are locked after financial records exist; no silent exchange conversion is performed.
- First-run guided tutorial that highlights real app controls and lets users practise with temporary demo records. Skip/X exits are always available, and demo data is discarded at the end.
- Light, dark, and system appearance choices in Settings; the first launch follows the device appearance, and the selected preference is saved separately from financial data.
- Clear distinction between virtual planning balances and actual money: this version does not accept deposits, hold funds, connect bank accounts, or execute transfers/payments.
- Local browser persistence, JSON export/import backup, and installable PWA service worker for offline use after the first successful load.

## Run locally
Open `index.html` in a browser for the core app. Browser service-worker offline installation works when served from HTTPS or localhost, not from a `file://` URL.

## Deploy
Upload the contents of this folder to a static host such as Netlify. Open the deployed HTTPS URL once while online. The service worker caches the app shell; subsequent visits can work offline. On supported mobile browsers, use the browser menu's “Install app” / “Add to Home Screen”.

## Important data note
This MVP stores records in localStorage on the current browser/device. It does not sync between devices and cannot restore data if browser storage is cleared. Use Export backup regularly and store the JSON file somewhere safe.

## Before real-world release
Test currency formatting/rounding, guided tutorial completion and skip paths, offline install/update behavior on target phones, data export/import, and edge cases. This is a functional MVP, not financial advice or a secure cloud-backed accounting system. The displayed buckets are budgeting records only, not bank accounts or real-money pots. A future real-money feature requires a suitable licensed financial partner, legal/compliance review, secure server-side integration, transaction reconciliation and explicit user consent.
