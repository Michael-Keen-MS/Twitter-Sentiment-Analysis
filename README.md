# Twitter Sentiment Analysis

Real-time Twitter sentiment analysis pipeline built during a hackathon at Comcast/Xfinity's Business Intelligence department to monitor live customer feedback on a newly launched product line.

## Overview

Two notebooks run simultaneously to form a streaming analytics pipeline:

1. **`TwitterScraper.ipynb`** — Connects to the Twitter streaming API, filters tweets matching specified search criteria, runs them through multiple sentiment analysis libraries, and writes results to a CSV file in real time.
2. **`TwitterScraper_VIZ.ipynb`** — Reads from the CSV as it updates and renders a live dashboard showing averaged sentiment scores across libraries alongside key engagement KPIs.

## Data Files

| File | Description |
|---|---|
| `tweets.csv` | Raw tweet stream output with sentiment scores per record |
| `tweets_chart.csv` | Aggregated KPI data consumed by the visualization notebook |

## How to Run

Run both notebooks simultaneously in separate Jupyter sessions:

```bash
# Terminal 1 — start the scraper
jupyter notebook TwitterScraper.ipynb

# Terminal 2 — start the live dashboard
jupyter notebook TwitterScraper_VIZ.ipynb
```

Update the search keyword or hashtag in `TwitterScraper.ipynb` to target any topic or product.

## Tech Stack
- Python 3
- `tweepy` — Twitter streaming API
- `textblob`, `vaderSentiment` — sentiment analysis
- `pandas` — data handling and CSV I/O
- `plotly`, `cufflinks` — real-time interactive dashboard
