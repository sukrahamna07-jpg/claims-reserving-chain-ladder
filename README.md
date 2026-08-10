# Claims Reserving Using the Chain Ladder Method

## Overview

This project applies the **Chain Ladder method** to estimate outstanding insurance claims using historical claims development data.

The analysis transforms quarterly claim data into an **incremental claims triangle** and **cumulative claims triangle**, then estimates development factors and cumulative development factors (CDF). These factors are used to project the ultimate claim amount for each origin period and estimate **IBNR (Incurred But Not Reported)** reserves.

The project was developed using **Python in Google Colab**, with a focus on data preparation, claims triangle construction, development factor analysis, and claims reserve estimation.

## Objective

The main objectives of this project are to:

* Construct an incremental claims development triangle from quarterly claim data.
* Convert incremental claims into a cumulative claims triangle.
* Calculate development factors for each claim development period.
* Calculate cumulative development factors (CDF).
* Estimate ultimate claims for each origin period.
* Estimate IBNR claims reserves.
* Visualize the claims development pattern and key results.

## Methodology

The analysis follows these main steps:

1. **Data Preparation**
   Clean and organize quarterly claim data based on development period and origin period.

2. **Claims Triangle Construction**
   Create an incremental claims triangle using `Origin` and `Claim Lag` as the primary dimensions.

3. **Cumulative Claims Triangle**
   Convert incremental claims into cumulative claims to observe the development of reported claims over time.

4. **Development Factor Calculation**
   Calculate age-to-age development factors from the cumulative claims triangle.

5. **Cumulative Development Factor (CDF)**
   Calculate cumulative development factors to estimate the remaining development of claims from the latest observed period to ultimate.

6. **Ultimate Claim Estimation**
   Estimate ultimate claims by applying the appropriate CDF to the latest reported cumulative claim for each origin period.

7. **IBNR Estimation**
   Calculate IBNR as the difference between estimated ultimate claims and reported claims.

## Dataset

The dataset contains quarterly claims development information covering origin periods from **2019 Q1 to 2023 Q2**.

The main variables used in the analysis include:

| Variable      | Description                                              |
| ------------- | -------------------------------------------------------- |
| `Development` | Quarterly development period                             |
| `Claim Lag`   | Number of quarters between origin and development period |
| `Claim`       | Incremental claim amount                                 |
| `Origin`      | Claim origin quarter                                     |

For portfolio purposes, the repository uses a sample version of the dataset rather than exposing potentially sensitive raw data.

## Development Factors

The Chain Ladder method uses historical claims development patterns to estimate how claims develop from one period to the next.

The estimated development factors are then converted into **CDFs**, which represent the expected cumulative development from each observed lag to the ultimate claim amount.

The analysis produced development factors ranging from approximately **1.0002 to 1.4836**, depending on the development period.

## Results

The final analysis produced the following aggregate estimates:

| Metric               |        Result |
| -------------------- | ------------: |
| Total Reported Claim | 44.26 billion |
| Total Ultimate Claim | 47.65 billion |
| Total IBNR           |  3.39 billion |

The results indicate that the estimated ultimate claims are higher than the currently reported claims. The difference represents the estimated claims that have not yet been fully reported or developed.

The most recent origin period, **2023 Q2**, has the largest estimated IBNR because it has only reached development lag 0 and therefore has substantially more future development remaining.

## Key Insights

* Earlier origin periods generally have more complete claims development histories and therefore lower CDF adjustments.
* More recent origin periods require larger development adjustments because fewer development periods have been observed.
* The Chain Ladder method estimates approximately **3.39 billion** in total IBNR based on the final calculation.
* The development pattern provides the basis for projecting incomplete claims experience toward ultimate values.
* The results demonstrate how historical claims development can be used to support insurance reserving analysis.

## Project Workflow

```text
Raw Claims Data
      ↓
Data Cleaning & Preparation
      ↓
Incremental Claims Triangle
      ↓
Cumulative Claims Triangle
      ↓
Development Factors
      ↓
Cumulative Development Factors (CDF)
      ↓
Ultimate Claims
      ↓
IBNR Estimation
      ↓
Visualization & Interpretation
```

## Tools & Technologies

* **Python**
* **Google Colab**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Jupyter Notebook**

## How to Run

1. Clone or download this repository.
2. Open the notebook in **Google Colab** or Jupyter Notebook.
3. Upload the sample dataset if required.
4. Run the notebook from the first cell to the last cell.
5. Review the claims triangle, development factors, CDF, ultimate claims, and IBNR results.

## Author

**Sukra Hamna**
