# Troubleshooting

This document summarizes issues encountered during development and operation, along with the analysis and solutions applied.

---

## 1. Interface Server Response Handling Issue

### 📌 Problem

During integration with the Interface Server, some API responses were not properly displayed in the admin UI.

### 🔍 Cause

The response data from the Interface Server was not always consistent,
and some fields were returned as null or missing.

The initial implementation did not fully handle these edge cases,
which caused errors during data processing.

### 🛠 Solution

* Added validation and null checks for response data
* Implemented default handling for unexpected values
* Refactored response parsing logic in the service layer for consistency

### 📈 Result

* Improved stability in data processing
* Reduced UI errors during operation

### 💡 What I Learned

When integrating with external systems, it is important to anticipate unexpected data formats
and apply defensive programming techniques to ensure system stability.

---

## 2. Data Inconsistency in Query Results

### 📌 Problem

There were cases where the data displayed in the admin UI did not match the actual database records.

### 🔍 Cause

As query conditions became more complex, some conditions were missing or incorrectly applied,
leading to unintended data being retrieved.

Additionally, issues were found in dynamic SQL handling using MyBatis.

### 🛠 Solution

* Reviewed and corrected query conditions
* Refactored MyBatis dynamic query logic for better clarity
* Verified key query functions through test scenarios

### 📈 Result

* Improved accuracy of data retrieval
* Reduced data inconsistency issues during operation

### 💡 What I Learned

Accurate query design is critical for data integrity,
and complex conditions require careful structuring and validation.
