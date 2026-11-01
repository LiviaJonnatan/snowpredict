# Data

- `data/raw/` contains all the JSON files from the API call for each `resort/point/year` and is gitignored.
- The parsed data (see below for details) is saved in `data/` and is gitignored. It can be built from running the notebook.

## Running without network (make an API call)

To run this notebook without making any API call, follow these steps:
1. Clone this repo
2. Download the zip folder from Google Drive
3. Unzip it into `data/raw`
4. Run the notebook without hitting the API

# Parsing

The parse produce three tables, each derived from the previous one.

| File | One row = | Purpose |
| ----- | ----- | ----- |
| `data/weather_hourly_long.parquet` | resort, point, hour (+ daypart label) | hourly aggregate, re-aggregate later |
| `data/weather_daypart_long.parquet` | resort, point, date, daypart | daypart-level |
| `data/weather_daily_wide.csv` | resort, point, date | daily block + daypart summaries as columns |