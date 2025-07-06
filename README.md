#  Dynamic Pricing for Urban Parking Lots

**Summer Analytics 2025 | Consulting & Analytics Club × Pathway**
*Author: Dhruv Gohil*

---

##  Overview

This project builds a real-time dynamic pricing engine for urban parking lots. It intelligently adjusts the parking price based on demand patterns, traffic congestion, special events, vehicle types, and competitive behavior. The system aims to make parking more efficient, reducing overcrowding and improving utilization.

---

## 🛠 Tech Stack

* **Python** — Core logic & modeling
* **Pandas** — Data processing
* **Bokeh** — Real-time interactive visualization
* **Geopy** — Calculating distances for competitive pricing
* **CatBoost** — Machine learning with categorical feature handling
* **Google Colab** — Development environment

---

##  System Architecture

```mermaid
graph TD
    A[Dataset Upload (CSV)] --> B[Preprocessing & Feature Engineering]
    B --> C1[Model 1: Baseline Pricing]
    B --> C2[Model 2: Demand-Based Pricing]
    B --> C3[Model 3: Competitive Pricing]
    C1 --> D[Price Output Table]
    C2 --> D
    C3 --> D
    D --> E[Visualization: Bokeh Live Plot]
```

---

##  Project Workflow

1. **Upload CSV:** Upload and read the dataset from Google Colab using `files.upload()`.
2. **Preprocessing:** Clean columns, map vehicle types to weights, and normalize relevant features.
3. **Model 1 - Baseline:**

   * A simple linear function increasing price with occupancy.
   * Acts as the reference.
4. **Model 2 - Demand-Based:**

   * Considers occupancy, queue, traffic, special day, vehicle type.
   * Normalizes demand to control price bounds.
5. **Model 3 - Competitive Pricing:**

   * Calculates average price of nearby lots.
   * Adjusts price upward/downward to remain market-competitive.
6. **ML Model (Optional):**

   * CatBoostRegressor trained on full feature set.
   * Tuned via GridSearchCV.
7. **Visualization:**

   * Real-time chart rendered using Bokeh.
   * Shows all 3 models over time.

---

##  Features Implemented

* [x] Real-time price simulation
* [x] Three-stage pricing logic
* [x] Competitive logic using geolocation
* [x] Interactive line plot for each lot
* [x] Colab-compatible setup

---


##  How to Run

1. Open the notebook in [Google Colab](https://colab.research.google.com/).
2. Upload your `dataset.csv` using the provided upload cell.
3. Run each cell step-by-step.
4. Interact with the real-time Bokeh graph showing price updates.

---

##  Assumptions

* Vehicle types are limited to \[car, bike, truck].
* Occupancy and queue are positively correlated with price.
* Nearby competitors are defined within a 1 km radius.
* Price is capped between \$5 and \$20 for business realism.

---

##  Outcome

By blending domain intuition with data-driven modeling, this system achieves:

* Fair, demand-sensitive pricing
* Adaptive control over parking usage
* Visualization that justifies pricing decisions

This project mimics a real-world smart parking backend that could be expanded to integrate with IoT devices or city infrastructure.



