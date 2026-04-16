# Bike-Sharing Demand Analysis — Excel Analytics Project

> End-to-end analysis of 1,000+ hourly bike rental records to uncover how weather, time, and day type drive demand — built entirely in Microsoft Excel.

---

## Overview

This project analyses a real-world bike-sharing dataset to answer a key business question:
**What factors most influence bike rental registrations, and how can operators use this to optimise availability?**

Using only Excel, I built a full analytical pipeline — from raw data cleaning and feature engineering to pivot-table dashboards and correlation analysis — surfacing actionable insights across weather conditions, wind speed, and weekday vs. weekend patterns.

---

## Dataset

| Property | Detail |
|---|---|
| Records | 1,004 hourly observations |
| Time period | Starting Jan 2011 |
| Variables | Date, Hour, Temperature, Humidity, Windspeed, Holiday flag, Day of week, Rental registrations, Permanent registrations |
| Total registrations analysed | **58,304** across all records |

---

## Key Findings

### Weather impact on registrations
| Humidity Category | Total Registrations |
|---|---|
| Less Humidity | 46,318 (79.4%) |
| High Humidity | 9,216 (15.8%) |
| Moderate Humidity | 2,770 (4.8%) |

> Low-humidity conditions drive nearly **5x more rentals** than high-humidity days.

### Windspeed vs. registration type
| Windspeed | Rental | Permanent |
|---|---|---|
| Low | 906 | 13,490 |
| Moderate | 444 | 5,127 |
| High | 1,396 | 12,535 |

### Weekday vs. weekend demand
| Day Type | Rental Registrations | Total Registrations |
|---|---|---|
| Weekday | 3,144 | 41,461 |
| Weekend | 1,777 | 16,843 |

> Weekdays account for **71% of total registrations** — usage is commute-driven, not leisure-driven.

### Day-of-week breakdown (Total Registrations)
| Day | Total |
|---|---|
| Saturday (5) | 9,095 — highest |
| Monday (1) | 8,450 |
| Wednesday (3) | 8,383 |
| Sunday (6) | 7,748 — lowest |

---

## Excel Techniques Used

- **VLOOKUP** — joined rental and permanent registration data across sheets
- **CHOOSE + IF formulas** — converted numeric day codes to day names
- **Nested IF logic** — categorised humidity (`< 0.70` = Less, `< 0.75` = Moderate, else High) and windspeed into Low / Moderate / High bands
- **CORREL function** — calculated temperature-to-registration correlation across 1,000 rows
- **AVERAGE & STDEV.S** — rolling statistical summaries per record
- **SUM** — aggregated rental + permanent into total registration column
- **Pivot Tables (x5)** — segmented registrations by day, humidity, windspeed, and weekend/weekday
- **Slicers** — interactive filtering on the dashboard sheet by date
- **Multi-sheet workbook** — structured across 7 sheets for clean separation of raw data and analysis

---

## File Structure

```
Nexthikes-Project1/
│
├── Next hikes final project (2).xlsx    # Main workbook
│   ├── Main Sheet                       # Raw data + feature engineering (1,004 rows)
│   ├── Registration_Day                 # Pivot: registrations by day of week
│   ├── Registration_Humidity            # Pivot: registrations by humidity category
│   ├── Diff_Registration_Humidity       # Pivot: rental vs permanent by humidity
│   ├── Registration_Windspeed           # Pivot: rental vs permanent by windspeed
│   ├── Registration_Weekend_Weekday     # Pivot: weekday vs weekend comparison
│   └── Slicer                           # Interactive dashboard with date slicer
│
└── README.md
```

---

## Business Insights

1. **Stock more bikes on low-humidity days** — they generate nearly 5x the registrations of high-humidity days.
2. **Weekday supply is critical** — 71% of all registrations happen Monday–Friday, suggesting commuter-driven demand.
3. **Saturday peaks, Sunday dips** — within the week, Saturday sees the highest volume (9,095) while Sunday is lowest (7,748).
4. **Temperature positively correlates with registrations** — warmer hours drive higher rental activity (CORREL analysis on 1,000+ records).

---

## Tools

![Microsoft Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)

---

## Author

**Sumeet Rajput**
[LinkedIn](https://www.linkedin.com/in/sumeet-rajput-a82211385) · [GitHub](https://github.com/SumeetRajput)
