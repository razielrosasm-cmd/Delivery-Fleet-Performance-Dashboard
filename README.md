# Regional Delivery Performance Ranking

## Project Overview

This project simulates a real-world logistics scenario where delivery routes are evaluated based on operational performance metrics.

The goal is to analyze efficiency, punctuality, and cost in order to:

* Identify underperforming routes
* Rank routes based on performance
* Detect top-performing (elite) routes
* Apply advanced Python techniques for data processing

---

## Skills Demonstrated

This project focuses on mastering core Python concepts before advancing to more complex data structures:

* ✅ List comprehensions
* ✅ `zip()` for multi-list iteration
* ✅ `lambda` functions with multiple conditions
* ✅ Advanced `sorted()` with multiple keys and tie-breaking
* ✅ `enumerate()` for ranking and indexing
* ✅ Real-world performance metrics modeling

---

## Dataset

```python
routes = ["North", "South", "East", "West", "Central", "Express"]

expected =  [200, 220, 210, 230, 250, 240]
delivered = [190, 200, 220, 210, 240, 230]
late =      [15, 25, 5, 30, 10, 12]
cost =      [600, 750, 500, 800, 900, 650]
```

---

## Performance Targets

```python
target_completion = 95
target_punctuality = 90
max_cost_per_package = 4.0
```

---

## Key Metrics

### Completion Rate

Measures how many expected deliveries were completed:

```
(delivered / expected) * 100
```

---

### Punctuality

Measures on-time delivery performance:

```
((delivered - late) / delivered) * 100
```

---

### Cost per Package

Operational efficiency indicator:

```
cost / delivered
```

---

### Performance Score

Weighted performance metric:

```
(completion * 0.5) + (punctuality * 0.3) + ((100 - cost_per_package * 10) * 0.2)
```

---

## Critical Routes Detection

Routes are flagged as critical if:

* Completion < target
* OR Punctuality < target
* OR Cost exceeds limit
* AND Overall score < 90

This introduces **multi-condition filtering logic** using list comprehensions.

---

## Ranking System (Advanced Sorting)

Routes are ranked using multiple criteria:

1. Highest performance score
2. Lowest cost per package (tie-breaker)
3. Highest completion rate (final tie-breaker)

Example implementation:

```python
sorted(records, key=lambda x: (-x[4], x[3], -x[1]))
```

---

## Ranking with Position (enumerate)

Routes are assigned ranking positions:

```python
[(1, "Central", score), (2, "North", score), ...]
```

Using:

```python
enumerate(sorted_data, start=1)
```

---

## Elite Routes Detection

A route is considered **elite** if:

* Completion ≥ 100
* Punctuality ≥ 95
* Cost per package < average

This simulates real-world performance incentives.

---

## Expected Outputs (Validation)

### Completion

```python
[95.0, 90.91, 104.76, 91.3, 96.0, 95.83]
```

### Punctuality

```python
[92.11, 87.5, 97.73, 85.71, 95.83, 94.78]
```

### Cost per Package

```python
[3.16, 3.75, 2.27, 3.81, 3.75, 2.83]
```

---

## 🚀 Why This Project Matters

This project replicates real operational analytics used in:

* Logistics & supply chain management
* Warehouse performance tracking
* Delivery optimization systems

It demonstrates the ability to:

* Transform raw data into actionable insights
* Apply structured logic to business problems
* Write clean, scalable Python code

---

## Next Step

This project serves as a foundation before moving into:

➡️ Dictionaries
➡️ Data aggregation by key
➡️ Real dashboard-like structures

---

## Author
Raziel Rosas Martinez
Developed as part of a structured progression from Python fundamentals to real-world problem solving.
