# House Price Prediction – King County, USA

Predicting house sale prices with Python and regression models.
Completed as the final project of the IBM course *Data Analysis with Python* (IBM Data Analyst Professional Certificate, Coursera).

## Business question
A real estate investment trust wants to estimate the market price of a house from its features
(living area, number of floors, grade, waterfront view, location, and more).

## Dataset
- About 21,600 house sales in King County (Seattle area), May 2014 – May 2015
- 21 features, such as `price`, `bedrooms`, `bathrooms`, `sqft_living`, `floors`, `waterfront`, `view`, `grade`, `lat`, `zipcode`
- Source: public King County house sales dataset, slightly modified by IBM Skills Network for the course

## Tools
Python · pandas · NumPy · Matplotlib · seaborn · scikit-learn · Jupyter

## What I did
1. **Data wrangling:** dropped ID columns and filled missing values in `bedrooms` and `bathrooms` with the column mean
2. **Exploratory data analysis:** counted houses by number of floors, compared prices for waterfront and non-waterfront houses (boxplot), and checked the relationship between `sqft_above` and price (regression plot and correlations)
3. **Model development:** built simple and multiple linear regression models and a pipeline with scaling and polynomial features
4. **Model evaluation and refinement:** used a train/test split, Ridge regression and a second-order polynomial transform

## Results

| Model | Data | R² |
|---|---|---|
| Linear regression – `sqft_living` only | full data | ≈ 0.49 |
| Linear regression – 11 features | full data | ≈ 0.66 |
| Pipeline (scaling + polynomial + linear regression) | full data | ≈ 0.75 |
| Ridge regression (alpha = 0.1) | test data | ≈ 0.65 |
| Polynomial (degree 2) + Ridge (alpha = 0.1) | test data | **0.70** |

## Key insights
- **Living area and grade** are the strongest price drivers; a single feature explains only about half of the price variation.
- **Waterfront houses** are more expensive on average, and price outliers occur in both groups.
- **Polynomial features** improve the model, which shows that the relationships are not purely linear.
- The test score is lower than the score on the full data, so the model only partly generalises to unseen houses.

## Next steps
- Log-transform `price` to reduce skew and make errors more even across price ranges
- Investigate outliers, such as a house listed with 33 bedrooms
- Tune the Ridge `alpha` with cross-validation (`GridSearchCV`)
- Add location features (`zipcode`) and try tree-based models

## Files
- `House_Sales_in_King_County_USA.ipynb` – full notebook with code and explanations
- `House_Sales_results.pdf` – notebook export with all outputs (charts and R² scores)
  
## Author
**Emmanuel Ogochukwu Okatta** – Junior Data Analyst (career changer), Essen, Germany
[GitHub](https://github.com/emmanuel-ogochukwu-okatta)
