# NBA Offseason Hub

> Annual NBA offseason analysis — salary tables, draft capital, areas for improvement, and road maps for all 30 teams.

**Live site:** `https://EthanRadecki.github.io/nba-offseason-hub`

---

## Repo structure

```
nba-offseason-hub/
│
├── index.html          ← the full app (single file)
│
├── data/
│   ├── teams.js        ← optional inline data (leave empty, use JSON files instead)
│   ├── new-york-knicks.json
│   ├── boston-celtics.json
│   └── ... (one JSON per team, named by slug)
│
└── logos/
    ├── new-york-knicks.png
    ├── boston-celtics.png
    └── ... (PNG logos, named by slug)
```

---

## Team slugs (filename format)

| Team | Slug |
|------|------|
| Atlanta Hawks | `atlanta-hawks` |
| Boston Celtics | `boston-celtics` |
| Brooklyn Nets | `brooklyn-nets` |
| Charlotte Hornets | `charlotte-hornets` |
| Chicago Bulls | `chicago-bulls` |
| Cleveland Cavaliers | `cleveland-cavaliers` |
| Dallas Mavericks | `dallas-mavericks` |
| Denver Nuggets | `denver-nuggets` |
| Detroit Pistons | `detroit-pistons` |
| Golden State Warriors | `golden-state-warriors` |
| Houston Rockets | `houston-rockets` |
| Indiana Pacers | `indiana-pacers` |
| Los Angeles Clippers | `los-angeles-clippers` |
| Los Angeles Lakers | `los-angeles-lakers` |
| Memphis Grizzlies | `memphis-grizzlies` |
| Miami Heat | `miami-heat` |
| Milwaukee Bucks | `milwaukee-bucks` |
| Minnesota Timberwolves | `minnesota-timberwolves` |
| New Orleans Pelicans | `new-orleans-pelicans` |
| New York Knicks | `new-york-knicks` |
| Oklahoma City Thunder | `oklahoma-city-thunder` |
| Orlando Magic | `orlando-magic` |
| Philadelphia 76ers | `philadelphia-76ers` |
| Phoenix Suns | `phoenix-suns` |
| Portland Trail Blazers | `portland-trail-blazers` |
| Sacramento Kings | `sacramento-kings` |
| San Antonio Spurs | `san-antonio-spurs` |
| Toronto Raptors | `toronto-raptors` |
| Utah Jazz | `utah-jazz` |
| Washington Wizards | `washington-wizards` |

---

## Adding a team

1. Copy `data/new-york-knicks.json` and rename it to the team's slug (e.g. `data/boston-celtics.json`)
2. Fill in all the fields with real data
3. Drop the team logo PNG into `logos/` named with the same slug (e.g. `logos/boston-celtics.png`)
4. Commit and push — GitHub Pages auto-deploys within ~30 seconds

---

## Data sources

| Data | Source |
|------|--------|
| Ratings (ORtg, DRtg, NRtg) | [Basketball Reference](https://www.basketball-reference.com) |
| Salary & contracts | [Spotrac](https://www.spotrac.com) |
| Backup salary data | [HoopsHype](https://hoopshype.com/salaries) |
| Draft capital & pick ownership | [Tankathon](https://www.tankathon.com/picks) |

---

## JSON schema reference

```jsonc
{
  "team": "Team Name",
  "record": "51 - 31",

  // Ratings
  "offRating": 118.42,
  "offRatingRank": "5th",
  "defRating": 114.34,
  "defRatingRank": "13th",
  "netRating": 4.09,
  "netRatingRank": "8th",

  // Salary table — last row should be Totals
  // flag: null | "player" (player option) | "team" (team option)
  "salaryTable": [
    { "name": "Player Name", "y1": "$25,000,000", "y2": "$27,000,000", "y3": null, "flag": "player" }
  ],

  // Free agents
  "restrictedFA": ["Player Name"],
  "unrestrictedFA": [
    { "name": "Player Name", "bird": true, "nonBird": false }
  ],

  // Draft picks
  "draftCapital": [
    { "year": "2026", "round": "1st", "via": "Own", "protection": "None" }
  ],

  // Areas for improvement — rank is out of 30 (30 = worst)
  "areasForImprovement": [
    { "area": "Defensive Rating", "rank": 13, "label": "13th in the league" }
  ],
  "improvementNarrative": "HTML string with your analysis.",

  // Road map — type: signing | trade | draft | extension | waive
  "roadmapMoves": [
    { "type": "signing", "description": "Move description.", "note": "Optional context." }
  ],
  "roadmapNarrative": "HTML string with your overall narrative."
}
```
