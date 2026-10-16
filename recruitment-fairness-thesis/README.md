# Algorithmic Bias Detection in Recruitment Systems

**Thesis topic:** A study of ethical AI frameworks and algorithmic bias detection in recruitment systems  
**Status:** Research prototype; validate methods and reproduce results before using findings in the thesis.

## Overview
This notebook explores recruitment data, trains binary hiring-decision classifiers, compares predictive performance, and audits outcomes by the protected attribute `Gender`.

It includes exploratory data analysis, duplicate removal, train/test splitting, feature scaling, Logistic Regression, Decision Tree, Random Forest, XGBoost (or a Gradient Boosting fallback), classification metrics, group fairness metrics, a heuristic bias score, text reports, and interactive Plotly dashboards.

## Important limitations to address
- The CSV dataset was not included in the uploaded notebook. The notebook expects `ajmal_recruitment_data.csv`. Put an authorised copy in `data/` and update the path to `../data/ajmal_recruitment_data.csv`, or document how the dataset can be accessed.
- Confirm the dataset's source, licence, provenance, feature definitions, gender encoding, and whether the target reflects real or simulated hiring decisions.
- Missing values are reported but are not imputed or removed. Handle them before modelling.
- The notebook scales every feature, including encoded categorical and protected columns. Review the preprocessing approach; nominal categories should not automatically be treated as continuous values.
- The custom bias score and Low/Moderate/High thresholds are heuristic choices, not universally accepted standards. Justify them in your thesis or replace them with a validated framework.
- The 80% disparate-impact rule is a screening heuristic, not proof of fairness or legality.
- Some fairness metrics can be undefined for particular group/model combinations. Missing values should not be treated as evidence of fairness.
- The dashboard assumes Gender groups are coded `0` and `1`; verify this in the dataset.
- High accuracy does not prove that a recruitment model is ethical or suitable for real hiring. Do not use this prototype to make actual employment decisions.

## Structure
```text
recruitment-fairness-thesis/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/recruitment_fairness_analysis.ipynb
├── data/README.md
├── src/README.md
├── reports/README.md
├── figures/README.md
└── docs/methodology-notes.md
```

## Setup (Windows PowerShell)
Recommended: Python 3.11 or 3.12; verify package compatibility with your installed Python version.
```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter lab
```
Open `notebooks/recruitment_fairness_analysis.ipynb`.

## Data setup
1. Obtain permission to use the dataset and check privacy/licensing restrictions.
2. Put the CSV at `data/ajmal_recruitment_data.csv`.
3. Change the notebook's loading line to:
   ```python
   df = pd.read_csv("../data/ajmal_recruitment_data.csv")
   ```
4. Run every cell from a clean kernel and inspect warnings and outputs.
5. Do not upload personal, restricted, or unlicensed data to GitHub. If the dataset cannot be shared, provide a data-access statement.

## Reproducibility
The notebook sets random seed `42`. Record package versions, dataset provenance/version, preprocessing choices, split strategy, and metric definitions. The notebook currently writes output files to its working directory; for a polished project, route generated charts to `figures/` and reports to `reports/`.

## Research integrity
This is a starting structure, not a claim that the method has been fully validated. Clearly distinguish exploratory results from defensible findings and discuss limitations with your supervisor.
