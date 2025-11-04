# 📊 IFS HRES Benchmark Notebook

This notebook can be used to generate the benchmark comparing:
- IFS HRES (baseline)
- Zeus subnet mean prediction
- Best-performing miner
using live data pulled from Weights & Biases.

### What the notebook does
- Loads all validator runs from W&B within the selected date range
- Extracts RMSE values for IFS, average miner score, and individual miners
- Groups results by forecast window (0–7 days) and variable
- Computes aggregate RMSE statistics
- Generates the bar charts used in our published benchmark

### How to run it
1. Set your W&B API key:
```
export WANDB_API_KEY=your_key_here
```

2. Install dependencies:
```
pip install -r requirements.txt
```

3. Open and execute the notebook:
```
jupyter notebook notebooks/IFS_HRES_Benchmarking.ipynb
```

Running the notebook will generate one PDF chart per variable.

### Notes
- Historic windows (negative horizons) are excluded, even though they make up the majority of samples
- “Best Miner” is computed only for miners active in ≥30% of samples for that window
