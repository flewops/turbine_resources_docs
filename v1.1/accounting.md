# Accounting

Customer invoices and credit control, vendor bills and cheque printing, TDS and TCS, bank reconciliation, assets, budgets, follow-ups, GST return preparation, financial reports and period closing — on the Indian financial year.

## The monthly cycle

### Four stages every month

| Stage | Work |
| --- | --- |
| Record | Customer invoices, vendor bills, payments, expenses |
| Reconcile | Import bank statements, match receipts and payments, clear open items |
| Close | Depreciation, revaluation, accruals, checklist, lock date |
| Report and file | Financial statements, GST returns, TDS/TCS records |

## Customer invoices and credit limits

### Post a customer invoice

Most invoices are created from sales orders (see [Sales](sales.md#invoicing)). To create one directly:

1. Go to **Accounting → Customers → Invoices** and click **New**.
2. Pick the customer, set the invoice date and add lines with product, quantity, price and GST tax. CGST + SGST or IGST is applied according to the place of supply.
3. Click **Confirm** to post. If the customer is over its credit limit, the invoice stays in draft and the screen shows the limit and the total due including this invoice.
4. To post over the limit, ask an accounting manager. Their posting goes through and the chatter records that it was posted over the credit limit.
5. Collect payment with **Register Payment**, or let bank reconciliation match the receipt.
6. To reverse an invoice, click **Credit Note**, post it and match it with the invoice.

Good to know:

- The limit is set on each customer; blocking is switched on for the company by your administrator.
- Only invoices are blocked. Quotations and orders still confirm, so check the credit warning on the quotation before dispatch.
- Invoice numbering follows the Indian financial year (for example INV/26-27/0001).

## Vendor bills, payments and cheques

### Enter a vendor bill

1. Go to **Accounting → Vendors → Bills** and click **New**, or use **Create Bill** on the purchase order.
2. Pick the vendor, enter the bill date and the vendor's invoice number as the **Reference**, and add lines with account and GST tax.
3. For a fixed asset, choose an **Asset Category** on the line; the asset is created when the bill is posted.
4. If a line would push a budget over plan, a banner shows planned, actual, this document and the excess. When your company blocks over-budget bills, only an accounting manager can post it.

### Pay by cheque

1. Click **Register Payment**, choose the bank journal and the **Checks** method, and create the payment.
2. On the payment, click **Print Check**, enter the number of the first cheque leaf, and print.
3. To reprint, click **Unmark Sent**, then **Print Check**. To cancel a printed cheque, click **Void Check**.

Good to know:

- Amounts print in Indian words — for example ONE LAKH, TWENTY-FIVE THOUSAND RUPEES AND FIFTY PAISE ONLY — and in Indian digit grouping (1,25,000.50) when the language is English (India).
- Before using a new cheque book, print a test page from **Configuration → Cheque Formats** and check positions against a real leaf.
- The cheque is cleared when its bank statement line is matched.

## TDS and TCS

### TDS on a vendor bill

1. Make sure the vendor has its PAN recorded (**Accounting → Transactions → PAN Entity**, linked on the vendor).
2. On the bill line, add the TDS tax for the section next to the GST tax. The bill total does not change.
3. Click **Pay** and choose **Withhold Only** (deduct now), **Withhold and Pay** (deduct and pay together) or **Payment Only**.
4. Check the base (the amount before GST) and the TDS amount, and set the date. **Create Payment** posts the TDS to TDS Deducted.
5. Pay the balance later; the payment proposes the net amount.

### TDS deducted by a customer

When a customer pays net of TDS, register the receipt with **Withhold and Pay** and add the customer-side TDS tax for the section. The TDS goes to TDS Receivable, to match against Form 26AS later.

### TCS on a sale

Add the TCS tax for the section on the invoice line. TCS is calculated on the value including GST and added to the invoice total.

### TDS and TCS reports

**Reporting → Taxes & Fiscal → Tax Report**, by tax grid, gives TDS and TCS totals by section for the quarter. By tax, it lists each TDS tax with its base and amount.

Good to know: deposit TDS and TCS with the government by challan as a normal payment and keep the challan details on file. The quarterly statements are prepared in the department's utility using these section reports.

## Bank statements and reconciliation

### Import and reconcile

1. On **Accounting → Dashboard**, open the menu of the Bank card and click **Import Statement**.
2. Add the file: CSV or Excel (read with your bank's saved file map), CAMT.053, MT940, OFX or QIF. Lines imported before are skipped.
3. Auto-reconciliation runs after import. It clears lines whose amount and reference match one open invoice or bill, and lines covered by reconciliation models such as bank charges.
4. Click **Reconcile** on the Bank card. Use the filters **To Reconcile**, **To Check**, **Reconciled** and **All**.
5. For each open line, either accept the suggested match, search an invoice, bill or payment under **Match journal items**, post it to an account under **Counterpart**, or apply a reconciliation model. Then **Validate**.
6. To fix a mistake, open the line under Reconciled and click **Undo reconciliation**.
7. To clear an invoice against a payment or credit note without a bank line, use the **Open Items** tab, tick both items and click **Reconcile**.
8. At month-end, print **Accounting → Reconciliation → Bank Reconciliation Statement** for the closing date.

Good to know:

- CSV files carry no balances. Enter the statement's opening and closing balance after import.
- Ask customers to quote the invoice number in the payment remark; auto-matching looks for it.

## Assets and depreciation

### Manage fixed assets

1. **From a bill** — choose the **Asset Category** on the bill line; posting the bill creates the asset.
2. **By hand** — **Assets → New**: name, category, gross value and date; click **Compute Depreciation** to preview, then **Confirm**.
3. Past periods post at once; future entries wait as drafts and post on their dates.
4. During the asset's life, use **Modify Depreciation**, **Pause** / **Resume Depreciation**, and **Sell / Dispose**.
5. **Sell / Dispose** writes off the asset and books the gain or loss. Open the **Disposal Entry** and post it.
6. Print **Reporting → Management → Depreciation Schedule** for a date range.

**Reset to Draft** works only before the first posted entry; after that, use **Modify Depreciation**.

## Budgets

### Plan versus actual

1. **Accounting → Budgets → New** — name, period (for example 1 April to 31 March) and responsible person.
2. Add lines with a **Budgetary Position** (a group of accounts), an **Analytic Account** or both, and the budget amount.
3. Click **Confirm**; an accounting manager clicks **Approve**. Only approved budgets send alerts.
4. Each line shows **Achieved** (actual), **Theoretical** (share of budget expected by now) and the percentage.
5. Click **Audit** on a line to see the journal items behind Achieved.
6. When a line goes over plan, the responsible person receives an **Over budget** activity.
7. At period end, **Copy to Next Period** starts next year's budget; **Split by Period** turns yearly lines into months.

## Customer follow-ups

### Chase overdue receivables

Overdue customers move through the levels of your follow-up plan (for example 7, 21 and 45 days after the due date).

1. **Accounting → Follow-Ups → Follow-ups** lists customers with overdue amounts; **My Follow-ups** shows only yours.
2. Open a customer's **Payment Follow-up** tab: amount due, amount overdue and the reminder due now.
3. Click **Send Reminder**, check the level, attachments, recipients and message, then send.
4. **Print Statement**, **Statement in Excel** and **Send Statement** produce the customer statement.
5. **Log a Call** records a promise to pay.
6. **Send All Reminders** processes every customer due at once.

## Recurring entries

### Recurring payments and recurring bills

- **Recurring payments** (no bill involved): set up a template under **Configuration → Recurring Templates**, then create a plan under **Accounting → Recurring Payments**. A daily job creates each payment on its date; **Skip**, **Create Payment** now or **Stop** as needed.
- **Recurring bills and invoices** (rent, AMC): on the bill, set **Auto-post** to Monthly, Quarterly or Yearly with an end date. The next period's copy is created and posted on its date.

A recurring payment books no expense, GST or TDS — it only moves money. Rent and services with GST or TDS belong on a recurring bill.

## GST returns

### Before you prepare a return

- All invoices, credit notes and bills of the month are posted; drafts are not included.
- Every registered customer and vendor has a valid GSTIN, a state and the right GST treatment.
- The place of supply on each invoice is correct.
- Every product line has an HSN or SAC code, and its unit is mapped to a GST UQC (**GST → Configuration → UOM Mapping**).
- Every credit note was created from its original invoice.
- Export invoices carry the shipping bill number, date and port code.
- Vendor bills have **ITC Eligibility** set (Inputs, Capital goods, Input services or Ineligible).

### Prepare GSTR-1

1. Select the company in the company switcher.
2. Go to **GST → GST Tool → GSTR1** and click **New**. Pick the **Period** and save.
3. Click **Fetch Invoices**. The month's posted documents are listed with their invoice type (B2B, B2CL, B2CS, CDNR, Export…).
4. Remove any purchase documents from the list, and correct invoice types where needed — for example, inter-state sales to unregistered buyers above ₹1 lakh per invoice belong in B2CL. Make corrections after the last **Fetch Invoices**.
5. Click **Generate CSV**. The status moves to **Ready to upload**.
6. Download the JSON, CSV and Excel files from the run.

If an invoice changes after generating, click **Reset**, then fetch and generate again.

### Prepare GSTR-3B and GSTR-9

- **GSTR-3B** — **GST → GST Tool → GSTR3B → New**, pick the period, **Fetch Invoices**, **Generate Data**, and download the table-wise files. Use them to check the portal's auto-filled GSTR-3B, which takes liability from GSTR-1 and ITC from GSTR-2B.
- **GSTR-9** — once a year, after every GSTR-1 of that year is final: **GST → GST Tool → GSTR-9 → New**, pick the fiscal year, set the previous year's turnover bucket, **Fetch Invoices**, **Validate**, **Generate Data** and download.

### File on the portal and record the filing

Filing is done on the GST portal by the authorised signatory: upload the file, review the summary against Turbine's figures, and file with DSC or EVC. Then, on the Turbine run, click **Upload** and **Filed**, and log the ARN and filing date in the chatter. These buttons record the status in Turbine only; they do not contact the portal.

### E-invoicing

For businesses above the e-invoicing threshold, Turbine generates the IRN for B2B invoices once your GST portal credentials are configured. Configure and test with your administrator before go-live.

## Reports and dashboards

### Financial reports

| Report | Where (Accounting → Reporting) | Use |
| --- | --- | --- |
| Balance Sheet, Profit and Loss | Statement Reports | Any period, with comparison |
| Cash Flow Statement | Statement Reports | Cash movement for a period |
| Annual Report | Statement Reports | Statements, prior-year comparatives and notes in one PDF |
| General Ledger, Trial Balance, Journals Audit | Audit | Account detail and balances |
| Partner Ledger, Aged Partner Balance | Partner Reports | Customer and vendor balances, ageing in 30-day buckets |
| Day Book, Cash Book, Bank Book | Daily Reports | Daily registers with running balance |
| Tax Report | Taxes & Fiscal | Tax by tax; TDS and TCS by tax grid |
| Depreciation Schedule, Asset Analysis | Management | Asset values by category |
| Budget Analysis | Management | Budget against achieved |
| Cash Forecast | Management | Opening cash plus expected receipts and payments |
| Excel versions | Dynamic Reports | Trial Balance, P&L, Balance Sheet, General Ledger, Partner Ledger and ageing in Excel |

Finance dashboards cover accounting overview, profit and loss, balance sheet, receivables and payables, bank and cash, assets, budgets, follow-ups and cash forecast.

Select the right company in the company switcher before printing.

## Month-end and year-end closing

### Every month

1. Reconcile bank and cash; print the Bank Reconciliation Statement.
2. Post or delete draft entries, including asset disposals.
3. Update exchange rates and run **Closing → Currency Revaluation** dated the month end.
4. **Closing → Period Closing → New** — pick the month and what to lock when closed.
5. Work through the checklist. Draft entries block closing; unreconciled bank lines, unmatched payments, negative bank balances and possible duplicate bills are warnings; tasks such as accruals, depreciation and tax return must be ticked.
6. Click **Close**. The lock date is set; **Reopen** restores the previous one.
7. File GST returns. Post the head-wise GST set-off as per GSTR-3B.

### At year-end

1. Keep one fiscal year per year under **Configuration → Fiscal Years**, 1 April to 31 March.
2. Close March as above, including revaluation at 31 March.
3. Open **Closing → Year-End Closing** for the year; review earnings to transfer, draft entries and open bank lines.
4. Confirm the closing date, journal and Retained Earnings account, tick **Lock the Fiscal Year**, and **Close**.

Good to know:

- A document dated in a locked period is moved to the first open date. Check the accounting date before posting.
- Treat the **Hard Lock Date** as final: it cannot be moved back.

## Administration

### Set-up checklist

- Company details, GSTIN, PAN and state; fiscal years from 1 April.
- Indian chart of accounts and GST taxes; TDS and TCS taxes by section.
- Bank journals with statement file maps; cheque formats.
- Customer credit limits and the company's credit blocking rule.
- Follow-up levels; budgetary positions; asset categories.
- GST periods and UQC mapping for returns; e-invoice and e-way bill credentials.

### Access rights

| Role | Can do |
| --- | --- |
| Billing | Create and post invoices and bills |
| Accountant | Full daily accounting; cannot post over credit or budget blocks |
| Accounting Manager | Override credit and budget blocks, approve budgets, close periods |
| GST User / GST Admin | View / create and run GST returns |

## Troubleshooting

### Common issues

| Message or symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| "… has reached its credit limit" on Confirm | Dues plus this invoice exceed the limit | Collect a payment, or ask an accounting manager to post | Accountant |
| "… cannot be posted, it goes over budget" | Company blocks over-budget bills | Ask an accounting manager, or raise the budget | Accountant |
| "The format of the file … is not supported" | CSV/Excel with no file map on the journal | Import from the bank card, or pick the file map | Accountant |
| "Every transaction … was already imported" | File imported before | Open the earlier statement | — |
| Cheque words show HUNDRED THOUSAND, not LAKH | Language is not English (India) | Set English (India) on the cheque format | Administrator |
| Nothing to revalue on the closing date | No exchange rate dated before that day | Date the closing rate the day before | Accountant |
| "Mark these tasks as done before closing" | Checklist tasks open | Tick each task, then Close | Accountant |
| Posted entry shows another date | Its date fell in a locked period | Expected; reopen the period if needed | Accounting manager |
| Fetch Invoices finds too few documents | Documents not posted, wrong company, or already in another return run | Check company and period; review older runs | GST user |
