# EvidentlyAI Data Monitoring Lab

Data monitoring example using Evidently and the California
Housing dataset.

This notebook demonstrates how to:

- Load the California Housing dataset from scikit-learn
- Add categorical features for house age and target price
- Split data into reference and production sets using `MedInc`
- Define an Evidently schema for numerical and categorical columns
- Run a `DataDriftPreset` report to compare both datasets

## Usage

Install dependencies:

```bash
pip install pandas numpy scikit-learn evidently
```

Open and run:

```bash
jupyter notebook EvidentlyAI_Data_Lab.ipynb
```

Run all cells to generate a drift report between the reference and
production datasets.

## Output

The notebook produces:

- Reference dataset
- Production dataset
- Evidently drift report

Monitored columns include:

- Numerical: `MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`,
  `Population`, `AveOccup`, `Latitude`, `Longitude`, `target`
- Categorical: `age_category`, `price_category`
