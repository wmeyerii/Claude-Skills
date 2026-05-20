# Data: SQL Queries

Write SQL queries to extract and analyze data from ERP systems used in industrial real estate management.

## Supported Systems
Yardi, MRI Software, NetSuite, SAP, JD Edwards, and custom databases.

## Methodology
1. Clarify business requirement (what decision does this support?)
2. Identify the system, relevant tables, time period, and desired output format
3. Construct and document the query
4. Test on restricted date range before running full extract

## Common Query Templates

**GL Trial Balance by Property**
```sql
SELECT property_code, account_code, account_name,
       SUM(debit_amount) - SUM(credit_amount) AS net_balance
FROM gl_transactions
WHERE period = '[YYYY-MM]'
GROUP BY property_code, account_code, account_name
ORDER BY property_code, account_code;
```

**Current Rent Roll**
```sql
SELECT tenant_name, property_code, suite, sqft,
       monthly_rent, lease_start, lease_end, lease_type
FROM leases
WHERE status = 'ACTIVE' AND lease_end >= CURRENT_DATE
ORDER BY property_code, suite;
```

**AP Aging Buckets**
```sql
SELECT vendor_name, invoice_number, invoice_date, amount,
       DATEDIFF(CURRENT_DATE, invoice_date) AS days_outstanding,
       CASE WHEN DATEDIFF(CURRENT_DATE, invoice_date) <= 30 THEN 'Current'
            WHEN DATEDIFF(CURRENT_DATE, invoice_date) <= 60 THEN '31-60'
            WHEN DATEDIFF(CURRENT_DATE, invoice_date) <= 90 THEN '61-90'
            ELSE '90+' END AS aging_bucket
FROM ap_invoices
WHERE status = 'OPEN'
ORDER BY days_outstanding DESC;
```

## System-Specific Notes
- **Yardi:** Property codes are the primary joining field
- **SAP:** Reference cost center mapping and transaction codes
- **MRI:** Confirm which accounting book (GAAP, tax, or cash) to extract
