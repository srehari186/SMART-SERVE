# SMART-SERVE
Canteen waste forecaster
📊 Overview

Canteens routinely over- or under-prepare food, leading to waste, added cost, and inefficient planning. This dashboard consolidates daily meal-level data (preparation, consumption, waste, cost, weather, and special events) into a single view that answers:

Which food items and categories waste the most?
How does waste vary by day of week, meal type, and weather?
What's the waste trend, and what can we expect in the coming weeks?
Do special events (festivals, exams, sports days) drive waste spikes?
🔍 Key Insights
🍛 Lunch generates the highest waste of all meal types.
🥗 Salad and Vegetable Curry together account for ~49% of total waste.
👥 Waste increases on days with the highest diner counts.
☀️ Hot/summer weather correlates with a higher waste percentage.
🗂️ Data

The dashboard is built on a daily canteen dataset with the following fields:

Column	Description
Date, DayOfWeek, IsWeekend	Calendar attributes
MealType	Breakfast / Lunch / Dinner
FoodItem, Category	Menu item and its category (Staples, Vegetables, Non-Veg, Sweets, Snacks, Starters)
Weather	Sunny, Hot, Cloudy, Rainy
SpecialEvent	Sports Day, Festival, Exam Week, or None
DinerCount	Number of diners served
QtyPrepared_kg, QtyConsumed_kg, QtyWasted_kg	Quantities in kilograms
CostPerKg_INR, WasteCost_INR	Cost fields in Indian Rupees

Sample data file: data/canteen_food_waste_sample.csv

🛠️ Tech Stack
Power BI Desktop — data modeling, DAX measures, visuals
Power Query (M) — data cleaning and transformation
DAX — KPI measures, rolling averages, and forecast logic
Built-in Power BI Analytics forecasting (exponential smoothing) for the trend projection
