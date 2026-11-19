# Hotel Booking Demand — EDA Project

## Overview
End-to-end exploratory analysis of City Hotel and Resort Hotel booking data. The notebook explores booking demand, origin countries, ADR and room pricing, seasonality, meal preferences, special requests, length of stay, market segments, and cancellation behavior.

## Dataset
- **File:** `hotel_bookings.csv`
- **Source:** Hotel Booking Demand dataset (hotel bookings for a City Hotel and Resort Hotel)
- **Rows/columns before cleaning:** 119,390 rows × 32 columns
- The CSV is included in this repository.

## Notebook contents
- Data quality inspection and cleaning (duplicate removal, children missing values, ordered month categorical)
- Non-cancelled subset for realized demand, guest profile, pricing, and preferences
- Guest origin countries + choropleth
- ADR by hotel, room type, month
- Meal preferences
- Special requests vs cancellation outcome
- Busiest months, length of stay, market segment
- Cancellation counts/rates by hotel and month
- Tables, charts, caveats, and stakeholder recommendations

## Key insights
The dataset-derived headline insights after exact duplicate removal are:

- Non-cancelled booking volume is larger for City Hotel (37,379 vs 25,992 bookings).
- Average non-cancelled ADR: City Hotel 108.28; Resort Hotel 92.97 (ADR is dataset currency, not inferred).
- The leading origin country is PRT (17,662 non-cancelled booking records).
- Peak realized bookings month (all hotels pooled): August; peak cancellation month by count: August.
- Highest pooled monthly average ADR: August (147.12).
- Most common non-cancelled market segment: Online TA; most common meal code: BB.
- Highest cancellation count by hotel: City Hotel; cancellation rates are {'City Hotel': 0.3003855656210227, 'Resort Hotel': 0.23480923221855865} (fraction).

Open the notebook for supporting charts, detailed tables, and caveats. Insights are descriptive; avoid treating associations as causal.


## How to run
1. Clone/download the repository.
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly pycountry jupyter
   ```
3. Start Jupyter:
   ```bash
   jupyter notebook
   ```
4. Open `Hotel_Booking_Demand_EDA.ipynb` and run all cells from top to bottom.

The notebook expects `hotel_bookings.csv` in the same folder as the notebook.


## Repository structure
```
├── Hotel_Booking_Demand_EDA.ipynb
├── hotel_bookings.csv
└── README.md
```

## Notes / limitations
- Exact duplicates are dropped to avoid repeated rows inflating counts.
- Missing `children` values are filled with 0; missing `country` is excluded only from country analysis.
- ADR charting is capped at the 99th percentile for readability; the summary metrics use the uncapped data.
- Monthly plots pool years, so year-specific changes can be masked.
- Booking records are used as a guest-origin proxy; they are not counts of distinct people.
