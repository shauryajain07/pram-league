# Premier League Match Predictor

A small football data experiment exploring a bigger question: how much can be estimated before the match starts, before the story has already been written?

The repository is an honest baseline rather than a finished betting model. It currently uses a compact Premier League attacker dataset and a multiple linear regression script to create a performance index. The next interesting step is making the evaluation properly chronological and moving from player-level signals toward pre-kickoff match probabilities.

## What is here

- `premier_league_attackers_2023-24.csv` — a small dataset of attacker features, including minutes, goals, assists, expected goals, shot conversion, dribbling, touches, and final-third passing.
- `regression_model.py` — cleans missing values, encodes categorical features, scales numeric inputs, fits a linear regression model, and writes predictions plus a 0–100 performance index.

Running the script also creates `actual_vs_predicted.png` and `premier_league_attackers_2023-24_with_performance_index.csv`.

## Run it locally

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install pandas numpy scikit-learn matplotlib
python regression_model.py
```

The included script fits and predicts on the same small dataset, so its output is exploratory and should not be read as out-of-sample accuracy.

## Questions this project is pushing toward

- Which features would have been available at the exact time of a match?
- How do you prevent future information from leaking into a prediction?
- Are calibrated probabilities more useful than a single winner label?
- Can football intuition survive evaluation that happens before kickoff rather than after the result?

The project is a place to work through those questions with data, not a claim that the model has solved them.
