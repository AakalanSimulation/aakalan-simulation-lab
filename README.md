# Aakalan Simulation Lab — MVP starter

## What is included
- Premium, responsive single-page demo with 12 game arenas: Management, Marketing, Finance & Trading, Academic Challenges, Strategy, Economics & Public Policy, Supply Chain, Project Management, Negotiation & Leadership, Sustainability & Climate, Entrepreneurship, and Critical Thinking.
- Decision-round interface and a virtual-clock mode selector (clock advancement is manual in this MVP); search/filter for the game catalogue.
- English/Hindi UI toggle; some game-specific copy and detailed controls still need full translation QA before calling the entire interface fully bilingual.
- Local demo profile, XP, badges, sample leaderboard, scenario prompts, and JSON learning-report download.
- No payments, no real-money orders, and no external market-data calls.

## Deployment preparation

- `.github/workflows/pages.yml` is included for automated GitHub Pages deployment from the `main` branch.
- Follow `DEPLOY_TO_GITHUB.md` to create a **new, separate** repository and enable GitHub Actions Pages.
- The deployment workflow does not configure a backend and does not mean the site is already published.

## Run locally (no coding tools required)
1. Download and extract `aakalan_simulation_lab_github_ready.zip`.
2. Open `index.html` in Chrome, Edge, or Firefox.
3. Choose a game and make decisions. Progress is stored in that browser only.
4. Use “Download my report” to export a JSON summary.

## Current status — important
This is a **working front-end prototype**, not a production multi-user service.
- Login is a local nickname prompt only; real authentication is not configured.
- Progress and leaderboard are stored only in the browser; users on other devices cannot see them.
- Game calculations are illustrative client-side formulas. They are not secure against tampering.
- Finance mode uses random illustrative changes, not current, historical or delayed exchange prices.
- Certificates are not yet cryptographically verifiable.
- Admin monitoring, server-authoritative scoring, shared rankings, automated email, and a real premium entitlement service are not connected.
- No Firebase project settings, credentials, or secrets are included.

## Recommended zero-cost architecture for the production phase
Respecting the requirement to keep this separate from Gyan Vardhan:
- New, separate Firebase Hosting site.
- Firebase Authentication with email/password (no paid SMS OTP).
- Firestore in a new project or isolated database, with strict rules and usage alerts.
- Existing Google Drive may be used for owner-managed exports/backups if desired; avoid Apps Script/Sheets and Firebase Storage.
- Keep private answer keys, scoring, entitlements, leaderboard aggregation, and certificate issuance server-authoritative. Because Firebase Cloud Functions commonly require the Blaze billing plan, verify current Firebase terms before selecting it. Do not enable billing without explicit approval.
- For a strictly ₹0 launch, start with local prototype and then evaluate a free-tier backend that can enforce server-side game rules. Free tiers and quotas can change; no provider guarantees unlimited free usage.
- Market data: use a legally permitted free historical/delayed data source only after verifying its API terms and limits. Until then, clearly label prices as simulated.

## Production readiness checklist
- [ ] Create a new project/site with a name distinct from Gyan Vardhan.
- [ ] Set up email/password authentication and account recovery.
- [ ] Define and test Firestore data model and security rules.
- [ ] Move simulation scoring, XP, leaderboard updates and certificate issuance to trusted server logic.
- [ ] Add server-side rate limits, idempotent round submissions, audit logs and data export.
- [ ] Add real delayed-data provider and display source/timestamp/licence.
- [ ] Add admin-only role controls; never trust a role supplied by the browser.
- [ ] Test mobile, accessibility, Hindi text, persistence, abuse resistance and quota failure.
- [ ] Deploy and verify public URL and health checks.

## Data and safety
This platform is educational. Virtual returns do not predict actual outcomes. Do not enter real passwords or sensitive personal data into the local prototype.
