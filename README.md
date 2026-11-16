# Online News Popularity Dataset

`P2_EDA_questions.ipynb` contains the data exploration and five project questions.
`P3_interactive.ipynb` contains the interactive exercises and Panel dashboard.
Keep `OnlineNewsPopularity.csv` in the same folder as the notebooks.

## Setup (Windows PowerShell)

Open PowerShell in this project folder. Python 3.11 or newer is recommended.
Create a virtual environment and install the libraries:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

## Run the Notebook

```powershell
.\.venv\Scripts\python.exe -m jupyter lab P2_EDA_questions.ipynb
```

Choose the Python kernel from this environment and run the cells in order.
Dependencies are listed in `requirements.txt`.
`ml_models.ipynb` is the shared ML notebook. Its logistic regression
section includes a stratified train/test split, a preprocessing pipeline,
five-fold cross-validation, parameter selection, coefficient interpretation,
and test-set evaluation against a majority-class reference. The Histogram Gradient
Boosting section uses the same features, split, folds, and metrics, with a small
parameter search, early stopping, and test-set evaluation. A preliminary table
compares the two completed model types using cross-validation. Random Forest and
the final three-model comparison remain empty placeholders; those sections must
be completed to meet the full ML requirement.

```powershell
.\.venv\Scripts\python.exe -m jupyter lab ml_models.ipynb
```

## Run the Dashboard

```powershell
.\.venv\Scripts\python.exe -m panel serve P3_interactive.ipynb --show
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

`P2_EDA_questions.ipynb` follows the updated upstream prompts: a data preview
and quality audit, conditional filtering, an article-length scatter plot,
a category distribution, and an interactive line plot with image counts in hover.
It also preserves all five project EDA analyses, including category medians,
title sentiment, and image/video combinations.

`P3_interactive.ipynb` follows the updated interactive-visualization prompts.
It includes a simple interactive comparison, a realistic choropleth plan and
empty prototype table, three groups of numeric feature choices, a scatter plot
with grouped X/Y selectors, the migrated dashboard, HTML export, and a reflection.
The news dataset has no geographic measurements, so no article map is fabricated.

Open either notebook from JupyterLab and run its cells in order. Each loads its
own data and can run independently. To use a different dashboard port:

```powershell
.\.venv\Scripts\python.exe -m panel serve P3_interactive.ipynb --port 5007 --show
```

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
