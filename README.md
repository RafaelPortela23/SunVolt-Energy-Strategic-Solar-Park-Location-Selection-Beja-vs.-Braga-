# SunVolt Energy: Strategic Solar Park Location Selection (Beja vs. Braga)

An end-to-end meteorological and predictive data science project developed for **SunVolt Energy** to determine the optimal location for a large-scale photovoltaic (PV) facility in Portugal by comparing **Beja** (Alentejo plains) and **Braga** (Northern Atlantic climate) using historical weather data from 2018 to 2026.

---

## 📌 Executive Summary & Recommendation

While Braga offers cooler ambient temperatures closer to Standard Test Conditions (25°C), Beja's overwhelming volume of raw shortwave radiation mathematically overcomes its heat-induced efficiency degradation—a phenomenon identified as the **"Thermal Paradox"**.

* **Beja:** Recorded **624 "Perfect" operational days** vs. Braga's 461 (+35%).
* **Braga:** Exhibited severe volatility and weather-induced downtime, with **1,274 "High Risk" days** vs. Beja's 800.
* **Final Decision:** **Beja** is recommended as the optimal, statistically bankable investment site, providing a stable energy production floor and predictable long-term yield.

---

## 🛠️ Key Technical Highlights

* **Data Processing:** Harmonized ~6,000 daily observations from Open-Meteo across solar irradiance, temperature, precipitation, cloud cover, and wind dynamics.
* **Domain Feature Engineering:**
  * **Radiation Efficiency:** Applied an empirical -0.3%/°C thermal degradation penalty when $T_{\max} > 25^\circ\text{C}$ to capture real-world panel efficiency drops.
  * **Day Quality Index:** Categorized daily conditions into *Perfect*, *Standard*, and *High Risk* based on joint thresholds of radiation efficiency, precipitation, and daylight duration.
  * **Degree Days:** Calculated Heating (HDD18) and Cooling (CDD22) metrics.
* **Machine Learning & Modeling:**
  * Benchmarked Logistic Regression, Random Forest (60-tree ensemble), Multi-Layer Perceptrons (MLP), k-Nearest Neighbors (kNN), and SVM.
  * Validated using stratified 10-fold cross-validation.
* **Statistical Rigor & Fairness:**
  * Conducted Paired $t$-tests and Wilcoxon signed-rank tests to confirm statistical significance across evaluation folds.
  * Performed algorithmic fairness auditing (Disparate Impact & Statistical Parity Difference) with reweighting mitigation.

---

## 📂 Repository Structure

```text
├── Milestone 3 - Solar.pdf        # Full technical report
├── datasets/                      # Raw and processed meteorological datasets
├── workflows/                     # Orange Data Mining workflows (.ows)
└── README.md                      # Project documentation
