---
name: daily-crude-inventory-email
description: Daily email to wmeyer@erpfunds.com: OECD and Cushing crude oil inventory changes vs 5-year averages
---

Compile a daily crude oil inventory report and email it to wmeyer@erpfunds.com via Outlook. Execute these steps:

## Step 1: Cushing, OK crude oil inventories (weekly data)

Fetch the full weekly history of Cushing crude oil stocks (thousand barrels) from EIA:
https://www.eia.gov/dnav/pet/hist/LeafHandler.ashx?n=PET&s=W_EPC0_SAX_YCUOK_MBBL&f=W

From that history compute:
1. Latest weekly level and its date (EIA releases new data Wednesdays ~10:30 AM ET; delayed one day on holiday weeks).
2. Week-over-week change (latest minus prior week), in million barrels.
3. Five-year average for the same calendar week: for each of the 5 prior years, take the observation closest to the same month/day as the latest data point, then average those 5 values.
4. Difference of the latest level vs that 5-year average, in million barrels and percent.

## Step 2: OECD oil inventories (monthly data)

Preferred source: web-search for the latest IEA Oil Market Report highlights (search: "IEA oil market report OECD industry stocks five-year average" and open the newest iea.org/reports/oil-market-report page). Extract the statement of the form "OECD industry stocks rose/fell by X mb in [month] to Y mb, Z mb below/above the five-year average." Report: the monthly change, the level, and the gap vs the 5-year average, plus which month the data covers.

Fallback if IEA is unreachable: use EIA Short-Term Energy Outlook, https://www.eia.gov/outlooks/steo/report/global_oil.php — extract the latest OECD commercial inventory level, recent monthly change, and its stated comparison to the five-year average.

OECD data updates monthly with a lag; always state the data month so it is clear when the number is unchanged from the prior day's email.

## Step 3: Send the email via Outlook COM (PowerShell)

Build a concise HTML email:
- Subject: "Daily Crude Inventory Report — [today's date]"
- Body: a short 2-3 sentence summary up top (draw or build at Cushing, above/below 5-yr avg; same for OECD), then a small table with: metric, latest level, change, 5-yr average, vs 5-yr avg (abs and %), data as-of date. End with source links (EIA page, IEA/STEO report used).

Send with this PowerShell pattern (Outlook COM is confirmed working on this machine with the wmeyer@erpfunds.com account):

$ol = New-Object -ComObject Outlook.Application
$mail = $ol.CreateItem(0)
$mail.To = "wmeyer@erpfunds.com"
$mail.Subject = "Daily Crude Inventory Report — [date]"
$mail.HTMLBody = $html
$mail.Send()

Pass the HTML as a PowerShell here-string. Use -Encoding utf8 if writing any intermediate files.

## Constraints
- If one data source fails, still send the email with the data you have and clearly note what is missing — never skip the send.
- Report numbers in million barrels, one decimal place.
- Do not editorialize on price direction; facts and comparisons only.