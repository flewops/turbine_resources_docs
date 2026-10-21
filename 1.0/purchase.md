# Purchase

Requests for quotation, purchase orders, vendor prices and lead times, receipts and vendor bill control — linked to stock and production demand.

## Purchase flow

### From demand to vendor bill

| Stage | Document | Created by |
| --- | --- | --- |
| Demand | Reordering rule, sales order (MTO / dropship), manufacturing shortage, or manual request | Turbine or buyer |
| Request for quotation | RFQ (P number) | Turbine or buyer |
| Order | Purchase order — same P number | Buyer, on **Confirm Order** |
| Receipt | Receipt transfer | Created automatically; validated by stores |
| Bill | Vendor bill | Accounts, from the order |

## Requests for quotation

### Create an RFQ

1. Go to **Purchase → Orders → Requests for Quotation** and click **New**.
2. Select the **Vendor**. Payment terms and currency come from the vendor record.
3. Add products. **Unit Price** and the expected arrival date come from the vendor line on the product's **Purchase** tab.
4. Click **Send by Email** if the vendor must confirm prices, or **Print RFQ** for a PDF.
5. Click **Confirm Order** when the price is agreed. The status becomes Purchase Order and a **Receipt** smart button appears.

Good to know:

- RFQs raised automatically from reordering rules, manufacturing shortages or make-to-order sales are grouped by vendor: one RFQ per vendor collects several lines.
- GST on the order follows the vendor's state: IGST for an out-of-state vendor, CGST + SGST for a vendor in your state.

### Vendor prices and lead times

Each product's **Purchase** tab holds one line per vendor: **Vendor**, minimum **Quantity**, **Unit Price**, **Currency** and **Lead Time** in days. The first line is the preferred vendor; drag lines to change the order. Keep these current — automatic RFQs use them.

## Receiving goods

### Receive against the order

1. Click **Receive** on the confirmed order, or open the receipt from **Inventory → Operations → Transfers → Receipts**.
2. Count the goods and correct **Quantity** if less arrived.
3. Enter lot or serial numbers for tracked products.
4. Click **Validate**. Choose **Create Backorder** to keep the remainder open, or **No Backorder** if nothing more is coming.

Full receiving steps — lots, expiry dates and multi-step receipts — are in [Inventory](inventory.md#receiving-goods). Inspection of incoming goods is covered in [Quality](quality.md).

## Vendor bills

### Bill control

The product's **Control Policy** decides what can be billed:

| Control policy | Bill quantity | Use for |
| --- | --- | --- |
| On ordered quantities | Everything ordered | Services, advance payments |
| On received quantities | Only what has been received | Stocked goods — prevents paying for goods not received |

Create the bill from the order with **Create Bill**, enter the vendor's invoice number as the **Reference**, and post it. Full bill entry, TDS and payment are covered in [Accounting](accounting.md#vendor-bills-payments-and-cheques).

## Special purchase flows

### Make to order and dropship

- **Replenish on Order (MTO)** — each sales order line raises its own RFQ, even when stock exists. The customer delivery waits for that purchase.
- **Dropship** — confirming the sales order raises an RFQ with the customer as the delivery address. When the vendor ships, validate the dropship transfer; your own stock is never touched.

### Subcontracting and job work

Purchase orders to a subcontractor for a finished product trigger the subcontracting flow described in [Manufacturing](manufacturing.md#subcontracting-and-job-work).

### Blanket orders and purchase agreements

With **Purchase Agreements** turned on, you can record a blanket order with a vendor — agreed products, prices and validity — and raise individual purchase orders against it.

## Reports

### Purchase analysis

**Purchase → Reporting → Purchase** analyses ordered, received and billed quantities and amounts by vendor, product, buyer and month, in pivot or graph view.

## Administration

### Settings to review

| Setting | Purpose |
| --- | --- |
| Purchase Order Approval | Orders above a set amount need a manager's approval before confirmation |
| Lock Confirmed Orders | Prevents edits after confirmation |
| Purchase Agreements | Blanket orders with agreed prices |
| Receipt Reminder | Emails vendors before the expected arrival date |
| Warnings | Shows notes on vendors and products when an order is created |
| Units of Measure | Buy in a different unit from the stock unit |

### Access rights

| Role | Can do |
| --- | --- |
| Purchase User | Create RFQs and orders |
| Purchase Administrator | Approve orders above the limit, configure settings, view reports |

## Troubleshooting

### Common issues

| Symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| RFQ goes to the wrong vendor or price | Vendor lines on the product are outdated or in the wrong order | Update the product's Purchase tab; drag the preferred vendor to the top | Buyer |
| "Missing a way to be replenished" on a product | No vendor line and no bill of materials | Add a vendor line | Buyer |
| Cannot create a bill | Control policy is on received quantities and nothing is received | Receive the goods first | Stores |
| Order stuck "To Approve" | Amount exceeds the approval limit | Purchase manager approves | Purchase manager |
| Wrong GST on the order | Vendor's state or GSTIN is wrong | Correct the vendor record and recompute taxes | Buyer |
