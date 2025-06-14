# Modern Mercantilism Forecast Challenge – Data & Code

This repository contains **all source data and Python code** referenced in my submission to Bridgewater Associates’ **2025 Modern Economics Forecast Challenge**.  
Everything here is released under an MIT licence so reviewers can replicate the probability estimates and stress-test results.

## Repository contents

| File | Purpose |
|------|---------|
| **`raw_export_bans.csv`** | Clean, hand-curated list of ≥ 6-month export bans by G-20 emerging-market countries since 2020. Columns: `country`, `commodity`, `start`, `end` (ISO dates, “ongoing” if still in force). |
| **`bayesian_workbook.xlsx`** | Excel workbook used to update the prior Beta(4, 6) distribution. Tabs:<br>  • `parameters` – prior hyper-parameters.<br>  • `export_bans` – same data as CSV for Excel users.<br>  • `stress_test` – posterior means and adjusted probabilities for all sensitivity scenarios (3, 5, 7 bans × Stable/Elevated price environments). |
| **`stress_test_demo.ipynb`** | Jupyter notebook that rebuilds the 2 × 3 sensitivity table shown in Appendix A3. Load, run-all, and compare with the PDF. |

## Quick start

```bash
# 1. Clone the repo
git clone https://github.com/your-handle/modern-mercantilism-challenge.git
cd modern-mercantilism-challenge

# 2. Create a lightweight environment
python -m venv venv
source venv/bin/activate       # Windows: venv\Scripts\activate
pip install -r requirements.txt  # just pandas & scipy

# 3. Reproduce the stress-test table
jupyter notebook stress_test_demo.ipynb
