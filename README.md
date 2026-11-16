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
`logistic_regression.ipynb` is the shared ML notebook. Its logistic regression
section includes a stratified train/test split, a preprocessing pipeline,
five-fold cross-validation, parameter selection, coefficient interpretation,
and test-set evaluation against a majority-class reference. Random Forest,
Histogram Gradient Boosting, and the final three-model comparison have empty
placeholders. Those sections must be completed to meet the full ML requirement.

```powershell
.\.venv\Scripts\python.exe -m jupyter lab logistic_regression.ipynb
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
