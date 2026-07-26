# DAX Measures

This document describes the DAX measures used in the **EV Charging Infrastructure Analysis** Power BI dashboard.

---

## 1. Total Stations

```DAX
Total Stations =
COUNTROWS(EV_Stations)
```

**Description**

Counts the total number of EV charging stations in the dataset.

---

## 2. Operational Stations

```DAX
Operational Stations =
CALCULATE(
    [Total Stations],
    EV_Stations[Status Code] = "E"
)
```

**Description**

Counts only the charging stations with an operational status code of **"E"**, representing active stations.

---

## 3. Total Level 2 Chargers

```DAX
Total Level 2 Chargers =
SUM(EV_Stations[EV Level2 EVSE Num])
```

**Description**

Calculates the total number of Level 2 charging ports available across all charging stations.

---

## 4. Total DC Fast Chargers

```DAX
Total DC Fast Chargers =
SUM(EV_Stations[EV DC Fast Count])
```

**Description**

Calculates the total number of DC Fast Chargers available across all charging stations.

---

# Summary

| Measure | Purpose |
|----------|---------|
| Total Stations | Counts all charging stations |
| Operational Stations | Counts operational charging stations |
| Total Level 2 Chargers | Sums all Level 2 charging ports |
| Total DC Fast Chargers | Sums all DC Fast charging ports |

---

## DAX Functions Used

- `COUNTROWS()`
- `SUM()`
- `CALCULATE()`

These measures power the KPI cards and support the dashboard's analysis of charging infrastructure across the United States.
