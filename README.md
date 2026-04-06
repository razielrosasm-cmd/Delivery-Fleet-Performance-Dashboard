# Delivery Fleet Performance Dashboard

## Project Overview

This project simulates a real-world logistics scenario where a delivery fleet is evaluated based on operational performance metrics.

The objective is to analyze and optimize delivery performance by measuring:

* Completion rate
* Punctuality
* Cost efficiency
* Overall performance score

The system processes daily operational data and generates a structured performance dashboard to support decision-making.

---

## Skills Demonstrated

This project showcases strong foundational Python skills applied to real business logic:

*  List comprehensions for efficient data processing
*  `zip()` for multi-variable iteration
*  `lambda` functions for dynamic selection (max/min)
*  Data structuring using tuples
*  Conditional filtering for business rules
*  Modular function design

---

## Dataset

```python
vehicles = ["Van 1", "Van 2", "Van 3", "Van 4", "Van 5"]

expected_packages = [120, 150, 130, 160, 140]
delivered_packages = [115, 140, 120, 150, 145]
late_packages = [10, 20, 5, 25, 8]
operational_cost = [300, 400, 350, 450, 380]
```

---

## Performance Targets

```python
target_completion = 95
target_punctuality = 90
max_cost_per_package = 3.0
```

---

## Key Metrics

### Completion Rate

Measures delivery fulfillment:

(delivered / expected) * 100

---

### Punctuality

Measures on-time delivery:

((delivered - late) / delivered) * 100

---

### Cost per Package

Measures operational efficiency:

cost / delivered

---

### Performance Score

A weighted performance metric combining all KPIs:

(completion * 0.5) + (punctuality * 0.3) + ((100 - cost_per_package * 10) * 0.2)

 Cost penalizes the score, simulating real-world operational pressure.

---

## Data Structure

Each vehicle is represented as a tuple:

```python
(vehicle, completion, punctuality, cost_per_package, score)
```

This structure allows efficient analysis using indexing and lambda functions.

---

##  Business Logic Implemented

###  Underperforming Vehicles

A vehicle is flagged if:

* Completion < target
* OR Punctuality < target
* OR Cost exceeds threshold

---

###  Best & Worst Vehicles

Using `lambda`:

```python
max(records, key=lambda x: x[4])
min(records, key=lambda x: x[4])
```

---

###  Most Expensive Vehicle

```python
max(records, key=lambda x: x[3])
```

---

###  Ranking System

Vehicles are ranked by performance score:

```python
sorted(records, key=lambda x: x[4], reverse=True)
```

---

###  High Efficiency Vehicles

Vehicles that exceed expectations:

* Completion ≥ 100
* Punctuality ≥ 90

---

##  Expected Output (Validated)

### Completion

```python
[95.83, 93.33, 92.31, 93.75, 103.57]
```

### Punctuality

```python
[91.30, 85.71, 95.83, 83.33, 94.48]
```

### Cost per Package

```python
[2.61, 2.86, 2.92, 3.00, 2.62]
```

### Performance Score

```python
[90.09, 86.66, 89.06, 85.87, 94.89]
```

---

##  Key Insights

* **Best performing vehicle:** Van 5
* **Worst performing vehicle:** Van 4
* **Most expensive vehicle:** Van 4
* **Underperforming vehicles:** Van 2, Van 3, Van 4
* **Top efficiency vehicle:** Van 5

---

##  Why This Project Matters

This project reflects real-world scenarios in:

* Logistics operations
* Fleet performance monitoring
* Supply chain optimization

It demonstrates the ability to:

* Transform raw operational data into insights
* Apply structured business logic
* Build scalable analytical functions

---

##  Next Step

This project serves as a foundation for advancing into:

 Dictionaries (structured data models)
 Aggregation and grouping
 Dashboard-style analytics

---

##  Author

Developed as part of a structured learning path from Python fundamentals to real-world data analysis and operational problem solving.
