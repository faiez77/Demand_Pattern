# Demand_Pattern_Analysis & Product Clustering 

🎯 Project Objective:

The core idea of this project is to cluster products that exhibit similar demand patterns over time.

Instead of grouping products only by total sales, this project focuses on how products behave in terms of demand:

What Do We Mean by “Demand Pattern”?

A demand pattern is not a single number.
It is a combination of multiple characteristics derived from time-series sales data:

Average demand → how much the product sells on average
Demand volatility → how much sales fluctuate over time
Recent demand trend → short-term behavior compared to the past
Demand range → minimum and maximum observed sales
Price information → impact of unit price on demand behavior

So two products belong in the same cluster if:
They sell similarly
Their demand fluctuates similarly
Their recent behavior is similar

📂 Dataset Description

Source: Grocery sales CSV dataset(https://www.kaggle.com/datasets/pratyushpuri/grocery-store-sales-dataset-in-2025-1900-record)
Granularity: Daily sales transactions

| Column       | Meaning                                          |
| ------------ | ------------------------------------------------ |
| `Product`    | Product name                                     |
| `Date`       | Transaction date                                 |
| `Quantity`   | Units sold                                       |
| `Store`      | Store name (missing → filled as `unknown_store`) |
| `Category`   | Product category                                 |
| `unit_price` | Price per unit                                   |


🔄 How clustering achieves this idea:
Step 1: Convert time-series data → behavior features
We do not cluster raw daily data.

Instead, we summarize each product into:
“How does this product behave?”
That’s why rolling window features are crucial.

Step 2: Scale features
Clustering is distance-based, so:
Quantity ≠ Price scale
Scaling ensures fair comparison

Step 3: Apply unsupervised learning
We let the algorithm:
Discover patterns
Group similar behaviors
Without predefined labels

📊 What does each cluster represent?

After clustering, each group naturally corresponds to:

Cluster Type	Meaning
Stable / High-demand	Consistent, predictable sales
Volatile	Unpredictable, fluctuating demand
Slow-moving	Low and infrequent demand

✔ These labels are added after clustering
✔ Clustering itself is purely data-driven
