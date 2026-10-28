# Hotel Booking Cancellation — Data Analysis

**Project focus:** Exploratory and diagnostic analysis of hotel reservation cancellations using Python, pandas, DuckDB SQL, and matplotlib/seaborn. This is the **data analysis** portion of my Hotel Booking work. An optional machine-learning extension is kept separately while I strengthen my ability to explain and validate the modeling steps.

## Business questions

1. Which hotel types and booking channels have the highest *cancellation rates* versus *canceled booking counts*?
2. How does **lead time** relate to cancellations, including within each hotel type?
3. How are **deposit type**, **market segment**, and **arrival month** associated with cancellations?
4. What estimated *booked value* is associated with canceled reservations (without calling it observed lost revenue)?

## Key Business Findings

| Finding | Earlier observed result | Implication to investigate |
| --- | --- | --- |
| Hotel type | City Hotel: **41.73%** cancellation rate; Resort Hotel: **27.76%** | Inspect segment and lead-time differences before changing policy. |
| High-rate vs high-volume segment | Groups: **61.06%** cancellation rate and **12,097** canceled bookings; Online TA: **36.72%** and **20,739** canceled bookings | Prioritization should consider both probability and size of affected bookings. |
| Lead time | **91+ days: 50.65%** cancellation rate vs **0–30 days: 18.56%** | Examine early booking patterns within individual hotels and channels. |

## Methods

- Explore dataset shape, columns and categories.
- Use DuckDB SQL to calculate booking volumes, cancellation rates, and segmentation.
- Visualize lead-time, deposit, segment and monthly arrival patterns.
- Estimate booked value as ADR × nights, explaining exclusions and interpretation.

## Run in Google Colab

1. Open [`hotel_booking_data_analysis.ipynb`](hotel_booking_data_analysis.ipynb) in Google Colab.
2. Choose **Runtime → Run all**. The first code cell reads the public CSV directly from GitHub; the notebook has a DuckDB installation cell.
3. Inspect errors and confirm metrics before referencing results on a resume.

**Original data:** [TidyTuesday hotels.csv (2020-02-11)](https://raw.githubusercontent.com/rfordatascience/tidytuesday/main/data/2020/2020-02-11/hotels.csv).

## Limitations

- The available time series uses **arrival month**, not the date the reservation was created, and endpoint years are not complete.
- ADR × booked nights estimates *associated booking value*, not proven lost revenue or hotel profit. Check currency assumptions independently.
- Relationships in this observational dataset do not establish causation.
- The notebook retains my original SQL/Python code without rewriting the methods; its structure has been organized for readability.

