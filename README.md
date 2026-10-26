# Hotel Bookings Analysis - Excel Final Project

Excel analysis of 119,390 hotel bookings (City Hotel & Resort Hotel, Jul 2015 - Aug 2017) focused on **cancellations, customer segmentation and revenue optimisation**.

## Files
| File | Description |
|---|---|
| `Hotel_Bookings_Analysis.xlsx` | Final workbook (Dashboard, Insights, cleaned Data, Data Dictionary, Cleaning Log) |
| `hotel_booking.csv` | Raw dataset (optional, see note below) |

## Workbook sheets
- **Dashboard** - KPIs (Total Bookings, Net Revenue, Cancellation Rate, ADR), filters (Hotel Type, Year, Customer Type), 9 charts, pivot-style tables, key insights
- **Insights** - 10 business questions, each with a table, a chart and a written insight / recommended action
- **Data** - cleaned data + 13 calculated columns (formulas)
- **Data_Dictionary** - meaning of every column
- **Cleaning_Log** - every cleaning step, assumptions, and how to build native PivotTables / Slicers

## Phase 1 - Cleaning (summary)
- No duplicate `Booking_ID`; header typo `Booking_1d` fixed
- Missing values: Children -> 0, Country -> "Unknown", Agent/Company -> 0
- Text standardised (Undefined -> SC / Unknown, "Non Refund" -> "Non Refundable")
- Arrival date was split over 3 columns with a text month -> rebuilt as a real `Arrival_Date`
- Personal data columns (name, email, phone, credit card) removed

## Phase 2 - Calculated columns
Total_Stay_Nights, Total_Guests, Guest_Type, Arrival_Date, Payment_Risk, Revenue_per_Booking, Realized_Revenue, Booking_Status, Lead_Time_Category (+ Arrival_Month_Num, Arrival_Quarter, Room_Changed, Data_Quality_Flag)

## Key findings
- 37.0% of bookings are cancelled; City Hotel 41.7% vs Resort Hotel 27.8%
- Cancellation rises with lead time: 18% (<30 days) -> 51% (>90 days)
- Online TA gives ~53% of net revenue; Groups are the riskiest segment (61% cancelled)
- July-August generate ~35% of net revenue
- Guests with a special request cancel far less (21.7% vs 47.7%)

## Notes
- Dashboard filters are drop-downs driven by COUNTIFS/SUMIFS formulas (they replace Slicers).
- Revenue = ADR x nights; Net Revenue counts non-cancelled bookings only.
- Dataset: public "Hotel Booking Demand" dataset, provided through the Route Academy course.
