# GST

GST set-up, tax on every sales and purchase document by place of supply, e-invoicing, e-way bills, job work and the monthly and annual return cycle — GSTR-1, GSTR-3B and GSTR-9 — prepared in Turbine and filed on the GST portal.

## How GST works in Turbine

### One set-up, applied everywhere

GST in Turbine is driven by three things you set up once: your company's GSTIN and state, each contact's GSTIN and GST treatment, and each product's HSN/SAC code and tax. From these, every quotation, order, invoice, bill, POS receipt and expense claim gets the right tax automatically.

| Situation | Tax applied |
| --- | --- |
| Customer or vendor in your own state | CGST + SGST |
| Customer or vendor in another state | IGST |
| Export or SEZ supply | IGST, or zero-rated under LUT, by fiscal position |
| Unregistered buyer | GST by place of supply; classified B2CS or B2CL in returns |
| Reverse charge purchase | Tax booked by you as recipient, flagged on the bill |

### The monthly cycle

| Step | Where | Who |
| --- | --- | --- |
| Post all invoices, credit notes and bills | Turbine | Accounts |
| Run month-end GST checks | Turbine | Accounts |
| Prepare GSTR-1 and download the file | Turbine | GST user |
| Upload, review and file GSTR-1 | GST portal | Authorised signatory |
| Review IMS and GSTR-2B | GST portal | GST user |
| Check GSTR-3B against Turbine, pay and file | Turbine and portal | GST user, signatory |
| Record ARN and status in Turbine | Turbine | GST user |

Turbine prepares the data and keeps the records; uploading and filing are always done on the GST portal by the person who signs.

## Setting up GST

### Company

1. **Settings → Users & Companies → Companies** — enter the GSTIN, PAN, full address and **State**. The state decides whether a supply is intra-state or inter-state.
2. For several GST registrations, create one company per GSTIN (see [multi-company](index.md#multi-company)).

### Customers and vendors

On each contact, fill:

| Field | Values |
| --- | --- |
| GST Treatment | Registered Business – Regular, Registered Business – Composition, Unregistered Business, Consumer, Overseas, Special Economic Zone, Deemed Export, UIN Holders |
| GSTIN (Tax ID) | The 15-character GSTIN; the first two digits must match the state |
| State | Must match the GSTIN state code |
| PAN | Needed for TDS and TCS |

A wrong state or GSTIN is the most common cause of wrong tax and wrong return classification.

### Products

- **HSN code** on goods and **SAC code** on services — required on invoices and in the HSN summary of GSTR-1.
- **Customer Taxes** and **Vendor Taxes** — the GST rate (for example GST 18%). Turbine splits it into CGST + SGST or IGST on each document.
- **Unit of measure** — map each unit to its GST UQC under **GST → Configuration → UOM Mapping** (for example Units → NOS, kg → KGS).
- Products with compensation cess, nil-rated or exempt supplies need their own taxes.

## GST on daily documents

### Sales and invoices

GST is applied on quotations, orders and invoices as soon as the customer and products are selected. Invoices are numbered by financial year (for example INV/26-27/0001) and print GSTINs, place of supply, HSN/SAC and tax by rate. See [Sales](sales.md#invoicing) and [Accounting](accounting.md#customer-invoices-and-credit-limits).

### Purchases and vendor bills

1. Enter the supplier's bill number in **Vendor Reference** — it is mandatory and is used to match GSTR-2B.
2. Check the GST on each line; the vendor's state decides CGST + SGST or IGST.
3. Under **Other Info → GST**, set **ITC Eligibility**: Inputs, Capital goods, Input services or Ineligible. A bill left as Ineligible shows its whole ITC as reversed in GSTR-3B.
4. Tick **Reverse Charge** for reverse-charge supplies such as GTA freight or legal services.

### Credit and debit notes

Always create a credit note from its original invoice with **Credit Note**, so the link to the original is kept for GSTR-1 (CDNR / CDNUR).

### Point of Sale and expenses

POS receipts show HSN-wise GST, and B2B sales at the counter can be invoiced with the customer's GSTIN ([Point of Sale](point-of-sale.md)). Expense categories carry GST so input tax on eligible employee claims is not lost ([Expenses](expenses.md)).

## E-invoicing

### Generate the IRN

For businesses above the e-invoicing turnover threshold, B2B invoices, credit notes and debit notes need an Invoice Reference Number (IRN) from the Invoice Registration Portal.

1. Post the invoice as usual.
2. Send it for e-invoicing from the invoice. Turbine submits it with your portal credentials and stores the IRN, acknowledgement number and signed QR code.
3. Print or email the invoice; the QR code and IRN print on it.

Good to know:

- An e-invoice can be cancelled on the portal only within the window the portal allows; after that, issue a credit note.
- Errors returned by the portal (for example an invalid GSTIN or missing HSN) are shown on the invoice. Correct the master data, then resend.
- Your administrator configures the e-invoice credentials; test with the sandbox before go-live.

## E-way bills

### Before goods move

An e-way bill is required for movement of goods above the notified value, and for every inter-state movement to a job worker regardless of value.

1. Open the delivery (or the invoice).
2. In the e-way bill section, enter the transporter, transport mode, vehicle number and distance.
3. Generate the e-way bill before the vehicle leaves. Turbine stores the e-way bill number and validity.
4. Update the vehicle number (Part B) if the goods change vehicles.

Send goods with the **Delivery Challan** printed from the delivery ([Inventory](inventory.md#indian-transport-documents)).

## Job work

### Goods sent without GST

Under Section 143 of the CGST Act, inputs and capital goods can be sent to a job worker without paying GST, on a delivery challan, provided they come back in time.

| Requirement | Turbine |
| --- | --- |
| Rule 55 challan for every outward and return movement | Job work challan with financial-year numbering, GSTINs, HSN, quantity and value |
| Return within 1 year (inputs) or 3 years (capital goods) | Challan ledger tracks quantities sent, returned, consumed and open per line |
| E-way bill for inter-state movement | Generated from the transfer |
| ITC-04 return | Data prepared from the challan ledger and exported |

Goods not returned within the time limit are treated as supplied on the day they were sent, and GST is payable with interest. Review open challans every month. See [Manufacturing — job work](manufacturing.md#subcontracting-and-job-work).

## Month-end GST checks

### Before you prepare a return

- [ ] All customer invoices, credit notes and vendor bills of the month are posted; drafts are not included
- [ ] Every registered customer and vendor has a valid GSTIN, state and GST treatment
- [ ] The place of supply on each invoice is correct
- [ ] Every line has an HSN or SAC code, and every unit is mapped to a UQC
- [ ] Every credit note was created from its original invoice
- [ ] Export invoices carry the shipping bill number, date and six-character port code
- [ ] Cess, nil-rated and exempt items use their own taxes
- [ ] Every vendor bill has ITC Eligibility set
- [ ] Inter-state sales to unregistered buyers above ₹1 lakh per invoice are marked B2CL

## GSTR-1

### Prepare the return in Turbine

You need GST Admin access to create and run returns; GST User access is view-only.

1. Select the company in the company switcher.
2. Go to **GST → GST Tool → GSTR1** and click **New**.
3. Pick the **Period** (for example Oct-2026); the dates fill in. Save.
4. Click **Fetch Invoices**. The month's posted documents are listed with their invoice type: B2B, B2CL, B2CS, CDNR, CDNUR, Export and others.
5. Remove any purchase document from the list with ✕; GSTR-1 holds outward supplies only.
6. Correct any wrong invoice type on the invoice (**Other Info → GST → Invoice Type**). Do this after the last **Fetch Invoices**, because fetching again recalculates types.
7. Click **Generate CSV**. The status moves to **Ready to upload**.
8. Download the files with **Json**, **CSV Files** and **Excel File**, or from **Attachments**.

If an invoice changes after generating, click **Reset**, then **Fetch Invoices** and **Generate CSV** again.

### Review before upload

Compare these tables with Turbine's files before filing:

| Table | What to check |
| --- | --- |
| B2B (4A) | GSTIN, invoice value and tax per invoice |
| B2CL (5) | Inter-state sales to unregistered buyers above ₹1 lakh per invoice |
| Exports (6A) | Shipping bill number, date and six-character port code |
| B2CS (7) | Intra-state and inter-state split; credit notes netted |
| Nil, exempt, non-GST (8) | Not duplicated as 0% B2B lines |
| Credit and debit notes (9B) | Shown as notes with correct amounts and original invoice |
| HSN summary (12) | B2B and B2C tabs filled with valid codes |
| Documents issued (13) | Series and counts of invoices and notes |

### File on the portal and record it

On the GST portal:

1. **Services → Returns → Returns Dashboard** — choose the year and period.
2. On the GSTR-1 tile, click **Prepare Offline** and upload the file from Turbine.
3. If records are rejected, download the error report, correct them in Turbine and upload again.
4. Click **Generate Summary**, compare the totals with Turbine, then **File Statement** with DSC or EVC. Note the ARN.

In Turbine, open the run, click **Upload** and then **Filed**, and log the ARN and filing date in the chatter with the acknowledgement attached. These buttons record the status in Turbine only; they do not contact the portal.

## GSTR-3B

### Check, pay and file

The portal auto-fills GSTR-3B: liability from GSTR-1 and input tax credit from GSTR-2B. Use Turbine's GSTR-3B as your books check.

In Turbine:

1. Confirm **ITC Eligibility** on every vendor bill of the month.
2. Go to **GST → GST Tool → GSTR3B → New**, pick the period and save.
3. Click **Fetch Invoices**, then **Generate Data**.
4. Download the table-wise files (3.1, 3.2, 4 and 5), JSON and Excel.

On the GST portal:

1. In **IMS**, accept, reject or keep pending each supplier document. Documents without action are deemed accepted.
2. Compare Tables 3.1 and 3.2 with Turbine. These values come from GSTR-1; correct any difference through GSTR-1A before filing.
3. Compare Table 4 (ITC from GSTR-2B) with Turbine's Table 4. Differences point to missing, late or ineligible supplier invoices.
4. Pay the tax and file. Record the ARN on the Turbine run with **Upload** and **Filed**.

After filing, post the head-wise GST set-off entry in Accounting as per the filed GSTR-3B.

## GSTR-9 annual return

### Prepare the annual return

Run GSTR-9 once a year, after every GSTR-1 of that year is final.

1. Go to **GST → GST Tool → GSTR-9** and click **New**.
2. Pick the **Fiscal Year**; dates and the financial year label fill in.
3. Set **AATO of Previous FY**: up to ₹20 lakh, ₹20 lakh to ₹5 crore, or more than ₹5 crore.
4. Save and click **Fetch Invoices**.
5. Click **Validate** and clear any errors shown.
6. Click **Generate Data** and review the section lines (Tables 4 to 18) and HSN lines.
7. Download the JSON, CSV and Excel files, compare with the portal's auto-filled values, file on the portal, and record the ARN in Turbine.

## Corrections

### Fixing returns

| Situation | What to do |
| --- | --- |
| Invoice changed after generating | **Reset** the run, correct the invoice, **Fetch Invoices**, **Generate CSV** |
| Invoice type wrong | Change it on the invoice after the last **Fetch Invoices** |
| Document should not be in the return | Remove its row with ✕ before generating |
| Run marked Filed by mistake | Click **Reset**; the run and its documents return to Not Uploaded |
| Late document for a filed month | Create a new GSTR-1 run for that period; only documents not in another run are fetched |
| Error found after GSTR-1 but before GSTR-3B | Correct it in GSTR-1A on the portal |
| Error found after GSTR-3B | Correct it in a later month's return, within the time limit |

An invoice can be in only one GSTR-1 run. If **Fetch Invoices** finds fewer documents than expected, check older runs first.

## Reference

### Menus

| Menu | Purpose |
| --- | --- |
| **GST → Dashboard** | Tiles by invoice type: B2B, B2BUR, B2CS, B2CL, Import, Export, CDNR, CDNUR |
| **GST → Invoice → Customer Invoice / Supplier Invoice** | Posted documents with their GST status |
| **GST → GST Tool → GSTR1, GSTR3B, GSTR-9** | Return runs |
| **GST → Periods → Fiscal Years, Periods** | Return periods |
| **GST → Configuration → Unit Quantity Code, UOM Mapping** | GST unit codes and their mapping |

### Statuses

| Status | Set by |
| --- | --- |
| Not Uploaded | A new run, or **Reset** |
| Ready to upload | **Generate CSV** or **Generate Data** |
| Uploaded to govt | **Upload** button — records the status only |
| Filed | **Filed** button — records the status only |

### GST fields on invoices and bills

| Field | Values |
| --- | --- |
| GST Status | Not Uploaded, Ready to upload, Uploaded to govt, Filed |
| Invoice Type | B2B, B2BUR, B2CL, B2CS, CDNR, CDNUR, Export, IMPS/IMPG |
| Export Type | Regular, Deemed Export, SEZ with payment, SEZ without payment |
| ITC Eligibility | Inputs, Capital goods, Input services, Ineligible |
| Reverse Charge | Ticked for reverse-charge documents |

### Due dates (monthly filers)

| Return | Due |
| --- | --- |
| GSTR-1 | 11th of the next month (QRMP: 13th after the quarter) |
| GSTR-3B | 20th of the next month (QRMP: 22nd or 24th by state) |
| ITC-04 | 25 October and 25 April above ₹5 crore turnover; 25 April otherwise |
| GSTR-9 | 31 December after the year end |

Due dates change by notification; always confirm on the GST portal.

## Administration

### Set-up checklist

- Company GSTIN, PAN and state; one company per GST registration.
- Indian chart of accounts and GST taxes, including cess, nil-rated, exempt and reverse charge.
- Fiscal positions for inter-state, export and SEZ supplies.
- Fiscal years and monthly periods under **GST → Periods**.
- UQC mapping for every unit of measure in use.
- E-invoice and e-way bill credentials, tested in the sandbox.
- HSN/SAC and taxes on every product; GST treatment and GSTIN on every B2B contact.

### Access rights

| Role | Can do |
| --- | --- |
| GST User | View return runs and GST status |
| GST Admin | Create, fetch, generate, reset and mark returns |
| Accountant | Correct invoices, bills and credit notes |

## Troubleshooting

### Common issues

| Message or symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| IGST on a local customer, or CGST/SGST on an out-of-state one | Wrong state or GSTIN on the contact | Correct the contact and recompute taxes | Accounts |
| "Missing required fields" on Fetch Invoices | Period or dates empty | Pick the period and save | GST user |
| Fetch Invoices finds too few documents | Not posted, wrong company, or already in another run | Check company and period; review older runs | GST user |
| Invoice type changed back | Fetch Invoices recalculates types | Change it after the last fetch | GST user |
| JSON unchanged after generating again | A second generate only adds new documents | **Reset**, fetch, generate | GST user |
| "Select the previous financial year AATO bucket before continuing." | GSTR-9 without AATO | Set AATO of Previous FY | GST admin |
| Vendor bill will not save | **Vendor Reference** is mandatory | Enter the supplier's bill number | Accounts |
| Whole ITC shown as reversed in GSTR-3B | Bills left as Ineligible | Set ITC Eligibility on each bill | Accounts |
| No period to pick | Periods not created | Create the fiscal year's periods | Administrator |
| Excel warns the format does not match | File is an older .xls format | Open it as .xls | — |
| Is a run marked Filed in Turbine filed on the portal? | No — the status is set by hand | File on the portal and log the ARN | GST user |
