# Brand Expenditure Tracker and Monthly MIS Report

I made this to practise one part of a brand executive's job that gets talked about a lot but is rarely shown: keeping track of what is actually being spent on each brand, and turning that into a monthly report someone can read in two minutes.

**The data is made up.** The brands (Soap - Brand A, Skincare - Brand B and so on), vendors, invoice numbers and amounts are all invented. I have not used any real company's numbers. The point is the structure and the checks, not the figures.

## What's in the workbook

`brand-expenditure-mis-tracker.xlsx` has five sheets:

| Sheet | What it does |
|---|---|
| Read Me | Short guide, colour legend and assumptions |
| Budget | Monthly budget for 4 brands x 7 activities, April to September 2026 |
| Expense Log | 286 invoices, one row each, with a Check column that flags problems |
| Brand Summary | Budget vs actual by brand and by activity, with an Over budget / Watch / On track flag |
| Monthly Report | Pick a month from the yellow cell to see that month by brand, plus a six-month trend and chart |

The activities are print ads, digital ads, POS materials, trade promotions, sampling, agency fees and packaging design.

## How it works

- Everything on the summary sheets is a formula (mostly `SUMIFS`), so if you add an invoice to the Expense Log the reports update on their own.
- Blue numbers are typed-in inputs, black ones are formulas. The yellow cells are the ones you are meant to change (the month picker and the "Watch" level, which is 90% by default).
- The Check column looks for duplicate invoice numbers and zero or negative amounts. I planted two duplicate invoices in the sample data on purpose, so the check has something to catch. It shows 4 flagged rows, which is two pairs.
- I used data validation (drop-downs) for brand, activity and payment status in the log, because typos in a brand name quietly break a `SUMIFS`.

## What the sample data shows

Over April to September 2026 the total budget was Rs 73.08 lakh and the spend was Rs 65.73 lakh, so about 90% was used.

- **POS Materials** went over budget (about 103%) and **Digital Ads** only just stayed level (about 100%).
- **Print Ads** used only about 72% of its budget, which would be worth asking about. Was it a planned saving or did something get delayed?
- **Soap - Brand A** is the closest brand to its limit at about 95%. Skincare - Brand B sits right at the 90% Watch line.
- About Rs 13.9 lakh is still pending payment, which is the sort of number a finance team would ask about.

## What I would do differently next time

- Add a brand x activity view, because a brand can look fine overall while one activity inside it is badly over.
- Pull real budgets from an actual plan instead of generating them.
- Add a column for approval status, since in real life invoices get stuck waiting for sign-off.

## Tools

Microsoft Excel (formulas, data validation, conditional formatting, charts). Built and checked for formula errors before uploading.

## Using it

Download the `.xlsx` file and open it in Excel. Overwrite the sample rows with your own, or add new rows under the last invoice and copy the Month and Check formulas down.
