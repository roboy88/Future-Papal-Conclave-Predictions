# Papal Election Predictor

This is a machine learning notebook that predicts which Catholic cardinals have the highest statistical probability of being elected pope, based on age, years of service, and geographic region.

## Files

- `predictor_colab.ipynb`: Main notebook for use in Google Colab
- `cardinals.csv`: Input dataset
- `requirements.txt`: Python libraries required to run the notebook locally

## Setup Instructions

1. Upload `cardinals.csv` in the first cell when prompted.
2. Run all cells in `predictor_colab.ipynb`.
3. View top predicted candidates and explore summary outputs.

## Dependencies

Install with:

```
pip install -r requirements.txt
```

## License

This project is for educational and analytical purposes. No endorsement or claim is made regarding papal selection.

## Why Didn’t the Model Predict Pope Leo XIV or Claudio Gugerotti?

Although this machine learning model is designed to forecast papal probabilities, it did not rank Robert Prevost (now Pope Leo XIV) or Archbishop Claudio Gugerotti among the top candidates. This outcome reflects several underlying constraints of the model and the training data:

### 1. Lack of Positive Election Data

The dataset only contains a single cardinal labeled as 'Elected_Pope = 1'. With so few positive examples, the model lacks enough variation to generalize what makes a cardinal “papable.” This severely limits the model's ability to distinguish real election patterns.

> Machine learning models require multiple examples of each outcome to detect patterns. One elected pope isn’t enough to train a generalizable classifier.

### 2. Conservative Historical Bias

This model was trained primarily on:
- Age
- Years as cardinal
- Geographic region (e.g., Africa, Latin America, Ukraine)
- Liturgical affiliation (e.g., Eastern Rite)
- Assigned office (e.g., prefect, eparch, bishop)

Based on historical precedent, the model heavily favors:
- Italian or Latin American cardinals
- Long-standing curial leaders (e.g., Parolin)
- Offices like Secretary of State or Congregation of Bishops

Prevost and Gugerotti, while significant, do not match this historical profile:
- Prevost is American (no U.S. pope has ever been elected)
- Gugerotti leads the Dicastery for the Eastern Churches, which has not traditionally produced popes

### 3. Random Forest Models Are Pattern-Conservative

Random Forests are excellent for encoding historical data patterns but do not extrapolate well to novel scenarios. Without seeing multiple examples of non-traditional papal candidates being elected, it assigns them a probability of nearly 0%.

### Want More Realism or Vision?

To better simulate visionary or reformative conclaves, consider:
- Augmenting the training data with multiple past popes
- Building a secondary model that weights global representation more heavily
- Exploring feature importance or SHAP values to interpret predictions

This project can evolve into both a historical mirror and a visionary forecasting tool with these enhancements.
