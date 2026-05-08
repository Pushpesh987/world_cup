# 🏏 ICC Men's Cricket World Cup 2023 — Data Analysis

A comprehensive data analysis of the ICC Men's Cricket World Cup 2023, focused on extracting meaningful insights about player performances, stadium conditions, and match outcome patterns.

---

## 📌 Project Objective

Analyze the 2023 Cricket World Cup tournament data to answer key questions:

- Who were the **top performers** (batsmen & bowlers) in each match?
- Which **stadiums** favoured batting first vs bowling first?
- What **patterns** emerged in match outcomes based on team strategy?
- What **type of player** (batsman, bowler, all-rounder) has the most match impact?

---

## 📂 Datasets

| Dataset                        | Description                                    | Rows × Columns |
| :----------------------------- | :--------------------------------------------- | :-------------- |
| `match_schedule_results.csv` | Match-level facts — teams, venue, winner      | 48 × 7         |
| `batting_summary.csv`        | Every batsman's innings in every match         | 916 × 11       |
| `bowling_summary.csv`        | Every bowler's spell in every match            | 574 × 9        |
| `world_cup_players_info.csv` | Player profiles — role, batting/bowling style | 151 × 7        |

All datasets are located in the `dataset/` folder.

---

## 🔧 Methodology

### 1. Data Preparation

- **Data Loading & Inspection**: Loaded all 4 CSVs and inspected shapes, data types, and sample values.
- **Handling Missing Values**:
  - `Dismissal` (batting) — 2 missing values filled with `'not out'` (domain knowledge: no dismissal = not out).
  - `bowlingStyle` (players) — 6 missing values filled with `'Unknown'`.
  - `description` (players) — 17 missing values filled with placeholder text.
  - `image_of_player` (players) — 66 missing values filled with empty string.
- **Data Cleaning & Formatting**:
  - Converted `Strike_Rate` from string to numeric.
  - Standardised venue names (e.g., two different spellings for Dharamsala).
  - Stripped whitespace from all text columns.
  - Checked for duplicates (none found).
  - Merged `Venue` and `Winner` from match data into batting and bowling tables via `Match_no`.

### 2. Exploratory Data Analysis (EDA)

- **Best Scorer per Match** — Identified the top run-scorer in each of the 48 matches.
- **Best Bowler per Match** — Ranked bowlers by wickets (desc) and economy (asc) per match.
- **Stadium Analysis** — Calculated bat-first win percentage and average scores per venue.
- **Player of the Match (MoM) Analysis** — Analysed MoM distribution by player, role, team, and venue.
- **Match Outcome Patterns** — Examined how teams won (by runs vs by wickets).
- **Overall Team Performance** — Compared total wins, top scorers, and top wicket-takers.
- **Advanced Visualizations** — Strike rate distributions, top individual innings, top bowling figures, and venue-wise boundary analysis.

---

## 📊 Key Findings

| Category                              | Insight                                                                     |
| :------------------------------------ | :-------------------------------------------------------------------------- |
| **Most Consistent Scorer**      | Daryl Mitchell — best scorer in 3 matches                                  |
| **Most Consistent Bowler**      | Adam Zampa — best bowler in 5 matches                                      |
| **Best Bat-First Venue**        | Wankhede Stadium, Mumbai                                                    |
| **Best Bowl-First Venue**       | Ekana Cricket Stadium, Lucknow                                              |
| **Most MoM Awards**             | Travis Head & Mohammed Shami — 3 each                                      |
| **Most Impactful Player Role**  | All-rounders & Batsmen (~15 MoM each)                                       |
| **Australia's Winning Edge**    | All-rounders won 6 MoM awards; better at chasing (5 wins by wickets)        |
| **India's Strength**            | Batsmen won 5 MoM awards; perfectly balanced (5 wins by runs, 5 by wickets) |
| **Greatest Individual Innings** | Glenn Maxwell — 201* vs Afghanistan                                        |
| **Most Dominant Bowling Spell** | Mohammed Shami — multiple 5-wicket hauls                                   |

### Detailed Insights

- **Daryl Mitchell** (NZ) topped the scoring chart in 3 separate matches, highlighting his consistency across the tournament.
- **Adam Zampa** (AUS) was the best bowler in 5 matches — his leg-spin was the most consistently match-winning weapon.
- **Wankhede Stadium (Mumbai)** had the highest bat-first win percentage, while **Ekana Stadium (Lucknow)** favoured bowling first.
- **All-rounders and batsmen** each received ~15 MoM awards, showing that dual-skill players and dominant batsmen are equally match-winning.
- **Australia's all-rounders** (Head, Marsh, Maxwell) collectively won 6 MoM awards — their depth across roles was the key to winning the World Cup.
- **India** went unbeaten through the group stage (9-0) but lost the final. Their 5-5 split between wins by runs and by wickets showed perfect balance, but Australia's chasing ability proved decisive in the knockout stage.

---

## 🛠️ Tools & Technologies

| Tool                   | Purpose                                               |
| :--------------------- | :---------------------------------------------------- |
| **Python**       | Core programming language                             |
| **Pandas**       | Data loading, cleaning, manipulation, and aggregation |
| **Matplotlib**   | Static charts and visualizations                      |
| **Plotly**       | Interactive visualizations (hover, zoom, filter)      |
| **Google Colab** | Interactive notebook environment                      |

---

## 📁 Project Structure

```
world_cup/
├── dataset/
│   ├── match_schedule_results.csv
│   ├── batting_summary.csv
│   ├── bowling_summary.csv
│   └── world_cup_players_info.csv
├── world_cup_2023_analysis.ipynb    # Main analysis notebook
└── README.md                        # This file
```

---

## 🚀 How to Run

1. **Clone the repository** or download the project folder.
2. **Open** `world_cup_2023_analysis.ipynb` in [Google Colab](https://colab.research.google.com/) or Jupyter Notebook.
3. **Run all cells** sequentially — the notebook handles library installation, data loading, cleaning, and visualization.
4. All visualizations are **interactive** (Plotly-based) — hover over charts for detailed tooltips.

### Requirements

```
pandas
matplotlib
plotly
```
