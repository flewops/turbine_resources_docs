# Maintenance

An equipment register for machines, tools, vehicles and IT assets; breakdown and preventive maintenance requests; equipment health figures; and repair orders for customer and in-house repairs.

## How a request moves

### Corrective and preventive work

Requests come from a breakdown (corrective) or from a recurring schedule (preventive). They move across the columns as work progresses — New Request → In Progress → Repaired — and close only when the status is set to **Done**. Moving the card to a column alone does not close it.

## Equipment register

### Add equipment

1. Go to **Maintenance → Equipment** and click **New**.
2. Enter the **Name** and **Equipment Category**. The category brings its default technician and any extra fields defined for it.
3. Under **Used By**, choose Department, Employee, Vehicle or Other, and pick which one.
4. Set the **Maintenance Team** and **Technician**; new requests for this equipment get them automatically.
5. **Used in location** — the stock location where it stands.
6. **Product Information** tab — vendor, model, serial number, in-service date, cost and warranty expiry. Cost is visible to Equipment Managers only.
7. **Maintenance** tab — expected MTBF (mean time between failures) in days.

Good to know:

- A serial number can be used only once across all equipment.
- The **Maintenance** smart button on the equipment lists all its requests.

## Reporting a breakdown

### Raise a corrective request

Anyone can raise a request. The team and technician come from the equipment, so the right people are notified immediately.

1. Go to **Maintenance → Maintenance Requests** and click **New**, or use the **Maintenance** button on the equipment.
2. Write a short subject — for example "Spindle overheating, machine stopped" — and pick the **Equipment**.
3. Keep **Maintenance Type** on **Corrective**.
4. Set **Planned Date** to when the breakdown happened or when the work is planned.
5. Set priority with the stars and describe the problem in **Notes**.
6. Save. The creator, the assignee and followers see every update.

If the machine is a production work center, tell the production planner so waiting work orders can be moved to another work center.

## Preventive maintenance

### Recurring schedules

A preventive request marked **Recurrent** creates its own next occurrence when it is done, so one request per routine is enough.

1. Create a request for the equipment and choose **Maintenance Type: Preventive**.
2. Set **Planned Date** and its end to the real slot.
3. Tick **Recurrent**, then set **Repeat Every** (for example 1 Months) and **Forever** or **Until** a date.
4. Write the checklist in the **Instructions** tab.
5. When the work is finished, set the status to **Done**. The next request appears one interval after the planned date, with the same slot and checklist.

Good to know:

- The next date counts from the planned date, not the day you closed it.
- Cancelling a recurring request stops the series.
- Use the same approach for calibration of gauges and measuring instruments.

## Working and closing requests

### Column and status

1. Move the request to **In Progress** when work starts.
2. Log findings in **Notes** or the chatter; attach photos to the chatter.
3. If approval is needed for a part or a stoppage, set the status to **Changes Requested**; the supervisor sets **Approved**.
4. When finished, move it to **Repaired** and set the status to **Done**. Only Done records the close date and counts towards repair-time figures.
5. A machine beyond repair goes to the **Scrap** column; set the equipment's scrap date.
6. **Cancel** a request raised by mistake; **Reopen Request** brings it back.

## Dashboard and equipment health

### Daily view

**Maintenance → Dashboard** shows one card per team with open requests, scheduled, high-priority and unscheduled counts. Click a figure to open those requests. The **Calendar** view shows planned work by day, week or month.

### MTTR and MTBF

| Figure | Meaning |
| --- | --- |
| MTTR | Average days from failure to close, over Done corrective requests |
| MTBF | Days from the in-service date to the latest failure, divided by the number of failures |
| Latest Failure | Planned date of the most recent Done corrective request |
| Estimated next failure | Latest failure plus MTBF |

Preventive requests and corrective requests that are not Done are not counted; record breakdown dates accurately.

### Reports

**Reporting → Maintenance Requests Analysis** groups requests by equipment, category, team, type or status in graph and pivot views.

## Repair orders

### Service and repair with parts and labour

Repair orders handle customer repairs and in-house rework, with spare parts, labour, warranty and billing in one document.

| Status | Meaning |
| --- | --- |
| New | Repair registered; nothing reserved |
| Confirmed | Repair approved; parts reserved or requested |
| Repaired | Work ended; parts consumed from stock |
| Cancelled | Repair abandoned |

1. Go to **Repairs → Orders** and click **New**.
2. Select the **Customer**, the **Product to Repair** and its **Lot/Serial Number** if tracked. Set **Scheduled Date**, **Responsible** and **Tags** (for example Urgent, Walk-in, On-site Service).
3. Tick **Under Warranty** if the customer should not be charged; lines are then created at zero price.
4. On the **Parts** tab, add lines of type **Add** (new part), **Remove** (part taken out) or **Recycle**. **Parts availability** shows Available, Expected or Late.
5. On the **Services** tab, add labour and diagnosis lines.
6. Click **Create Quotation** to send the customer a quote for approval, if required.
7. Click **Confirm Repair**. Parts are reserved; if short, a purchase or manufacturing order is raised according to the part's route.
8. Do the work and click **End Repair**. Parts are consumed and stock updates.
9. Click **Create Invoice**, or bill the repair at the [Point of Sale](point-of-sale.md) counter.

Print **Repair Order** as a job card for the customer to sign at hand-over.

## Administration

### Set-up order

1. **Equipment Categories** — group machines, for example Production Machines, Utilities, Gauges.
2. **Maintenance Teams** — add the users of each team.
3. **Maintenance Stages** — New Request, In Progress, Repaired, Scrap.
4. **Equipment** — one record per machine; match names to work center names.
5. **Preventive schedules** — one recurring request per routine.
6. **Repairs** — repair operation type and locations, tags, spare-part and service products with HSN/SAC and GST.

### Access rights

| Role | Can do |
| --- | --- |
| Maintenance User | Raise and follow own, followed or assigned requests |
| Equipment Manager | See all requests and equipment costs; configure teams and categories |
| Inventory User | Process repair orders |

## Troubleshooting

### Common issues

| Symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| Request in Repaired still counted as open | Status not set to Done | Set the status to Done | Technician |
| Next preventive request not created | Not Preventive, Recurrent not ticked, or not Done | Set Preventive, Recurrent, then Done | Supervisor |
| MTTR or MTBF shows 0 | No Done corrective requests yet | Close breakdowns with Done | Technician |
| Operator cannot see a colleague's request | Users see only requests they created, follow or are assigned to | Add as follower, or give Equipment Manager | Supervisor |
| "Another asset already exists with this serial number" | Serial numbers are unique across equipment | Check for a duplicate equipment record | Administrator |
| Repair parts show Late | Purchase or manufacturing of the part is overdue | Follow up the linked order | Stores |
