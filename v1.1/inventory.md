# Inventory

Receipts, deliveries, batch dispatch, returns, replenishment, lots and expiry, landed costs and Indian transport documents — with every movement valued and traceable.

## How goods move

### Transfers

Every movement in Turbine is a transfer that someone validates. Receipts bring goods in, deliveries take them out, and internal transfers move them between locations. Stock in between carries the lot, serial number, expiry date and value of every unit.

| Transfer | Created by | Validated by |
| --- | --- | --- |
| Receipt | Confirmed purchase order | Stores |
| Delivery | Confirmed sales order | Dispatch |
| Internal transfer | Multi-step routes, putaway or manual moves | Stores |
| Return | The original receipt or delivery | Stores |
| Dropship | Sales order on the Dropship route | Purchase / dispatch |

## Receiving goods

### Receive a vendor delivery

1. Go to **Inventory → Operations → Transfers → Receipts** and open the receipt. The vendor and purchase order number are shown on it.
2. Check each line's **Quantity** against what arrived; change it if less came in.
3. For lot-tracked products, enter a **Lot/Serial Number** per lot and split the line if several lots arrived. For products with expiry, confirm the **Expiration Date** of each lot.
4. For serial-tracked products, enter one serial number per unit.
5. Click **Validate**. Choose **Create Backorder** to keep the remainder open, or **No Backorder** to close it.

### Two- and three-step receipts

With multi-step receiving, the receipt moves goods only to the Input area. The **Quality Control** and **Storage** transfers that follow appear under internal transfers; validate each in turn.

Good to know:

- Putaway rules decide the shelf: a product category with a putaway rule is stored on its rack automatically.
- If a lot's removal date has already passed, Turbine asks you to confirm before validating. Check the expiry date before you accept.
- With average costing, a product's cost updates to the purchase price when it is received.
- GST on the purchase comes from the purchase order, not the receipt.

## Delivering goods

### Pick, pack and deliver

A confirmed sales order creates its delivery and reserves stock immediately — earliest expiry first for products on FEFO.

1. Go to **Inventory → Operations → Transfers → Deliveries** and open the delivery. If stock is short, the delivery waits; click **Reserve** again after new stock arrives.
2. Check the reserved lots and serial numbers.
3. To pack, select the lines and click **Put in Pack**. Turbine creates a package and calculates its weight.
4. Click **Validate**. If you ship less than ordered, choose **Create Backorder**; the remainder stays open and is reserved automatically when stock arrives.
5. Print the **Delivery Slip** from **Print**. It shows packages, weights, lots and expiry dates.

With pick-pack-ship, the order creates the **Pick** first; validating it creates the **Pack**, and validating the Pack creates the **Delivery Order**.

Good to know:

- The customer's GST and place of supply come from the sales order; the delivery needs no tax work.
- **Signature** captures the customer's sign-off on the delivery when the setting is on.
- Selling in packs works: 3 boxes of 10 on the order become a delivery of 30 units.

### Batch dispatch with a vehicle

Group the deliveries leaving on one vehicle into a batch, so the driver gets one list and you validate them together.

1. Go to **Inventory → Operations → Jobs → Batch Transfers** and click **New**, or select deliveries in the list and use **Add to batch**.
2. Add the deliveries and set the **Vehicle** and **Driver**. Turbine shows the vehicle's payload and how much of it the batch uses.
3. Click **Confirm**, pick the goods, then **Validate** to complete every delivery in the batch.
4. Print the **Batch Transfer** report for the driver.

Vehicles and their capacities come from [Fleet](fleet.md).

## Returns

### Customer and vendor returns

A return is always created from the original transfer, so the lot, serial number and sales or purchase order stay linked.

1. Open the validated delivery (or receipt) and click **Return**.
2. Enter the quantity coming back on each line, or click **Return All**.
3. Validate the return when the goods arrive. The order's delivered quantity drops, so a credit note can follow.
4. To replace goods instead of refunding, use **Exchange** on the return; Turbine creates a new delivery for the same items.

Customer-requested returns from the portal are logged on the sales order; nothing reaches stock until the return above is created and validated. **Reporting → Returns** lists every return.

## Replenishment

### Three ways to refill stock

**Reordering rules** for stocked items:

1. Open **Operations → Procurement → Replenishment**. Each line shows a product, its Min and Max, the forecast and the suggested quantity.
2. Add a rule with **New**: product, location, Min and Max.
3. Click **Order** to raise the RFQ now, or **Automate** to let the nightly scheduler order for you. **Snooze** hides a line for a while.

**Replenish on Order (MTO)** for items bought or made per order: each sales order line raises its own purchase or manufacturing order.

**Dropship** for items you never hold: the vendor ships straight to the customer.

Good to know:

- A suggested quantity also covers quantities already promised to customers. Check the **Forecasted** report before ordering.
- The vendor, price and lead time come from the product's **Purchase** tab.

## Counting and scrapping

### Physical count

1. Open **Operations → Adjustments → Physical Inventory** and filter by location or product.
2. Type what you counted in **Counted Quantity**; the difference shows beside it.
3. Click **Apply** on the line, or **Apply All**, and give the count a reference. Differences post as inventory gains or losses.
4. A manager can use **Request a Count** to assign a count to a person and date.

Counted quantities do nothing until applied; **Clear** discards a count.

### Scrap

1. Open **Operations → Adjustments → Scrap** and click **New**, or click **Scrap** on a transfer.
2. Choose the product, quantity, location and — for tracked items — the lot or serial number. Add a **Scrap Reason**.
3. Click **Confirm**. Stock and its value fall immediately.

## Lots, serial numbers and expiry

### Traceability

Every lot and serial number keeps its full history, from vendor receipt to customer delivery. Open **Products → Lots / Serial Numbers**, search the lot, and click **Traceability** to see every receipt, transfer, production and delivery it passed through.

### Expiry dates

| Date on the lot | Meaning | Set on the product as |
| --- | --- | --- |
| Expiration Date | Goods must not be used after this day | Days after receipt |
| Best Before Date | Quality starts to decline | Days before expiry |
| Removal Date | Remove the lot from saleable stock; deliveries warn after it | Days before expiry |
| Alert Date | Turbine creates a follow-up activity for the lot | Days before expiry |

Good to know:

- Best Before, Removal and Alert are counted backwards from expiry. Entering them as days after receipt makes fresh lots look expired.
- FEFO (first expiry, first out) is set on the product category or location.
- Lot and serial numbers can print on delivery slips and invoices, and as GS1 barcodes on labels.

## Landed costs

### Add freight and duty to product cost

1. Open **Operations → Adjustments → Landed Costs** and click **New**.
2. Select the receipts under **Transfers**.
3. Add a cost line with a landed-cost service product and choose how to split it: Equal, By Quantity, By Current Cost, By Weight or By Volume.
4. Click **Compute** to see each product's share, then **Validate**.

Only units from those receipts still in stock are revalued; units already sold keep their old cost. Book landed costs soon after the receipt.

## Indian transport documents

### Delivery challan

On any delivery, use **Print → Delivery Challan**. It shows both GSTINs and PANs, the states, each item's HSN code, quantity and value, with copies marked for consignee, transporter and consigner. A delivery slip is not a delivery challan — send goods with the challan.

### E-way bill

Once your administrator has connected your GST portal credentials, deliveries carry an e-way bill section. Generate the e-way bill before the goods leave.

### Job work challans

Goods sent to job workers move on job work challans with their own financial-year numbering, and returns are tracked against each challan. See [Manufacturing — job work](manufacturing.md#subcontracting-and-job-work).

## Reports

### Stock reports

| Report | Answers | Where |
| --- | --- | --- |
| Stock | Quantity on hand and value per product | Reporting → Stock |
| Stock by Location | What sits in each warehouse, rack and package | Reporting → Stock by Location |
| Moves History | Every completed movement, with lot, from, to and user | Reporting → Moves History |
| Moves Analysis | Movement quantities in pivot and graph views | Reporting → Moves Analysis |
| Returns | Every return transfer | Reporting → Returns |
| Forecast | Expected stock by date with incoming and outgoing documents | **Forecasted** button on the product |
| Traceability | The full path of one lot or serial number | **Traceability** button on the lot |

Every list can be grouped, filtered and exported to Excel.

## Administration

### Warehouse configuration

**Inventory → Configuration → Warehouses**:

| Field | Options |
| --- | --- |
| Incoming Shipments | 1 step (receive), 2 steps (receive then store), 3 steps (receive, quality control, store) |
| Outgoing Shipments | 1 step (deliver), 2 steps (pick then deliver), 3 steps (pick, pack, deliver) |
| Buy / Manufacture to Resupply | Creates the buy and manufacture rules for the warehouse |
| Resupply Subcontractors | Allows sending components to subcontractors |

### Settings to review

Lots & Serial Numbers, Expiration Dates, Storage Locations, Multi-Step Routes, Units of Measure & Packagings, Packages, Replenish on Order (MTO), Dropshipping, Landed Costs, Batch Transfers, Delivery Signature and Customer Returns.

### Costing and valuation

The product category sets the **Costing Method** — Standard Price, FIFO or Average Cost (AVCO) — and whether valuation is posted automatically. Decide this before go-live: changing it later revalues stock.

## Troubleshooting

### Common issues

| Symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| Expiry warning on a fresh lot | Best before, removal or alert days entered as days after receipt | Re-enter them as days before expiry | Administrator |
| Delivery stays Waiting | Not enough stock, or an MTO purchase not yet received | Receive the goods, then **Reserve** | Stores |
| Wrong lot reserved | Category removal strategy is FIFO, not FEFO | Set FEFO on the category or location | Administrator |
| No quality step on receipts | Warehouse set to 1-step receipts | Change Incoming Shipments on the warehouse | Administrator |
| Reorder suggestion seems too high | It includes quantities already promised to customers | Check the forecast before ordering | Planner |
| Landed cost did not change product cost | Those units were already sold | Expected; book landed costs promptly | Accounts |
| Lots missing from delivery slip | Lot display on delivery slips is off | Turn it on in Inventory settings | Administrator |
| Another warehouse's transfers not visible | That company is not selected | Tick the company in the company switcher | User |
