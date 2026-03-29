# Sorting & Searching Fundamentals and Implementation

This repository contains **real-world problems** designed to help you understand **Sorting and Searching algorithms from fundamentals to advanced real-time financial systems**.

Each problem includes:

* Scenario
* Problem Statement
* Concepts Covered
* Use Cases
* Expected Output

# Week 3

## Problem 1: Transaction Fee Sorting for Audit Compliance

### Scenario

A banking application processes **10,000 daily transactions**. Auditors require transactions to be sorted by fee amount for compliance reviews.

### Problem Statement

Implement a fee-sorting system that:

* Sorts transactions by **fee in ascending order using Bubble Sort** (for small batches ≤ 100)
* Sorts by **fee + timestamp using Insertion Sort** (for medium batches 100–1,000)
* Handles duplicate fees (**stable sorting required**)
* Flags **high-fee outliers (> $50)**

### Concepts Covered

* Bubble Sort: adjacent swaps, early termination
* Insertion Sort: sorted subarray building
* Time complexity: O(n²) analysis
* Stability in sorting algorithms

### Use Cases

* Banking transaction audit reports
* Fraud detection using fee patterns
* Compliance fee threshold analysis

### Expected Output

```
Input transactions:
id1, fee=10.5, ts=10:00
id2, fee=25.0, ts=09:30
id3, fee=5.0, ts=10:15

BubbleSort (fees): [id3:5.0, id1:10.5, id2:25.0] // 3 passes, 2 swaps
InsertionSort (fee+ts): [id3:5.0@10:15, id1:10.5@10:00, id2:25.0@09:30]
High-fee outliers: none
```

## Problem 2: Client Risk Score Ranking

### Scenario

The risk management team needs quick sorting of **500 client risk scores** for priority review.

### Problem Statement

Implement a system that:

* Sorts clients by **riskScore (ascending) using Bubble Sort**
* Sorts by **riskScore DESC + accountBalance using Insertion Sort**
* Identifies **Top 10 highest-risk clients**

### Concepts Covered

* In-place sorting algorithms
* Adaptive behavior of Insertion Sort
* Space complexity O(1)

### Use Cases

* KYC risk prioritization
* Loan approval ranking
* AML risk analysis

### Expected Output

```
Input: [clientC:80, clientA:20, clientB:50]

Bubble (asc): [A:20, B:50, C:80] // Swaps:2
Insertion (desc): [C:80, B:50, A:20]

Top 3 risks: C(80), B(50), A(20)
```

## Problem 3: Historical Trade Volume Analysis

### Scenario

Analyze **1 million daily trades** by volume for market trend reports.

### Problem Statement

Build a system that:

* Sorts trades by **volume (ascending) using Merge Sort**
* Sorts by **volume (descending) using Quick Sort**
* Merges two sorted trade lists (morning + afternoon)
* Computes **total trade volume**

### Concepts Covered

* Merge Sort: divide and conquer
* Quick Sort: pivot selection and partitioning
* Stability vs in-place sorting
* Worst-case complexity in Quick Sort

### Use Cases

* Market volume reports
* Portfolio rebalancing
* Trading analytics

### Expected Output

```
Input: [trade3:500, trade1:100, trade2:300]

MergeSort: [1:100, 2:300, 3:500] // Stable
QuickSort (desc): [3:500, 2:300, 1:100] // Pivot: median
Merged morning+afternoon total: 900
```

# Week 4

## Problem 4: Portfolio Return Sorting

### Scenario

Sort **10,000 investment assets** based on historical returns for investment recommendations.

### Problem Statement

Implement a system that:

* Uses **Merge Sort** to sort assets by returnRate (stable sorting)
* Uses **Quick Sort** to sort by returnRate DESC + volatility ASC
* Handles pivot selection (random vs median-of-3)

### Concepts Covered

* Stability in Merge Sort
* Quick Sort optimization
* Hybrid algorithms
* External sorting (large data)

### Use Cases

* Asset allocation systems
* Portfolio optimization
* Investment recommendation engines

### Expected Output

```
Input: [AAPL:12.0%, TSLA:8.0%, GOOG:15.0%]

Merge: [TSLA:8.0%, AAPL:12.0%, GOOG:15.0%]
Quick (desc): [GOOG:15.0%, AAPL:12.0%, TSLA:8.0%]
```

## Problem 5: Account ID Lookup in Transaction Logs

### Scenario

Search **1 million transaction logs** for specific account IDs for compliance purposes.

### Problem Statement

Implement:

* Linear Search to find first/last occurrence
* Binary Search (after sorting by ID)
* Count comparisons and analyze time complexity
* Handle duplicate account IDs

### Concepts Covered

* Linear Search: O(n)
* Binary Search: O(log n)
* Searching with duplicates
* Time complexity comparison

### Use Cases

* Transaction forensics
* Dispute resolution
* Regulatory reporting

### Expected Output

```
Sorted logs: [accB, accA, accB, accC]

Linear first accB: index 0 (1 comparisons)
Binary accB: index 1 (1 comparisons), count=2
```

## Problem 6: Risk Threshold Binary Lookup

### Scenario

A financial system uses **risk bands** to categorize clients. New clients must be placed in the correct band quickly.

### Problem Statement

Build a system that:

* Uses Linear Search for unsorted risk data
* Uses Binary Search on sorted risk bands
* Finds **floor value** (largest ≤ target)
* Finds **ceiling value** (smallest ≥ target)

### Concepts Covered

* Binary search variations
* Lower bound and upper bound
* Searching in sorted arrays

### Use Cases

* Risk classification systems
* Dynamic pricing engines
* Financial compliance systems

### Expected Output

```
Sorted risks: [10, 25, 50, 100]

Linear: threshold=30 → not found (4 comparisons)
Binary floor(30): 25, ceiling: 50 (2 comparisons)
```
