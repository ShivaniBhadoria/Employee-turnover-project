# Employee Turnover Analytics (Portobello Tech)

Predicts which employees are likely to leave, explains why, and sorts people into retention risk zones.
Course-end Project 1 of the Machine Learning module, Professional Certificate in AI and Machine Learning.

## What's in this folder

| File | Purpose |
| --- | --- |
| `employee_turnover_analysis.ipynb` | The full project: all 7 steps with explanations and charts |
| `HR_comma_sep.csv` | The dataset (14,999 employees) |
| `requirements.txt` | The Python libraries the project needs |

## Set up on a Mac (one time)

1. Install Python 3.12 from https://www.python.org/downloads/ (or `brew install python@3.12`).
2. Open Terminal and go to this folder:
   ```bash
   cd ~/Downloads/employee_turnover_project
   ```
3. Create and activate a virtual environment (a private space for this project's libraries):
   ```bash
   python3.12 -m venv .venv
   source .venv/bin/activate
   ```
4. Install the libraries:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

On Windows, use `py -3.12 -m venv .venv` and `.venv\Scripts\activate` instead.

## Run it

```bash
source .venv/bin/activate   # each time you open a new Terminal window
jupyter lab
```

JupyterLab opens in your browser. Open `employee_turnover_analysis.ipynb` and choose **Run > Run All Cells**. It takes under a minute.
When finished, press `Ctrl+C` in Terminal to stop JupyterLab, and run `deactivate` to leave the environment.

Prefer VS Code? Install the Python and Jupyter extensions, open this folder, open the notebook, and pick the `.venv` kernel at the top right.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| `ModuleNotFoundError: No module named 'imblearn'` | The environment isn't active or the install failed: activate `.venv` and run `pip install imbalanced-learn` |
| An imblearn import error that mentions scikit-learn | The two versions don't match: run `pip install "scikit-learn==1.7.*"` |
| `FileNotFoundError: HR_comma_sep.csv` | Keep the CSV in the same folder as the notebook |
| The notebook can't find your libraries | In JupyterLab or VS Code, switch the kernel to the `.venv` one |

## Expected results

Exact numbers can vary slightly with library versions. On the test set:

| Model | Recall (left) | Precision (left) | ROC-AUC |
| --- | --- | --- | --- |
| Logistic regression | about 0.81 | about 0.51 | about 0.83 |
| Random forest | about 0.98 | about 0.98 | about 0.99 |
| Gradient boosting | about 0.94 | about 0.93 | about 0.99 |

The notebook also saves `employee_risk_zones.csv`, with each test employee's probability of leaving and risk zone.
