# Online News Popularity Dataset

`EDA.ipynb` answers five exploratory questions and includes a Panel dashboard
comparing article shares by news category and weekday/weekend publication.
Keep `OnlineNewsPopularity.csv` in the same folder as the notebook.

## Setup (Windows PowerShell)

Open PowerShell in this project folder. Python 3.11 or newer is recommended.
Create a virtual environment and install the libraries:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

## Run the Notebook

```powershell
.\.venv\Scripts\python.exe -m jupyter lab EDA.ipynb
```

Choose the Python kernel from this environment and run the cells in order.
The commented installation cell is optional when dependencies are already installed.
`ml_models.ipynb` is the shared ML notebook. Its logistic regression
section includes a stratified train/test split, a preprocessing pipeline,
five-fold cross-validation, parameter selection, coefficient interpretation,
and test-set evaluation against a majority-class reference. Random Forest,
Histogram Gradient Boosting, and the final three-model comparison have empty
placeholders. Those sections must be completed to meet the full ML requirement.

```powershell
.\.venv\Scripts\python.exe -m jupyter lab ml_models.ipynb
```

## Run the Dashboard

```powershell
.\.venv\Scripts\python.exe -m panel serve EDA.ipynb --show
```

Keep the terminal running while using the dashboard; press Ctrl+C to stop it.
The controls restrict the category, publication-day group, and four article
characteristics. Plot types and the share-count outcome stay fixed.
Category medians use all matching articles; the scatter plot shows a reproducible
sample of at most 5,000 matching articles, with the matching count displayed.

Each tab's **Download HTML** button exports its current chart with Plotly included.
Open the downloaded file in a browser to use hover and zoom offline. It captures
the selected view; changing the Panel filters requires the running dashboard.

## P2 and P3 Coursework

`P2_categorical_interactive_transform.ipynb` includes a data-quality audit,
categorical plots, title-length groups created with `apply()`, an interactive
category/weekday heatmap, and a plan for joining verified publication metadata.

`P3_interactive.ipynb` includes all eight interactive-visualization questions,
a geographic feasibility check and choropleth plan, five example geocoding
queries, a Panel widget, a mini dashboard, HTML export, and a reflection.
The example cities are separate from the news data, which has no locations.

Open either notebook from JupyterLab and run its cells in order. To serve the P3
dashboard alongside the main EDA dashboard:

```powershell
.\.venv\Scripts\python.exe -m panel serve P3_interactive.ipynb --port 5007 --show
```

Keep `P3_geocoded_destinations.json` beside P3 to reuse its five cached geocoding
results. If that file is missing, Q5 makes five rate-limited Nominatim queries;
it needs an internet connection and caches only a complete successful result.
Geocoding data is from OpenStreetMap contributors / Nominatim; attribution and
service-policy links are included in the notebook.

## Repository Updates

For a new clone, configure the upstream class repository and your group's origin:

```powershell
git remote add upstream https://github.com/CS133-DataVisualization/CS133_Fa26_datafile.git
git remote set-url origin https://github.com/satam2/news-popularity-data-project.git
git remote -v
```

The output should list `origin` as the group's `news-popularity-data-project`
repository and `upstream` as the class's `CS133_Fa26_datafile` repository,
each with fetch and push entries.

To pull updates from the original repository: `git sync-upstream`.
Otherwise: `git pull origin main`.
