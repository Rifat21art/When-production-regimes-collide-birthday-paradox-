# When Production Regimes Collide


## Run

Python 3.10+ is recommended. Install dependencies:

```bash
python -m pip install -r requirements.txt
python -m jupyterlab

Open `Production_Regime_Collisions.ipynb` and choose **Kernel → Restart & Run All**. Start Jupyter from this folder.
```

Run cells from top to bottom from this repository's root directory. It was mainly experimented on Google Colab and altered with minor modifications and revisions for git ready style.

The notebook first attempts to fetch UCI dataset 601 (`ucimlrepo`). If network access or the UCI endpoint is unavailable, download the AI4I 2020 CSV from [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/601) and save it as `ai4i2020.csv` in the repository root. The CSV is input data and is intentionally not committed.

## Main reported findings

- 10,000 observations and 339 machine failures (3.39%).
- With three tertile bins for each of five continuous variables and three product types, the nominal regime space is `N = 3 × 3⁵ = 729`; 435 regimes were observed and the effective size was approximately 159.
- The empirical 50% collision point is about 15 observations versus about 32 under the uniform `N = 729` benchmark.
- Regime familiarity was weakly positively associated with failure in this synthetic dataset; rarity was not evidence of risk.
- Adding regime-frequency features did not improve Random Forest failure prediction in the reported comparison (mean PR-AUC 0.755 baseline vs 0.731 collision-aware).

## Data and license

AI4I 2020 Predictive Maintenance Dataset, UCI Machine Learning Repository, dataset 601, [CC BY 4.0](https://archive.ics.uci.edu/dataset/601). Cite the dataset and the accompanying paper when reusing this work.
