# I-94 Traffic Volume Dashboard (Power BI)

An interactive Power BI dashboard that shows when traffic is heaviest on the I-94 highway between Minneapolis and St Paul, using hourly data from 2012 to 2018.

![Dashboard](traffic%20dashboard%20screenshot.png)

## Questions the dashboard answers
- At what hours of the day is traffic heaviest, and does it differ on weekdays and weekends?
- Which days of the week and months are busiest?
- Does the pattern change from year to year? (use the Year filter)

## Data
- Source: Metro Interstate Traffic Volume dataset, UCI Machine Learning Repository
- About 40,500 hourly records after cleaning (October 2012 to September 2018)
- Cleaning (done in Python, see `prepare_dashboard_data.ipynb`): removed duplicate timestamps, replaced impossible values (0 K temperatures, extreme rainfall) with blanks, and added columns for year, month, hour, day type and time of day

## What I built
- Line chart: average traffic by hour of day, split by weekday and weekend
- Column chart: average traffic by day of week
- Column chart: average traffic by month
- Year filter that updates all charts

## Key insights
- Average traffic is about 3,290 vehicles per hour, about 3,560 on weekdays and about 2,620 on weekends (roughly 26% lower).
- Weekdays have two peaks, around 7 am and 4 to 5 pm, both near 6,000 vehicles per hour. Weekends have a single, smoother peak around midday (about 4,400).
- Friday is the busiest day (about 3,675) and Sunday the quietest (about 2,425).
- Monthly differences are small: August is highest (about 3,430) and December lowest (about 3,040).

## Limitations
- One highway segment, one direction, 2012 to 2018
- 2012 only contains October to December, and some periods have missing hours, so year-to-year comparisons should be read carefully
- The dataset marks holidays only for the first hour of the day, so holidays are not analysed
- Averages describe patterns; they do not explain causes

## Files
- `Traffic_Dashboard.pbix`: the Power BI report (open with the free Power BI Desktop)
- `dashboard_screenshot.png`: screenshot of the dashboard
- `prepare_dashboard_data.ipynb`: Python notebook that downloads and prepares the data

## Tools
Power BI Desktop, Python, Pandas
