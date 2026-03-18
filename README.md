# Yelp Business Listings Data Quality Audit

Audit of Yelp business data (1M records) identifying data quality issues affecting ratings and geographic analysis.

## Goal
Assess whether the dataset is reliable for business category and geographic comparisons.

## Dataset
Large Yelp business listings dataset containing 1,000,000 records.

## Key Data Quality Issues
- `Rating = 0` used as a placeholder for unrated businesses
- Invalid and inconsistent values in the `State` column
- Raw averages distorted by inclusion of unrated businesses

## Cleaning Approach
- Created `is_rated` flag to isolate valid ratings
- Created `valid_state` flag to filter geographic data
- Built cleaned subsets for reliable analysis

## Key Findings
- ~259,000 records contain placeholder ratings
- ~4,000 records contain invalid state values
- Category averages significantly change after filtering
- Geographic analysis requires validation of location data

## Business Impact
Without cleaning, the dataset leads to misleading comparisons and incorrect decisions.

After applying simple validation rules, the dataset becomes reliable for benchmarking and analysis.

## Tech Stack
- Python
- pandas
- matplotlib

## Notes
Dataset not included due to size.
