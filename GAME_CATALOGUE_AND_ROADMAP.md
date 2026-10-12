# Aakalan — Game Catalogue and Fast-Track MVP Plan

## Product decision
Build one unified, bilingual (English/Hindi) learning-and-strategy platform, not separate apps. Each game is a module with a scenario, decision inputs, an outcome model, a debrief, progression and a repeatable next round.

## 12 game arenas
1. Management Simulator — pricing, production, staffing, quality, cash flow.
2. Marketing Lab — segmentation, channels, offers, campaign budget, conversion and ROI.
3. Finance & Trading — virtual stocks, indices, commodities, defensive assets, cash, risk and portfolio return.
4. Academic Challenge Arena — topic mastery, revision strategy, quizzes, case-based learning and exam preparation.
5. Strategy & Decision Lab — competition, resource allocation, strategic trade-offs and adaptive planning.
6. Economics & Public Policy — inflation, employment, taxation, incentives and distributional consequences.
7. Supply Chain & Operations — procurement, inventory buffers, reliability, delivery and working capital.
8. Project Management — schedule, scope, cost, quality, team capacity and project risk.
9. Negotiation & Leadership — interests, bargaining, trust, value creation and durable agreements.
10. Sustainability & Climate — transition investment, energy, waste, resilience and measurable impact.
11. Entrepreneurship Studio — customer discovery, product-market fit, experiments, unit economics and runway.
12. Critical Thinking & Research — evidence quality, source diversity, assumptions, counterarguments and conclusions.

## Fast-track build sequence
### Track A — Immediate (prototype)
- Responsive catalogue with searchable game modules.
- Decision forms and explainable outcome cards.
- Local demo progress, XP, sample achievements and downloadable report.
- English/Hindi toggle and mobile layout.
- All finance activity uses virtual money.

### Track B — Production MVP
- Create a separate repository and deployment, not connected to Gyan Vardhan.
- Set up authentication and a persistent player profile.
- Add server-authoritative round submissions, scoring, XP and leaderboard aggregation.
- Add scenario versions and audit records.
- Add privacy-aware account deletion and export.
- Add automated service health checks, quota warnings and graceful degraded mode.
- Launch without payments; reserve premium entitlements as a future capability.

### Track C — Data and quality
- Integrate a permitted delayed/historical market-data source only after validating licence, attribution and rate limits.
- Clearly label source, timestamp and simulated components.
- Validate finance calculations with deterministic test cases; keep random scenario shocks reproducible during tests.
- Add accessible keyboard navigation, responsive testing and full Hindi localisation.
- Test cross-user isolation, abuse resistance, duplicate submissions, reconnects and quota failures.

## Production architecture principles
- Browser: UI and input only; never trusted for scores, XP, premium entitlements, rankings or certificate issuance.
- Server: validates each decision, computes outcomes, stores results, awards badges and generates verifiable certificates.
- Database: users, game sessions, decisions, results, scenario versions, achievements, leaderboard snapshots and audit events.
- Admin: role is assigned and checked server-side; never accept admin status from a browser field.
- Reliability: static informational pages remain available when the database is unavailable; dynamic actions show a clear degraded-mode message and retry safely.
- Privacy: collect minimal user information; provide export and deletion paths.
- Security: secrets only in provider secret settings; never commit keys or credentials.

## ₹0 budget rules
- Use only verified free tiers and open-source libraries.
- No paid APIs, SMS OTP, payment gateway or real-money trading.
- Do not activate any provider billing plan without explicit user approval.
- Free-tier quotas and policies may change; monitor limits and degrade gracefully instead of promising unlimited free usage.

## Current deliverable status
The downloadable v2 ZIP contains the updated front-end prototype and starter configuration. It is not yet a production service. Real authentication, shared database, trusted server logic, certificates, delayed market data and public deployment are still outstanding.
