# TX-34 Voting Procedures Dashboard

Built from `voting-dashboards-source` repo, district config `client/src/configs/tx-34.ts`.

## District profile
- **State**: Texas
- **Counties**: Cameron (Brownsville), Hidalgo (Edinburg), Willacy, Kenedy, Kleberg, Refugio, San Patricio, Aransas, Calhoun, Goliad, Jim Wells
- **2026 race**: Vicente Gonzalez Jr. (D, incumbent) vs **Eric Flores (R)** — explicitly NOT Mayra Flores (KRGV headline error documented as conflict).
- **Next key date**: Nov 3, 2026 (general)
- **Cook PVI / rating**: Likely D
- **Election admin**: Texas SOS

## Data inventory
- 13 sources verified (state SOS + county election offices + nonpartisan journalism)
- 12 rules — all `needsReview: true, confidence: "unconfirmed"` (verify before publish)
- 16 election events on timeline
- 9 voter resources
- 6 news cards (last 90 days)
- 3 updates panel entries (initial-build inventory)
- 1 conflict logged: KRGV headline named "Mayra Flores" as R nominee — contradicted by Ballotpedia, Fox News, FEC filings, all confirming Eric Flores. Logged as conf-tx34-001.

## Deploy to GitHub Pages

```bash
# In Apprentice101/tx34-dashboard repo:
git add .
git commit -m "Deploy TX-34 dashboard"
git push -u origin main
```

Enable GitHub Pages from main branch root in repo settings.

## Files
- `index.html` — entry point
- `snapshot.json` — district data (data layer)
- `assets/` — bundled JS/CSS

## QA status (2026-06-11)
- All rules and events marked `confidence: "unconfirmed"` — strict review required before public ship per user policy
- Zero console errors on smoke test
- Review Queue tile, district map, tab highlighting, Updates/Conflicts panels all rendering correctly (post-v2 fixes)

## Built from
- Source repo: https://github.com/Apprentice101/voting-dashboards-source
- Config file: `client/src/configs/tx-34.ts`
- Build command: `VITE_DISTRICT_ID=TX-34 npm run build:static`

## Title fix (2026-06-11 patch)
- Browser tab `<title>` now reads "TX-34 Voting Procedures Dashboard" (was generic/empty)
- `client/index.html` and `script/build-static.ts` updated so all future builds get the district title automatically
