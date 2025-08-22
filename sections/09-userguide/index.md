---
title: User guide
has_children: false
nav_order: 10
---

# User guide

# Launching the application
To run the web application, execute the following command:

On Mac/Linux:

```bash
Copia
Modifica
PYTHONPATH=. streamlit run my_project/app.py
```
On Windows:

```bash
$env:PYTHONPATH="."
streamlit run my_project/app.py
```
This will start the Streamlit server and automatically open the application in the browser.

# User interface and features
![Interface](homepage.png)
When the application loads, the user is presented with a sidebar menu that serves as the main input panel. From here, the user can:
- Enter the food name (e.g., "Milk", "Carrots", "Chicken breast")
- Select the category of the item (fruit, meat, vegetables, dairy products, etc.)
- Provide the purchase date and expiry date, ensuring accurate tracking of freshness
- Indicate the quantity together with the correct unit of measure (e.g., grams, liters, pieces)

All added food items are automatically displayed in a persistent list on the home page. This list is continuously updated and sorted into three main categories:
- ✅ OK – items still fresh and safe to consume
- ⏳ Expiring soon – items close to their expiry date, highlighted to encourage timely consumption
- ❌ Expired – items that have already passed their expiry date

The sidebar also includes a filtering function that allows users to quickly view only the foods that match their expiry status of interest (e.g., show only “expiring soon” items).
![Filter](filter.png)

# Smart cooking suggestions
Further down the sidebar, users will find the “What can I cook today?” button.
This feature is integrated with the Spoonacular API and automatically generates recipe suggestions based on the items in the fridge, prioritizing foods that are near expiration.
This not only helps reduce waste but also provides inspiration for meal planning directly within the application.
![Meal inspiration](mealinspiration.png)

# Data visualization and insights
At the bottom of the interface, the application presents a set of statistics and visual insights, which include:
- The number of items currently fresh, expiring soon, or already expired
- The percentage of food waste relative to the total
- An estimate of the economic loss caused by expired products that were not consumed in time

These insights are designed to make users more aware of their consumption habits, helping them improve planning, reduce unnecessary purchases, and ultimately save money while reducing food waste.
![Statistics](statistics.png)