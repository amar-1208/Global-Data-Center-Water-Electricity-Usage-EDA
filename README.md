# Global Data Center Water & Electricity Usage — EDA

An exploratory data analysis of global data center resource consumption, examining Power Usage Effectiveness (PUE) and Water Usage Effectiveness (WUE) across facility types, countries, cooling systems, and years (2019–2025).

---

## Problem Statement

Data centers consume approximately 1–2% of global electricity and significant volumes of fresh water. This project analyses a global hybrid dataset to answer:
- **How efficient are data centers globally?** (PUE and WUE distributions)
- **Which facility types and cooling systems perform best?**
- **Is the industry improving year-on-year?**
- **Are data centers expanding into water-stressed regions?**

---

## Dataset Overview

| Feature | Description |
|---|---|
| `PUE` | Power Usage Effectiveness — ratio of total facility power to IT equipment power (lower = better) |
| `WUE_L_per_kWh` | Water Usage Effectiveness — litres of water consumed per kWh of IT load (lower = better) |
| `Facility_Type` | Hyperscale / Enterprise / Colocation / Edge |
| `Cooling_System_Type` | Air-side economizer / Evaporative / Liquid / Hybrid |
| `Year` | Year of record (2019–2025) |
| `Country` | Country where the data center is located |
| `Surrounding_Water_Stress_Tier` | Local water stress level (Low / Medium / High / Extremely High) |
| `Estimated_Capacity_MW` | Total installed IT capacity in megawatts |
| `Daily_Electricity_Usage_MWh` | Daily electricity consumption in megawatt-hours |
| `Daily_Water_Usage_Gallons` | Daily water consumption in gallons |

---

## Analysis Performed

### 1. Data Overview
- Loaded dataset; inspected shape, dtypes, and statistical summary via `info()` and `describe()`

### 2. PUE Distribution (Global)
- Histogram with KDE reveals two distinct peaks:
  - **~1.2** — Modern hyperscale facilities with advanced cooling
  - **1.5–1.6** — Standard enterprise data centers, the global majority
- Global median PUE: **1.643** — more than half of facilities still operate well above efficient benchmarks

### 3. WUE Distribution (Global)
- Wide spread in water consumption per kWh reflects highly variable cooling strategies and climates

### 4. Resource Efficiency by Facility Type
- Bar and box plots compare average PUE and WUE across Hyperscale, Enterprise, Colocation, and Edge facilities
- Hyperscale facilities consistently outperform all others on both metrics

### 5. Year-on-Year Trend Analysis (2019–2025)
- Violin plots track the global distribution of PUE and WUE annually
- Overall improvement trend visible, but the pace of progress is uneven

### 6. Water Stress Tier Expansion
- Stacked bar chart tracks data center density across water stress tiers year-on-year
- Growth is occurring in high and extremely high water stress areas — a sustainability red flag

### 7. Geographic Analysis
- Top 15 countries by number of data centers identified
- Top 10 countries by total installed capacity (MW) ranked

### 8. Cooling System Analysis
- Countplot of cooling system type distribution across the dataset
- Box plot of WUE by cooling system reveals evaporative cooling as the most water-intensive

### 9. Resource Correlation Analysis
- **PUE vs. Daily Electricity Usage** — scatterplot confirms higher PUE linearly increases energy waste
- **Capacity vs. Daily Water Usage** — near-linear relationship; larger facilities consume proportionally more water

---

## Key Findings

| Finding | Implication |
|---|---|
| Median PUE of 1.643 | Majority of global data centers operate inefficiently |
| Maximum PUE of 2.0 | Some facilities waste as much power on overhead as on computing |
| Two distinct efficiency tiers (1.2 and 1.5–1.6) | Technology and investment gap between hyperscale and enterprise operators |
| WUE varies significantly by cooling type | Cooling system selection has a direct impact on water sustainability |
| Data center growth in high water-stress regions | Industry expansion conflicts with water sustainability goals |
| Linear capacity–water usage relationship | Water planning must scale proportionally with facility growth |

---

## Recommendations

1. **Mandate PUE targets below 1.4** for all new data center builds
2. **Prioritise air-side economisers** in temperate climates to reduce WUE without performance loss
3. **Restrict siting in water-stressed regions** without mandatory water recycling and sourcing plans
4. **Retrofit legacy enterprise facilities** with modern cooling (liquid immersion, hot-aisle containment)
5. **Build a predictive resource model** — regression on facility type, cooling system, and capacity to forecast PUE/WUE

---

## Tools & Libraries

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-lightgrey?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualisation-teal)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Plotting-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)

---

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/global-datacenter-eda.git
cd global-datacenter-eda

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn

# 3. Launch the notebook
jupyter notebook Global_Data_Center_Water_and_Electricity_Usage_EDA_Analysis.ipynb
```

---

**Amarendra Andia** — Metallurgical & Materials Engineering Student, NIT Jamshedpur.
