# OrderFlowImbalanceAnalysis

This repository contains a modular Python script for constructing Order Flow Imbalance (OFI) features from financial order book data. The code is designed to be clean, well-documented, and compatible with future versions of pandas.

## Features
- Computes OFI features including Best-Level OFI, Multi-Level OFI, Integrated OFI, and Cross-Asset OFI.
- Processes order book data with support for multiple levels (default is 10 levels).
- Aggregates data into time buckets (default frequency is 1 minute).
- Handles timezone adjustments (default is America/New_York).
- Filters data for a specific date range (currently set to 2024-10-21 08:54 to 11:04).

## Requirements
- Python 3.6+
- pandas
- numpy
- scikit-learn

Install the dependencies using:
```
pip install pandas numpy scikit-learn
```

## Usage
1. Ensure your input data (CSV file) contains order book data with columns like `ts_event`, `symbol`, `bid_px_00`, `bid_sz_00`, `ask_px_00`, `ask_sz_00`, etc.
2. Run the script:
   ```bash
   python compute_ofi_features.py
   ```
3. The script will process the data and save the results to `ofi_features.csv`.

You can customize the input file, output file, number of levels (`M`), and time bucket frequency (`freq`) by modifying the arguments in the `main()` function.

## Code Structure
- **Data Loading and Preprocessing**: Loads the dataset, converts timestamps, adjusts timezone, and filters the date range.
- **Order Flow Computation**: Calculates bid and ask order flows for each level.
- **Time Bucketing and Aggregation**: Aggregates order flows into time buckets.
- **Feature Computation**: Computes the OFI features (Best-Level, Multi-Level, Integrated, Cross-Asset).
- **Output Generation**: Saves the results to a CSV file.

## License
MIT License
