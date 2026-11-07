# SnowPredict: Can machine learning predict the best time for a ski vacation?

|Milestone | Details | Due Date |
|--------|--------|--------|
| MS 1 | Project preferences (5 topics) as a group of 3-5 students | Oct 16, 2026 |
| MS 2 | Data wrangling and project redefinition | Nov 13, 2026 |
| MS 3 | EDA, Initial Modeling, and Pipeline Development | Nov 30, 2026 |
| MS 4 | Final Modeling and Deliverables | Dec 10, 2026 |

For each milestone, groups will present their progress in a 10-minute presentation (with slides) to their assigned project TF.

> *Further each milestone details below.*

## Proposal

Data source: https://open-meteo.com/

Problem Question:
- For any date in the ski season (Dec 1 - Apr 30), how well can the model trained on earlier winter sessions (historical data from 2006) predict ski-condition index 30 days ahead in Canadian ski resorts? Which variables are the main driver (snow depth, fresh snowfall, rain, etc.)? Is our model better than just using the historical day-of-season average?

> *Full revised proposal is in the Google Drive.*

## Repository Structure
```
snowpredict/
├── README.md ← this file: project overview and milestones
├── MS2.ipynb ← Milestone 2: get, parse, clean and explore the data
├── data/
│ ├── README.md ← how to get the data without calling the API
│ ├── raw/ ← 462 raw JSON responses, one per resort/point/year (gitignored, ~390 MB)
│ ├── raw_manifest.csv ← what was downloaded, when, and file sizes (gitignored)
│ ├── weather_hourly_long.parquet ← one row per resort, point, hour (gitignored)
│ ├── weather_daypart_long.parquet ← one row per resort, point, date, daypart (gitignored)
│ ├── weather_daily_wide.csv ← one row per resort, point, date; feature table (gitignored)
│ └── ski_season_clean.csv ← Dec–Apr rows only, with season, split and ski index (gitignored)
├── pyproject.toml ← project metadata and dependencies (uv)
├── requirements.txt ← same dependencies for pip users
└── uv.lock
```

## Milestone Details
### Milestone 2: Data Wrangling and Project Redefinition
In this milestone your group gets the data, loads it, cleans it and learns what it contains, and then uses what it learned to state the project question precisely. By the end, your group should have a usable table in a Jupyter notebook and a project question that the data can answer. Exploratory data analysis and a baseline model come in Milestone 3, so the focus here is the data itself.

**Deliverables:**
- A 10 minute presentation to your project TF, followed by about 10 minutes of questions and discussion. Plan for 25 minutes in total.
- The slides from your presentation, as a PDF.
- The Jupyter notebook (.ipynb) that you used to get, load and clean the data.
- A revised proposal of one to two pages, as a PDF.

### Milestone 3: EDA, Initial Modeling, and Pipeline Development 
Following the verification and cleaning of the data, groups will engage in a well-motivated Exploratory Data Analysis (EDA). The objective is to interpret the EDA findings and use them to refine and solidify the project goals. This stage will also involve creating a clear navigation plan for the project's next steps. Groups will also establish an initial, straightforward model, referred to as the baseline model. This model serves as a benchmark for measuring progress in subsequent iterations. Additionally, students will propose a comprehensive pipeline for model training and testing. The pipeline encompasses data preprocessing, model implementation, and the evaluation of model outputs using a well-considered set of metrics. This preparation lays the foundation for more advanced model iterations.

### Milestone 4: Final Modeling and Deliverables
In this concluding milestone, project groups will wrap up the modeling tasks. They will interpret their findings in context and highlight the limitations of their approach. To present their work comprehensively, students will (1) write-up their modeling results and process in a 2000-2500 word final report, (2) create a concise 6-minute video presentation to showcase their final deliverables, and (3) submit their well-organized and commented code in a python notebook.
