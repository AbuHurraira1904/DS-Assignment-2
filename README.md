# DS Assignment 2: Cleaned Datasets

Cleaned datasets for Assignment 2 (Exploratory Data Analysis) of Data Science (CS4048), FAST-NU Lahore.

- Roll number: 23L-0662
- Version: v1.0
- Date: 19 October 2026

## Files

| File | Rows | Columns | Description |
|---|---|---|---|
| `23L_0662_A2_netflix_cleaned.csv` | 8,807 | 19 | Cleaned Netflix Movies and TV Shows data |
| `23L_0662_A2_supermarket_cleaned.csv` | 1,000 | 19 | Cleaned Supermarket Sales data |

## Original sources

- **Netflix:** https://www.kaggle.com/datasets/shivamb/netflixshows (standard version, 8,807 rows x 12 columns). The data belongs to its original author. Please check the licence on the Kaggle page.
- **Supermarket Sales:** `supermarket_Sales.csv`, provided by the instructor and used exactly as supplied (1,000 rows x 17 columns).

## What I changed in the Netflix data

- Moved 3 movie durations from `rating` to `duration`, and set their `rating` to Unknown.
- Filled missing `director`, `cast`, `country` and `rating` with "Unknown".
- Removed extra spaces from all text columns (88 `date_added` values and 1 title).
- Converted `date_added` to a date. The 10 missing dates are left missing.
- No rows were removed. Outliers were kept.

New columns:

| Column | Meaning |
|---|---|
| `year_added` | Year from `date_added` |
| `years_to_add` | `year_added` minus `release_year` |
| `num_countries` | Number of countries (0 means unknown) |
| `num_genres` | Number of genres in `listed_in` |
| `duration_minutes` | Movie length in minutes (Movies only) |
| `num_seasons` | Number of seasons (TV Shows only) |
| `rating_group` | Kids, Family, Teens, Adults or Unknown |

## What I changed in the Supermarket data

- Combined `Date` and `Time` into one `datetime` column. The two text columns are removed.
- Added `hour`, `weekday` and `month`.
- No rows were removed. No missing values, duplicates or calculation errors were found, so nothing else was changed.
- `Gross margin percentage` is constant and `Gross income` equals `Tax 5%`. I kept both columns but did not use them in the analysis.

## Notes for Assignment 3

- Netflix: do not use `show_id`, `title` or `description` as features. `duration_minutes` and `num_seasons` are never filled together.
- Supermarket: `Tax 5%`, `Total`, `Cost of goods sold` and `Gross income` are all calculated from `Unit price` and `Quantity`.

## Versions

| Version | Date | Change |
|---|---|---|
| v1.0 | 19 October 2026 | First version |
