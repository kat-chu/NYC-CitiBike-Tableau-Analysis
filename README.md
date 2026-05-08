# NYC Citi Bike Ridership Analysis | Jan - Mar 2024

![Tableau](https://img.shields.io/badge/Tool-Tableau-E97627?style=flat&logo=tableau&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)
![Data](https://img.shields.io/badge/Records-1.6M+-blue?style=flat)

---

## View the Full Interactive Dashboard

**[Tableau Public Dashboard](https://public.tableau.com/views/NYC_CitiBike_Analysis_2024/Story1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

Direct URL: https://public.tableau.com/views/NYC_CitiBike_Analysis_2024/Story1

---

## Overview

New York City's Citi Bike program is the largest bike-sharing program in the United States, generating millions of ride records every month. This project analyzes 1,663,295 rides from January through March 2024 to answer a fundamental question for city planners and program administrators: who is riding, when are they riding, and where?

The analysis uncovers two distinct phenomena that have direct implications for how the city should allocate bikes, plan infrastructure, and design pricing strategy. The findings are presented through two interactive dashboards and a geographic map built for a non-technical city official audience.

---

## Project Structure

```
NYC-CitiBike-Tableau-Analysis/
│
├── Images/
│   ├── dashboard_1_rider_behavior.png
│   ├── dashboard_2_station_usage.png
│   └── station_map.png
├── .gitignore
└── README.md
```

---

## Dataset

- **Source:** [Citi Bike System Data](https://www.citibikenyc.com/system-data)
- **Direct URL:** https://www.citibikenyc.com/system-data
- **Period:** January, February, and March 2024
- **Files:** 8 CSV files unioned in Tableau
- **Total Records:** 1,663,295 rides
- **Fields:** ride_id, rideable_type, started_at, ended_at, start/end station name, start/end coordinates, member_casual

---

## Methodology

Eight CSV files spanning January through March 2024 were unioned in Tableau Public to create a single dataset of 1.6 million records. Three calculated fields were engineered directly in Tableau to support the analysis:

- **Trip Duration (Minutes):** Calculated using DATEDIFF between started_at and ended_at timestamps
- **Hour of Day:** Extracted using DATEPART to enable hourly ridership analysis
- **Day of Week:** Extracted using DATENAME to identify weekly usage patterns

Both dashboards were built with interactive filter actions, allowing users to click any data point and dynamically filter the other visualizations on the same dashboard. The geographic map was filtered to the top 50 busiest start stations to optimize performance and focus the analysis on the most actionable locations.

---

## Phenomenon 1: Members and Casual Riders Use the System in Fundamentally Different Ways

![Dashboard 1](Images/dashboard_1_rider_behavior.png)

When you separate the 1.6 million rides by rider type, two completely different usage profiles emerge. Annual members and casual riders are not using the same program in the same way. They are effectively two different user groups with different needs, different schedules, and different motivations.

### Key Findings

- Members show two sharp daily peaks, a morning surge around 8am and an evening surge around 5-6pm, a textbook commuter pattern
- Casual riders show a single broad afternoon peak between 3-5pm with no morning spike, consistent with leisure and tourist activity
- Casual riders take trips averaging 22 minutes, nearly twice the 11-minute average for members, suggesting exploratory rather than point-to-point travel
- Weekend ridership shows a higher proportion of casual riders relative to weekdays, further confirming the leisure use pattern
- Friday is the single busiest day across both groups, while Thursday consistently sees the lowest weekday ridership
- Both groups drop to near-zero ridership between 2-4am

### Why This Matters

These behavioral differences have direct operational implications. Member commuters need reliable bike availability at residential stations in the early morning and at commercial/transit hub stations in the evening. Casual riders need availability at tourist-heavy and recreational areas throughout the afternoon. A one-size-fits-all rebalancing strategy will fail both groups. The data supports a time-of-day and location-specific approach to bike redistribution.

---

## Phenomenon 2: Electric Bikes Dominate and Station Demand Is Highly Concentrated

![Dashboard 2](Images/dashboard_2_station_usage.png)

The second phenomenon reveals a significant shift in how riders choose their bikes, and a geographic concentration of demand that has major implications for infrastructure investment.

### Key Findings

- Electric bikes account for 65% of all rides (1,087,449) compared to 35% for classic bikes (575,846), a nearly 2-to-1 preference for e-bikes
- Electric bike preference holds across both member and casual rider groups, suggesting this is a program-wide shift rather than segment-specific behavior
- W 21 St & 6 Ave in Chelsea is the single busiest start station, followed by Broadway & W 58 St near Columbus Circle
- The top 10 busiest stations are heavily concentrated in Midtown Manhattan and Chelsea, areas with dense office buildings, transit hubs, and tourist destinations
- Station demand drops sharply outside of this core geographic zone

### Why This Matters

The dominance of electric bikes suggests the program should prioritize e-bike availability and charging infrastructure, particularly at the highest-demand stations. The geographic concentration of demand in Midtown and Chelsea means that bike shortages at a relatively small number of stations can have an outsized impact on overall program satisfaction. Targeted investment in these high-demand corridors would yield the greatest return.

---

## City Official Map: Station Popularity Across NYC

![Station Map](Images/station_map.png)

The interactive map plots the top 50 busiest Citi Bike start stations across New York City. Color intensity represents total ride volume, with darker dots indicating higher ridership. The map makes the geographic concentration of demand immediately visible. Activity is densest in Midtown Manhattan and the west side of Manhattan from Chelsea through the Upper West Side, with a secondary cluster emerging in Brooklyn. Outer borough stations show significantly lower demand during this period, which may reflect seasonal patterns given the January through March timeframe.

---

## Summary of Key Metrics

| Metric | Value |
|--------|-------|
| Total Rides Analyzed | 1,663,295 |
| Member Ride Share | ~74% |
| Casual Ride Share | ~26% |
| Electric Bike Share | 65% |
| Classic Bike Share | 35% |
| Avg Member Trip Duration | 11 minutes |
| Avg Casual Trip Duration | 22 minutes |
| Busiest Day of Week | Friday |
| Peak Hour for Members | 5-6 PM |
| Peak Hour for Casual Riders | 3-4 PM |
| Busiest Start Station | W 21 St & 6 Ave (Chelsea) |

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Tableau Public 2024.3 | Data visualization, dashboard and story creation |
| Tableau Calculated Fields | Trip duration, hour of day, day of week engineering |
| Citi Bike Open Data | Primary data source |

---

## Context

This project was completed as part of the Data Analytics and Visualization Bootcamp at the University of Minnesota. It demonstrates applied data visualization, interactive dashboard design, calculated field engineering, and data storytelling for a non-technical city official audience.
