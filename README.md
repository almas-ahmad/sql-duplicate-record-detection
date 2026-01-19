# sql-duplicate-record-detection
Real-world SQL use case for detecting duplicate transaction records using aggregation and HAVING clauses to ensure accurate analytics and reporting.
# SQL Duplicate Record Detection

## 📌 Problem Statement
In large transactional systems, duplicate records can lead to incorrect reporting,
double counting, and financial discrepancies. This project identifies duplicate IDs
in a GPS table.

## 🧠 Business Use Case
- Detect duplicate transaction mappings
- Improve data quality and reporting accuracy
- Support finance and reconciliation teams

## 🛠 SQL Logic Used
- GROUP BY aggregation
- COUNT(*) to identify duplicates
- HAVING clause for conditional filtering

## 📄 Query
```sql
SELECT
    id,
    COUNT(*) AS duplicate_count
FROM gps_team.gps_team_blackbuck_fleetapp_gps_wallet_transaction_mapping
GROUP BY id
HAVING COUNT(*) > 1;
