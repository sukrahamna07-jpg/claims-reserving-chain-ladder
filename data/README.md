# Dataset

This folder contains documentation and sample data used for the claims reserving analysis.

The project uses quarterly claims development data covering origin periods from **2019 Q1 to 2023 Q2**.

## Variables

| Variable      | Description                                                         |
| ------------- | ------------------------------------------------------------------- |
| `Development` | Quarterly development period                                        |
| `Claim Lag`   | Number of quarters between the origin period and development period |
| `Claim`       | Incremental claim amount                                            |
| `Origin`      | Claim origin quarter                                                |

## Data Structure

The dataset is transformed into an incremental claims triangle and subsequently a cumulative claims triangle for the Chain Ladder analysis.

## Data Privacy

The repository does not contain the original raw Excel dataset when the source data is not intended for public distribution. A sample or anonymized dataset may be provided for reproducibility.
