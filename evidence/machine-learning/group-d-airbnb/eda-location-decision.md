## EDA Decision Note — Location

- `neighbourhood_group` shows clear differences in typical listing prices and should be retained as a candidate feature for regression.
- `neighbourhood` contains 221 unique categories and may provide more detailed location information.
- The usefulness of detailed neighbourhood information versus the additional modelling complexity should be considered during Data Preparation.
- No location variables are removed or transformed during EDA.