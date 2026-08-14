# 🍽️ Canteen Waste Forecasting Dashboard

An interactive **Power BI dashboard** for tracking, analyzing, and forecasting food waste in a canteen/cafeteria setting — built to help operations teams reduce over-preparation, cut costs, and plan smarter.




## 📊 Overview

Canteens routinely over- or under-prepare food, leading to waste, added cost, and inefficient planning. This dashboard consolidates daily meal-level data (preparation, consumption, waste, cost, weather, and special events) into a single view that answers:

- Which food items and categories waste the most?
- How does waste vary by day of week, meal type, and weather?
- What's the waste trend, and what can we expect in the coming weeks?
- Do special events (festivals, exams, sports days) drive waste spikes?

---

## 🧩 Key Features

| Section | Description |
|---|---|
| **KPI Cards** | Average waste (kg), average food consumed, average waste cost (₹) at a glance |
| **Top 10 Food Items by Waste** | Ranks items driving the most waste, in kg |
| **Waste Trend Over Time** | Daily waste trend with a **forecast band** projecting future waste |
| **Waste by Food Category** | Category-level breakdown (Vegetables, Staples, Snacks, Starters, Sweets, Non-Veg) |
| **Waste by Day of Week** | Highlights weekday vs. weekend waste patterns |
| **Waste by Weather** | Shows how weather conditions correlate with waste levels |
| **Auto-Generated Insights** | Narrative call-outs (e.g., "Lunch generates the highest waste") |
| **Slicers** | Filter by Month and Meal Type (Breakfast / Lunch / Dinner) |

---

## 🔍 Key Insights

- 🍛 **Lunch** generates the highest waste of all meal types.
- 🥗 **Salad** and **Vegetable Curry** together account for ~49% of total waste.
- 👥 Waste increases on days with the **highest diner counts**.
- ☀️ **Hot/summer weather** correlates with a higher waste percentage.

---

## 🗂️ Data

The dashboard is built on a daily canteen dataset with the following fields:

| Column | Description |
|---|---|
| `Date`, `DayOfWeek`, `IsWeekend` | Calendar attributes |
| `MealType` | Breakfast / Lunch / Dinner |
| `FoodItem`, `Category` | Menu item and its category (Staples, Vegetables, Non-Veg, Sweets, Snacks, Starters) |
| `Weather` | Sunny, Hot, Cloudy, Rainy |
| `SpecialEvent` | Sports Day, Festival, Exam Week, or None |
| `DinerCount` | Number of diners served |
| `QtyPrepared_kg`, `QtyConsumed_kg`, `QtyWasted_kg` | Quantities in kilograms |
| `CostPerKg_INR`, `WasteCost_INR` | Cost fields in Indian Rupees |

> Sample data file: `data/canteen_food_waste_sample.csv`

---

## 🛠️ Tech Stack

- **Power BI Desktop** — data modeling, DAX measures, visuals
- **Power Query (M)** — data cleaning and transformation
- **DAX** — KPI measures, rolling averages, and forecast logic
- **Built-in Power BI Analytics forecasting** (exponential smoothing) for the trend projection

See [`docs/PowerBI_Build_Guide.md`](docs/PowerBI_Build_Guide.md) for the full data model, Power Query steps, and DAX measures used to build this from scratch.

---

## 📁 Repository Structure

```
canteen-waste-forecasting/
├── README.md
├── data/
│   └── canteen_food_waste_sample.csv
├── powerbi/
│   └── Canteen_Waste_Forecasting.pbix
├── docs/
│   └── PowerBI_Build_Guide.md
└── assets/
    └── dashboard_preview.png
```

---

## 🚀 Getting Started

1. Clone this repository.
2. Open `powerbi/Canteen_Waste_Forecasting.pbix` in **Power BI Desktop**.
3. If prompted, update the data source path to point to `data/canteen_food_waste_sample.csv`.
4. Refresh the data model (**Home → Refresh**).
5. Explore the dashboard using the Month and Meal Type slicers.

To rebuild the dashboard from scratch (data model, DAX measures, forecasting logic), follow [`docs/PowerBI_Build_Guide.md`](docs/PowerBI_Build_Guide.md).

---

## 📈 Forecasting Approach

Future waste is projected using Power BI's built-in **Analytics forecast** (ETS / exponential smoothing with weekly seasonality), shown as the shaded confidence band on the trend chart. An alternative DAX-based moving-average/seasonal-index forecast is also documented in the build guide for teams that want full transparency into the calculation.

---

## 🤝 Contributing

Contributions are welcome — feel free to open an issue or submit a pull request for additional visuals, improved forecasting models (e.g., Prophet/ARIMA via Python integration), or data quality improvements.

---

## 📄 License

This project is available under the [MIT License](LICENSE).
