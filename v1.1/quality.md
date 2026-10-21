# Quality

Inspection plans for incoming and outgoing goods, automatic quality alerts on transfers, pass/fail test sheets and a hard stop on goods that fail.

## How inspection works

### The inspection cycle

1. A quality manager defines **measures** — what to check on a product, and on which operation (receipts, deliveries).
2. When a transfer containing that product is confirmed — for example when a purchase order is confirmed — Turbine creates a **quality alert** for it automatically.
3. The inspector generates the test sheet, enters results and attaches evidence.
4. The transfer cannot be validated until every alert on it has **Passed**.

### Types of check

| Type | How it is graded |
| --- | --- |
| Quantitative | A measured value; passes if it lies between the Min and Max (inclusive) |
| Qualitative | Satisfied or Unsatisfied |

## Inspecting goods

### Inspect a vendor receipt

1. Open the receipt from **Inventory → Operations → Transfers → Receipts**, or go to **Quality → Quality Assurance → Quality Alerts**.
2. Click the **Quality Alerts** smart button and open the alert (status **Waiting**).
3. Click **Generate Tests**. One line appears per measure; each starts as Failed until a result is entered.
4. For quantitative lines, enter the measured value. For qualitative lines, choose **Satisfied** or **Unsatisfied**.
5. Attach photos or the vendor's test certificate in the chatter and save.
6. When the alert shows **Passed**, return to the receipt and click **Validate**.

Deliveries with controlled products follow the same steps before dispatch.

### When goods fail

- The alert shows **Failed**, and validating the transfer gives "There are items failed in quality test". The whole transfer is held, including lines that were not inspected.
- Inform the purchase team with an activity on the alert.
- Agree the action with the quality manager: return to the vendor (**Return** on the receipt), scrap, or send for rework through a repair order.
- Never change a measured value to force a pass; every change is recorded in the chatter.

### Messages you may see

| Message | Meaning | Action |
| --- | --- | --- |
| There are items still in quality test | An alert is still Waiting | Complete the tests |
| There are items failed in quality test | An alert has Failed | Escalate to the quality manager |

## Supporting tools

### Traceability, calibration and rework

- **Lots and expiry** — inspected goods are tracked by lot or serial number with expiry and best-before dates ([Inventory](inventory.md#lots-serial-numbers-and-expiry)).
- **Gauge calibration** — register measuring instruments as equipment and schedule preventive calibration in [Maintenance](maintenance.md).
- **Rework** — send rejected goods for repair with a [repair order](maintenance.md#repair-orders).
- **In-process checks** — add an inspection operation to the bill of materials ([Manufacturing](manufacturing.md#quality-during-production)).

## Administration

### Who does what

| Role | Access | Can do |
| --- | --- | --- |
| Storekeeper | Inventory User | See alerts and tests on a transfer; cannot enter results |
| Inspector | Quality User | Generate tests, enter results, attach evidence |
| Quality manager | Quality Manager | Everything above, plus maintain measures |

Keep each inspector to one company in multi-company databases.

### Create a measure

**Quality → Configuration → Measures**:

| Field | Rule |
| --- | --- |
| Name | What is checked, with its unit — for example "Width (mm)" |
| Product | The product to inspect; one product per measure |
| Type | Quantitative (with Min/Max) or Qualitative |
| Min / Max | Tolerance band, inclusive (quantitative only) |
| Trigger On | Operation types, for example Receipts and Delivery Orders |

Archive a measure to stop new alerts; existing alerts are kept.

### Warehouse set-up

Use **1-step receipts** on warehouses that receive inspected products. Alerts are created on the transfer that is confirmed from the order; a separate quality-control step in a multi-step receipt does not create its own alert.

### Rollout steps

1. List the products that need inspection, their parameters, tolerances and the operation (receipt or delivery).
2. Set inspected warehouses to 1-step receipts; turn on Lots & Serial Numbers if goods are traced.
3. Import measures: one row per product × parameter.
4. Assign Quality User to inspectors and Quality Manager to the quality head.
5. Test a pass, a fail, a mixed receipt and a delivery with real products.
6. Agree the failed-goods procedure (return, scrap or repair) in writing and train inspectors.

## Troubleshooting

### Common issues

| Symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| No alert on a receipt | Product has no measure for Receipts, or the receipt is still draft | Add the measure; confirm the receipt | Quality manager |
| No alert on the quality-control step | Multi-step receipt in use | Use 1-step receipts for inspected products | Administrator |
| Storekeeper cannot enter results | Has Inventory access only | Give the inspector Quality User | Administrator |
| Good lines held with a failed line | A failed alert holds the whole transfer | Agree the action with the quality manager; return or scrap the failed goods | Quality manager |
