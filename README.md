# Player Match Stats Scraper

A Python web scraper that collects a football player's match-by-match statistics and saves them as a clean CSV file for analysis.

## What it does

- Scrapes each match row from the player's stats page
- Extracts competition, date, opponent, result, and the player's individual stats
- Fills missing values with `NaN` so every column stays the same length
- Exports the final table to a csv file

## Data collected

| Column | Description |
|---|---|
| competition | League or tournament name |
| date | Match date |
| opponent_team | Opposing team |
| status | Result (win/draw/loss) |
| scoreline | Final score |
| own_team | Team the player played for |
| minutes_played | Minutes on the pitch |
| position | Position played |
| goals | Goals scored |
| assists | Assists made |
| yellow_cards | Yellow cards received |
| red_cards | Red cards received |
| rating | Match rating |

## Tech stack

- Python 3
- BeautifulSoup (`bs4`)
- requests
- pandas
- numpy
- re (regular expressions)

## Installation

```bash
git clone https://github.com/YOUR_USERNAME/player-stats-scraper.git
cd player-stats-scraper
pip install -r requirements.txt
```

## Usage

1. Open the script/notebook and set the player page URL.
2. Run all cells (or `python scraper.py`).
3. The output is saved as `player_stats.csv`.

## How it works

1. The page HTML is fetched and parsed with BeautifulSoup.
2. Each match row is located using partial class matching (`re.compile`), because the site's CSS class names contain hashed parts that change over time.
3. Every field is wrapped in `try/except`, and `np.nan` is appended on failure.
4. All lists are combined into a pandas DataFrame and exported to CSV.

## Dataset

The cleaned dataset is available on Kaggle: [add your Kaggle link here]

## Disclaimer

This project is for educational purposes. Data belongs to its original source. Check the website's Terms of Service and robots.txt before scraping or republishing the data.

## Author

LakheDai
