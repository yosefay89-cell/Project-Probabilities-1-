# 📊 Probability & Statistical Distributions — Programming Assignment

> **Faculty of Computers and Information**
> Software Engineering B.Sc.

---

## 📁 Project Structure

```
StatisticsAssignment/
│
├── Program1_Statistics.cs        # Part 1 — Statistical Measures
├── Program2_OutlierDetection.cs  # Part 2 — Outlier Detection
└── README.md                     # Project Documentation
```

---

## 📌 Dataset

The following 25 values are used in both programs:

```
115, 182, 191, 31, 196, 1099, 5, 172, 10, 179,
83, 21, 20, 21, 186, 177, 195, 193, 188, 199,
62, 109, 105, 183, 110
```

> **n = 25**

---

## 🔢 Part 1 — Statistical Measures (`Program1_Statistics.cs`)

### Description

A C# program that reads the dataset and computes the following 13 statistical measures:

| #      | Statistic                          | Description                             |
| ------ | ---------------------------------- | --------------------------------------- |
| (i)    | **Mean**                           | Average of all values (Σxᵢ / n)         |
| (ii)   | **Mode**                           | Most frequently occurring value(s)      |
| (iii)  | **Median**                         | Middle value of sorted data             |
| (iv)   | **Variance**                       | Population variance σ² = Σ(xᵢ − x̄)² / n |
| (v)    | **P20**                            | 20th Percentile                         |
| (vi)   | **P50**                            | 50th Percentile                         |
| (vii)  | **Third Quartile (first mention)** | Q3 = P75                                |
| (viii) | **Second Quartile**                | Q2 = Median = P50                       |
| (ix)   | **Third Quartile**                 | Q3 = P75                                |
| (x)    | **Range**                          | Max − Min                               |
| (xi)   | **Interquartile Range (IQR)**      | Q3 − Q1                                 |
| (xii)  | **Standard Deviation**             | σ = √Variance                           |
| (xiii) | **Summation of Divisions**         | Σ(xᵢ / n)                               |

### Key Methods Used

```csharp
CalculateMean(double[] data)
CalculateMode(double[] data)
CalculateMedian(double[] sorted)
CalculateVariance(double[] data, double mean)
CalculatePercentile(double[] sorted, double percentile)   // Interpolation method
CalculateRange(double[] sorted)
```

### Sample Output

```
===========================================
   Probability & Statistical Distributions
         Programming Assignment - Part 1
===========================================

Dataset (25 values):
115, 182, 191, 31, 196, 1099, 5, 172, 10, 179, ...

(i)   Mean                  = 172.6800
(ii)  Mode                  = 21
(iii) Median                = 172.0000
(iv)  Variance              = 36772.8576
(v)   P20                   = 21.0000
(vi)  P50                   = 172.0000
(vii) Third Quartile (Q3)   = 191.0000
(viii)Second Quartile (Q2)  = 172.0000
(ix)  Third Quartile (Q3)   = 191.0000
(x)   Range                 = 1094.0000
(xi)  Interquartile Range   = 133.0000
(xii) Standard Deviation    = 191.7679
(xiii)Summation of Divisions = 172.6800
```

---

## 🚨 Part 2 — Outlier Detection (`Program2_OutlierDetection.cs`)

### Description

A C# program that checks whether each value in the dataset is an **outlier** or not, using two standard statistical methods.

### Methods

#### ① IQR Method (Tukey's Fences)

A value is considered an **outlier** if it falls outside the fences:

```
Lower Fence = Q1 − 1.5 × IQR
Upper Fence = Q3 + 1.5 × IQR
```

#### ② Z-Score Method

A value is considered an **outlier** if:

```
|Z| > 3     where Z = (x − mean) / stdDev
```

### Sample Output

```
===========================================
        OUTLIER CHECK FOR EACH VALUE
===========================================
#     Value      IQR Outlier     Z-Score      Z Outlier
-------------------------------------------------------
1     115        No              -0.3002       No
2     182        No               0.0484       No
...
6     1099       YES ⚠️           4.8289        YES ⚠️
...

SUMMARY
[IQR Method]    Outliers found (1): → 1099
[Z-Score Method] Outliers found (1): → 1099  (Z = 4.8289)
```

> ⚠️ The value **1099** is clearly an outlier in both methods.

---

## ▶️ How to Run

### Requirements

- [.NET SDK](https://dotnet.microsoft.com/download) (version .10 or later)
- Any C# IDE: **Visual Studio**, **Visual Studio Code**, or **Rider**

### Steps

```bash
dotnet run Program1_Statistics.cs
dotnet run Program2_OutlierDetection.cs

```

---

## 🧠 Concepts Used

- Descriptive Statistics (Mean, Mode, Median, Variance, Std Dev)
- Percentiles & Quartiles (Interpolation Method)
- Outlier Detection (IQR / Z-Score)
- C# LINQ for data manipulation (`GroupBy`, `Sum`, `Average`, `OrderBy`)
- Array sorting and indexing

---
