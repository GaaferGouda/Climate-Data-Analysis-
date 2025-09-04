#  Climate Data Analysis with NASA Power API

This project provides a **merged workflow** for analyzing climate data using the **NASA Power API**.  
It combines fetching, processing, visualization, and exporting in one clean pipeline.

---

##  Workflow Steps

### 1. Setup & Imports
We use the following Python libraries:
- `requests` → for fetching API data  
- `pandas` → for tabular processing  
- `matplotlib` → for plotting  

---

### 2. Fetch Climate Data
We access the **NASA POWER API** endpoint:

Parameters include:
- **latitude, longitude** → location coordinates  
- **start, end** → date range (`YYYYMMDD` format)  
- **parameters** → variable(s) of interest  

Examples of variables:
- **T2M** → 2-meter air temperature (°C)  
- **RH2M** → 2-meter relative humidity (%)  

**General API Formula:**

Response = f(latitude, longitude, start, end, parameter)

---

### 3. Process & Analyze Data

The raw JSON response is converted into a **Pandas DataFrame**.  
Then, we compute **monthly averages** from the daily values.

**Daily → Monthly Aggregation:**

X_monthly = (1 / N) * Σ (X_daily)

where:  
- **X_daily** = daily value  
- **N** = number of days in the month  

---

### 4. Visualization

We plot the processed data to identify long-term **climate trends**.

Examples:
- Temperature cycles (higher in summer, lower in winter)  
- Relative humidity trends  

---

### 5. Export Results

Processed data is saved to **CSV files** for further analysis and reproducibility.

---

##  Example: Alexandria, Egypt (2010–2015)

- **Latitude:** 31.2001  
- **Longitude:** 29.9187  
- **Period:** 2010-01-01 → 2015-12-31  
- **Variables:**  
  - T2M (Air Temperature at 2m)  
  - RH2M (Relative Humidity at 2m)  

**Sample Output Files:**
- `alexandria_t2m_monthly.csv` → Monthly average temperatures  
- `alexandria_rh2m_monthly.csv` → Monthly average humidity  

---

