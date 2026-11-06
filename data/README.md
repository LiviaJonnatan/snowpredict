# Data

- `data/raw/` contains all the JSON files from the API call for each `resort/point/year` and is gitignored.
- The parsed data (see below for details) is saved in `data/` and is gitignored. It can be built from running **section 1.3** in the notebook.

## Running without network (make an API call)

To run this notebook without making any API call, follow these steps:
1. Clone this repo
2. Download the zip folder from Google Drive
3. Unzip it into `data/raw`. Now you should have `data/raw/<resort_point_year>.json` files.
4. Run the notebook without hitting the API. The first few output you should see:

```
[ 22/462] Whistler Blackcomb/base: fetched 0, cached 22, failed 0
[ 44/462] Whistler Blackcomb/mid: fetched 0, cached 44, failed 0
...
Done. 0 fetched this run, 462 already cached, 0 failed and still needed.
Raw JSON on disk: 386.0 MB across 462 files
```
And now, check if you have `data/raw_manifest.csv`.

The files are huge and took multiple API calls to successfully get the data. So, ensure you downloaded the zip folder and put it in the right place.

# Parsing

The parse produce three tables, each derived from the previous one. You should see three files from running **section 1.3** in the notebook.

| File | Purpose |
| ----- | ----- |
| `data/weather_hourly_long.parquet` | hourly aggregate, re-aggregate later |
| `data/weather_daypart_long.parquet` | daypart-level |
| `data/weather_daily_wide.csv` | daily block + daypart summaries as columns |
| `data/ski_season_clean.csv` | Dec-Apr rows, 2006-2026 seasons with `split` and `ski_index`. Built in section 3 of MS2 notebook. |