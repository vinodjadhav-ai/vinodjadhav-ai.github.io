# Unit 6 — Group D: Airbnb NYC Market Segmentation and Price Prediction

## Project overview

Group D investigated two questions: which segments exist in the New York City Airbnb market, and how can price prediction help hosts make competitive decisions? We used the **AB_NYC_2019** dataset (48,895 listings, 16 variables). The project combined exploratory data analysis (EDA), regression and clustering. My personally assigned responsibility was **data understanding and EDA**; the regression and clustering findings below are **collective Group D results**, not models I claim to have built individually.

## What the group found

- **Pricing:** mean $152.72, median $106; 95% of listing prices were $355 or below. The skew and expensive outliers make city-wide average price misleading.
- **Room type:** entire homes/apartments had a median price of **$160**, private rooms **$70**, and shared rooms **$45**.
- **Location:** median price was **$150** in Manhattan, **$90** in Brooklyn, **$75** in Queens and Staten Island, and **$65** in the Bronx.
- **Regression:** Histogram Gradient Boosting achieved test **MAE $59.38**, test **RMSE $205.05** and **R² 0.146**. Random Forest had a slightly lower test MAE ($59.24), while Gradient Boosting was favoured on the broader evaluation measures.
- **Market segmentation:** the group reported **nine** market segments (four entire-home, three private-room and two shared-room groups). Price was excluded from forming clusters, then compared afterwards.

## Interpretation and limitations

The group recommended comparing listings with similar room types, locations and availability characteristics rather than relying on a single city-wide price. Prediction remains uncertain: R² of 0.146 means most price variation was not explained by the available variables. Our report notes that only 88 test listings (0.9%) contributed 82.73% of total squared prediction error. The findings describe 2019 listing data, not today's market.

## Evidence

- [Final group report (PDF)](group-final-report.pdf)
- [My EDA and data-understanding contribution](my-eda-contribution.md)
- [Teamwork reflection](teamwork-reflection.md)
- [Trello task board (PDF)](trello-team-board.pdf)

**Source:** Group D final submitted report, sections “Dataset and Preparation”, “Exploratory Findings”, “Regression: Price Prediction” and “Clustering: Market Segments”.
