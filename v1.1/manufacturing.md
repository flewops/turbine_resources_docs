# Manufacturing

Bills of materials, manufacturing and work orders, component planning, serial and lot traceability, subcontracting, Indian job work and production costing.

## The manufacturing flow

### From demand to dispatch

1. **Demand** — a sales order (make to order), a reordering rule (make to stock) or a planner creates a manufacturing order (MO).
2. **Components** — Turbine reserves components from stock. If something is short, replenishment raises a purchase or a child manufacturing order.
3. **Work orders** — operators run each operation at its work center: start, pause, done.
4. **Produce** — finished goods enter stock, components are consumed and costs are recorded.
5. **Deliver** — the delivery to the customer is released.

### Key terms

| Term | Meaning |
| --- | --- |
| Bill of Materials (BoM) | The recipe: components, quantities, operations and by-products |
| Kit | A BoM that is never manufactured; selling it ships its components |
| Work center | A machine, station or team, with working hours and an hourly cost |
| Operation | One step of the recipe at one work center, with a set duration |
| Manufacturing Order (MO) | The instruction to make a quantity of a product |
| Work Order | One operation of one MO, timed by the operator |
| Backorder | The remaining quantity of a partly finished order |
| Unbuild | Reversing production: finished goods back into components |

## Manufacturing orders

### MO statuses

| Status | Meaning | Next step |
| --- | --- | --- |
| Draft | Created; nothing reserved | Check and click **Confirm** |
| Confirmed | Components reserved, work orders created | Start the first work order, or **Produce All** |
| In Progress | Work has started | Finish the work orders |
| To Close | All work orders finished | Click **Produce All** |
| Done | Finished goods in stock, costs recorded | Nothing; **Unbuild** only to reverse |
| Cancelled | Stopped; reservations released | Nothing |

### Create and produce an MO

1. Go to **Manufacturing → Operations → Manufacturing Orders** and click **New**.
2. Pick the **Product**; the **Bill of Material** fills in. Enter the **Quantity**, **Scheduled Date** and **Responsible**.
3. Check the **Components** tab (each line shows **Available** or **Not Available**) and the **Work Orders** tab.
4. Click **Confirm**. The MO gets its number and **Component Status** shows Available, Expected, Late or Not Available.
5. Run the work orders, or — if you do not time operations — click **Produce All** directly.
6. **Produce All** consumes components, puts finished goods in stock and closes the MO.

### Partial production and splitting

- **Partial production** — type the quantity you are making now in **Quantity** and click **Produce**. Choose **Create backorder** to keep the remainder on a new MO, or **No Backorder** if it will never be made.
- **Split** — gear icon → **Split**, enter **Max Batch Size**, and Turbine creates one MO per batch.

### Header buttons

| Button | What it does |
| --- | --- |
| **Plan** / **Unplan** | Books work orders on the work centers' calendars / removes the booking |
| **Check availability** | Tries again to reserve components |
| **Unreserve** | Releases components for a more urgent order |
| **Produce All** / **Produce** | Produces the full quantity / the quantity typed |
| **Unbuild** | Takes finished goods apart again (Done MOs only) |
| **Update BoM** (red link) | Reloads components and operations after a BoM change |

### Real cost of an MO

The **Overview** smart button lists each component with its unit cost and each operation with the time spent and the work center's hourly cost, then the total and unit cost.

## Work orders for operators

### Run an operation

1. Go to **Manufacturing → Operations → Work Orders** and group or search by your work center.
2. Click **Start** (▶). The status becomes In Progress and the timer runs.
3. Click **Pause** for breaks or interruptions; click ▶ to resume.
4. Click **Done** (✓) when the operation is complete. The next operation changes from Blocked to To Do.
5. When the last work order is finished, the MO becomes **To Close**; the supervisor clicks **Produce All**.

Good to know:

- Components linked to an operation in the BoM are consumed when that operation is done.
- A work order's **Time Tracking** tab shows who worked and when; supervisors correct times there.
- Operations run one after another by default. With **Operation Dependencies** on the BoM, independent operations can run in parallel.
- Operators work from the Work Orders list on a PC, tablet or phone at the workstation.

## Components and replenishment

### When components are short

1. The MO shows **Not Available** on short components and the **Component Status** at the top.
2. Open **Inventory → Operations → Procurement → Replenishment**. The **To Reorder** filter lists products whose forecast falls below the minimum.
3. Click **Order**. Turbine creates one RFQ per vendor, or a child MO for components that have their own BoM.
4. Confirm the purchase and receive the goods. Turbine reserves them on the MO automatically; if not, click **Check availability**.

### Make to order

With the **Replenish on Order (MTO)** route on a product, confirming a sales order creates an MO for that quantity, linked to the sale through the **Sale** smart button. Assign a **Responsible** planner to automatically created MOs.

## Lots and serial numbers

### Produce tracked products

1. Confirm the MO. A **Lot/Serial Number** field appears with **Generate Serial**.
2. Click **Generate Serial**, enter the first number and the count, then **Generate**.
3. Choose **Apply** to keep one MO for all units, or **Prepare MO** to create one MO per serial number.
4. For lot-tracked components, click **Details** on the line to confirm which lot was used.
5. Click **Produce All**. The **Traceability** smart button shows each unit with the component lots it used.

Every serial number can later be traced from **Manufacturing → Products → Lots/Serial Numbers** to its sales, purchases and repairs.

## Exceptions

### Scrap, wrong consumption, unbuild and cancel

| Situation | What to do |
| --- | --- |
| Damaged part during production | MO gear → **Scrap**, choose product, quantity and **Scrap Reason**; tick **Replenish Quantities** to reorder |
| Used more or less than the BoM | Type the real quantity in **Consumed**; a **Consumption Warning** lets you **Confirm** or **Set Quantities & Validate** |
| Planned quantities must change | gear → **Lock/Unlock** (if permitted), edit, lock again |
| Wrong product or quantity produced | **Unbuild** the done MO; components return to stock |
| Order no longer needed | **Cancel**; reservations are released |
| By-products | Produced automatically with the MO when defined on the BoM |

Whether the consumption warning appears depends on the BoM's **Flexible Consumption**: Allowed, Allowed with warning, or Blocked (only a manager can close the MO).

## Quality during production

### In-process inspection

Build inspection into the routing: add a check operation such as "Final Inspection" to the BoM at its own work center. The operator clicks **Done** only when the product passes. Record defects with a **Scrap Reason**, rework faulty units through [repair orders](maintenance.md#repair-orders), and attach photos in the MO chatter. Inspection of incoming and outgoing goods is covered in [Quality](quality.md).

## Engineering changes

### Change a bill of materials

Only Manufacturing Administrators can edit BoMs, operations and work centers.

1. Record the request and reason with **Log note** on the BoM.
2. For a minor fix, edit the BoM in place. For a new version, **Duplicate** the BoM, set **Reference** to a version code (for example V2), edit the copy, and archive the old one when approved.
3. New MOs use the new BoM immediately.
4. Draft and Confirmed MOs show a red **Update BoM** link; open each and click it. MOs in progress keep the old recipe.

## Planning and scheduling

### Plan MOs

- **Plan** on a confirmed MO books each work order on its work center's calendar and updates the scheduled date.
- gear → **Plan based on Components Availability** also takes expected component arrivals into account.
- Daily planning uses MO filters **Late**, **Delayed Production**, **Late Availability**, **Components Available** and **MO Ready**, plus Calendar and Kanban views. Star an MO to mark it urgent.
- **Manufacturing → Reporting → Work Orders** shows expected hours per work center.

### Lead times

| Lead time | Set on | Effect |
| --- | --- | --- |
| Vendor lead time | Product → Purchase tab | Expected arrival of components |
| Manufacturing lead time | BoM → Miscellaneous | Automatic MOs are scheduled that many days earlier |
| Days to prepare MO | BoM → Miscellaneous | MOs are created and confirmed in advance |
| Customer lead time | Product → Inventory tab | Promised delivery date on sales orders |

## Subcontracting and job work

### Subcontracting

An outside company makes the product for you: you order it on a purchase order, and when it arrives, Turbine records the production and component consumption automatically.

1. Create a purchase order to the subcontractor for the finished product and confirm it. Turbine creates the receipt and a subcontracting MO behind it.
2. If the subcontractor works with your components, confirming the order also creates a transfer of those components to the subcontractor; validate it when they leave.
3. When the goods arrive, validate the receipt. The subcontracting MO closes and finished goods enter stock.

### Indian job work (GST Section 143)

For goods sent to job workers without payment of GST, Turbine adds the documents the law requires on top of the subcontracting flow:

- **Job work challan** — a numbered challan per financial year for every outward movement, with GSTINs, HSN, quantity and value, printed for consignee, transporter and consigner.
- **Challan ledger** — tracks quantities sent, returned, consumed and still open per challan line, including partial returns over several receipts.
- **ITC-04** — the return data for goods sent to and received from job workers, exported for filing.

Find these under the **Job Work** menu in Inventory. Goods not returned within the legal time limit (one year for inputs, three years for capital goods) are treated as supplied; review open challans regularly.

## Reports

### Management questions

| Question | Report |
| --- | --- |
| What does one unit cost, and can we build it now? | **BoM Overview** on the BoM (turn on **Forecast**) |
| What did this MO really cost? | **Overview** on the MO |
| Do operations take longer than planned? | **Reporting → Work Orders** — expected vs real duration |
| How productive are the machines? | **Reporting → Overall Equipment Effectiveness** |
| Which lot went where? | **Traceability** on the MO or lot |
| What will stock be next week? | **Forecasted** on the product |

## Administration

### Set-up order

1. Users and access rights.
2. Manufacturing, Inventory, Purchase and Sales settings.
3. Warehouse steps for receipts, deliveries and manufacturing (1, 2 or 3 steps).
4. Units of measure and product categories with their costing method.
5. Products: components with vendors, prices and lead times; then finished products.
6. Work centers with working hours and cost per hour.
7. Bills of materials with operations and by-products.
8. Reordering rules for components.
9. Opening stock through a physical inventory.
10. An end-to-end test: sale → MO → purchase → receipt → production → delivery.

### Manufacturing settings

| Setting | Purpose |
| --- | --- |
| Work Orders | Operations, work centers and timed work orders |
| Work Order Dependencies | Parallel operations defined on the BoM |
| Subcontracting | Subcontracting BoMs and flows |
| By-Products | Secondary outputs on BoMs |
| Unlock Manufacturing Orders | Lets users change planned quantities without unlocking |
| Allocation Report | Shows which orders a production is promised to |

### Work centers

**Manufacturing → Configuration → Work Centers**: name and code, **Working Hours**, **Time Efficiency**, **OEE Target**, **Setup Time** and **Cleanup Time**, **Cost per hour** and **Alternative Workcenters**. Cost per hour drives the labour part of product cost.

### Access rights

| Action | Manufacturing User | Manufacturing Administrator |
| --- | --- | --- |
| Create, process and cancel MOs and work orders | Yes | Yes |
| Read BoMs, work centers and operations | Yes | Yes |
| Create or edit BoMs, work centers and operations | No | Yes |
| Change Manufacturing settings | No | Yes |

### Costing

A manufactured product costs its components plus its operations (work center time × cost per hour). The BoM Overview shows planned cost; the MO Overview shows actual cost. For Standard Price products, click **Compute Price from BoM** after a BoM or price change. Compare MO and BoM overviews monthly to spot variances.

## Troubleshooting

### Common issues

| Symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| Start button missing on a To Do work order | The work center is marked as down | Ask the administrator to release it, or move the work order to another work center | Planner |
| Work order shows Blocked | Waiting for the previous operation | Finish the earlier operation | Operator |
| Components Not Available | Not enough stock to reserve | Replenish, receive, then **Check availability** | Planner |
| Cannot change To Consume | Confirmed MOs are locked | gear → **Lock/Unlock** if permitted | Supervisor |
| Sale did not create an MO | Product has no MTO route or no BoM | Add the route and BoM | Administrator |
| "Missing a way to be replenished" | No vendor and no BoM on the product | Add a vendor line or a BoM | Administrator |
| Cannot edit a BoM | User has Manufacturing User access | Ask the Manufacturing Administrator | — |
| Red **Update BoM** link on an MO | The BoM changed after the MO was created | Check the MO and click **Update BoM** | Planner |
