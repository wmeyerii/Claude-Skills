# ERP Data Extraction & Structuring Tool

This resource guides extraction and analysis of data from enterprise resource planning systems used in real estate and industrial operations.

## Key Supported Systems
Yardi, MRI Software, SAP, JD Edwards, and NetSuite, along with smaller solutions like AppFolio and RealPage.

## Primary Use Cases
General ledger pulls for month-end closing, tenant rent roll extraction, accounts payable/receivable aging analysis, cost center reporting, fixed asset inventory, and data preparation for financial models.

## Extraction Process

1. **Identify the report type** — determine which module contains needed data (GL, AP, AR, budget, fixed assets, or payroll)

2. **Clean raw data** — remove embedded subtotals, standardize dates to YYYY-MM-DD format, normalize debit/credit amounts, flag duplicate transactions, and identify missing account codes or unmapped cost centers

3. **Structure output** — organize results as summary pivots, exception lists, and analysis-ready tables

4. **Run analyses** — calculate GL variances, AP aging buckets, tenant delinquency, operating expense ratios, and cash flow bridges

## System-Specific Guidance
Yardi users should treat property codes as the joining field. SAP users should reference cost center mapping and transaction codes. MRI users need to confirm which accounting book (GAAP, tax, or cash) to extract.
