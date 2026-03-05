# FRC Scouting Dashboard — AdamBots Edition

A lightweight, browser-based scouting dashboard for FIRST Robotics Competition (FRC) teams. Combines **Elo ratings**, **OPR (Offensive Power Rating)**, and **custom scouting data** into a unified tool for match predictions and team analysis.

## Features

- **Real-time Data**: Pulls live event data from The Blue Alliance (TBA) API
- **Team Rankings**: Sorted by Elo rating, OPR, and historical performance
- **Match Predictions**: Hybrid model blending Elo and OPR predictions with adjustable weighting
- **Scouting Integration**: Upload CSV scouting data to refine OPR predictions
- **Match Analysis**: View upcoming matches, predicted scores, and win percentages
- **Picklist Generator**: Ranked team recommendations based on composite scoring
- **Drive Coach View**: Quick reference for alliance partners and upcoming opponents
- **Local Caching**: All data cached in browser—works offline after first load
- **CSV Export**: Download predictions for record-keeping

## Getting Started

### Requirements
- A free TBA API key from [thebluealliance.com](https://www.thebluealliance.com)
- Any modern web browser (Chrome, Safari, Firefox, Edge)

### Local Setup

1. **Clone or download** the three files:
   - `index.html`
   - `app.js`
   - `style.css`

2. **Open in browser** → Double-click `index.html` or right-click → Open with Browser

3. **Enter your TBA API key** → Get one at [thebluealliance.com/account](https://www.thebluealliance.com/account)

4. **Enter event key** → e.g., `2026milak` (year + event code)

5. **Click "Load Event Data"** → App fetches teams, matches, and OPR

6. **Upload scouting CSV** (optional) → Refine predictions with your team's data

## How It Works

### Data Sources
- **TBA API**: Teams, matches, results, OPR
- **Elo Rating**: Calculated from match outcomes (starts at 1500)
- **Scouting CSV**: Custom team observations (upload your own data)

### Prediction Models
- **OPR-based**: Alliance scoring potential from official OPR
- **Elo-based**: Rating-based probability (accounts for match history)
- **Hybrid**: Blends OPR and Elo (adjustable via slider)
- **Scouting-adjusted**: Incorporates your team's scouting observations

### CSV Format (Optional)
Upload a CSV with these columns for best results:
```
event_key, team_key, match_key, contributedPoints, TeleopPoints, EndgamePoints, DidClimb, qDriverSkill, qScoringSkill, otherNotes
```

## Tabs Overview

| Tab | Purpose |
|-----|---------|
| **Teams** | View all teams ranked by Elo, with OPR and record |
| **Matches** | All event matches with lineups and scores |
| **Predictions** | Unplayed matches with win probability forecasts |
| **Picklist** | Ranked team recommendations (composite score) |
| **Coach** | Upcoming matches for your team with strategy tips |
| **Strategy** | Detailed alliance analysis and role recommendations |
| **Scouting** | Your team's scouting observations and averages |

## Deployment

### iPad
Copy files to iPad, open `index.html` in Safari. Add to Home Screen (Share → Add to Home Screen) for app-like experience.

## Settings

- **Elo K-Factor**: Adjust how quickly ratings change (default: 24)
- **Model Blend**: 0 = OPR only, 1 = Elo only (default: 0.5)
- **Scouting Weight**: How much to trust your scouting vs. OPR (0–60%, default: 20%)
- **Use Cached Data**: Toggle to use saved data or fetch fresh from TBA

## Tips

- **Save your API key** → "Save Key" button → stored locally
- **Clear cache** → If data looks stale, clear and reload
- **Export predictions** → CSV download for spreadsheets/analysis
- **Customize your home team** → Highlights your team in tables

## Technical Notes

- **Pure JavaScript**: No build tools, no backend required
- **Client-side only**: All processing happens in your browser
- **localStorage**: Caches API responses and settings locally
- **No tracking**: Your data stays on your device
- **Responsive**: Works on desktop, tablet, mobile

## File Structure

```
frc-scouting-dashboard/
├── index.html      # Main page structure
├── app.js          # All logic (fetch, predict, render)
├── style.css       # Styling (AdamBots theme)
└── README.md       # This file
```

## Troubleshooting

**"Missing TBA key" error** → Paste your API key and click "Save Key"

**No data loading** → Check event key format (e.g., `2026milak`)

**Predictions not updating** → Click "Update Predictions" after changing model settings

**CSV upload fails** → Ensure CSV has `event_key` column matching your event

## License & Attribution

Built with The Blue Alliance API. Themed for AdamBots FRC Team 245.

