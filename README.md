# Market Basket Analysis of Café Transactions

## Project Overview

This project applies **Market Basket Analysis (MBA)** using the **Apriori algorithm** to uncover meaningful product associations from a café's transactional data. The dataset contains timestamped transactions of various product types (e.g., barista espresso, scone, regular syrup), enabling us to explore buying patterns and generate actionable business insights.

---

## Dataset Description

The dataset contains **149,116** transaction records with the following columns:

- `transaction_id`: Unique ID for each transaction
- `transaction_date`: Date of transaction
- `transaction_time`: Time of transaction
- `store_id`: Unique store identifier
- `store_location`: Location of the store
- `product_id`: Product identifier
- `unit_price`: Price of each unit
- `transaction_qty`: Quantity purchased
- `product_category`: Category of the product
- `product_type`: Type of product (used in this analysis)
- `product_detail`: Detailed description of the product

---

## Methodology

### Preprocessing
- Merged `transaction_date` and `transaction_time` to create a unified timestamp.
- Grouped products by `timestamp` to simulate individual customer baskets.
- Pivoted the dataset using one-hot encoding to create a basket matrix of product types.

### Applying Apriori
- Used `mlxtend` to apply the **Apriori algorithm** with a defined `min_support` threshold.
- Generated association rules using `support`, `confidence`, and `lift`.

### Filtering & Interpretation
- Rules were filtered and sorted by highest **lift** and **confidence** to prioritize meaningful insights.

---

##  Key Findings

| Rule | Insight |
|------|---------|
| `regular syrup → barista espresso` | 99.5% confidence & 7.1 lift — customers buying syrup almost always pair it with espresso. |
| `barista espresso → regular syrup` | 30.4% of espresso buyers add regular syrup. |
| `sugar free syrup → barista espresso` | Nearly all sugar-free syrup buyers also purchase espresso (99.4% confidence). |
| `barista espresso → scone` | 11.7% of espresso buyers also get a scone — mild but relevant pairing. |

---

## Visualizations

The project includes the following visualizations:
- **Bar charts** showing most frequent product combinations
- **Network graph** of association rules
- **Pie charts** for segment distributions
- **Geographical map visualizations** of store locations and transactions (in Tableau)

---

## Business Recommendations

- **Bundle** syrups with espresso to increase revenue.
- Offer **targeted promotions** for sugar-free options to health-conscious customers.
- Recommend **snack pairings** like scones with espresso during peak hours.
- Use product associations to inform **menu design** and **inventory planning**.

---

## Tools & Libraries Used

- **Python** (Pandas, NumPy, Matplotlib, Seaborn)
- **mlxtend** – For the Apriori algorithm and rule generation
- **Jupyter Notebook** – Development environment

---


## Project Status

 Completed. The analysis has been successfully carried out and visualized. You can explore and extend it further by:
- Changing the minimum support threshold
- Trying 3-item association rules
- Comparing product associations by time or location

---





