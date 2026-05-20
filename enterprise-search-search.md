# Enterprise Search: Cross-Platform Search

Query across Notion, Google Drive, Gmail, and Slack to locate documents like leases, deal memos, budgets, and correspondence.

## Three-Step Methodology

**Step 1 — Define What You Need**
Specify: document type, relevant property or entity, timeframe, key terms, and file format.

**Step 2 — Platform-Specific Search**
| Document Type | Best Platform | Search Syntax |
|---------------|--------------|---------------|
| Financial models, reports | Google Drive | `type:spreadsheet "[property name]" budget 2024` |
| LP correspondence | Gmail | `from:[LP firm] subject:quarterly` |
| Vendor invoices | Gmail | `from:[vendor] invoice` |
| Deal memos, IC materials | Notion or Drive | Title search + keyword |
| Current rent rolls | Google Drive | `"rent roll" type:spreadsheet` |
| Leases | Drive or DocuSign | Property name + tenant name |

**Step 3 — Cross-Reference Results**
Confirm version authenticity and establish where documents reside for future access.

## Recommended Folder Structure
```
[Property Name]/
  ├── Leases/
  ├── Financial Models/
  ├── Reports/
  ├── Legal/
  └── Due Diligence/
```
