# Fleet

Company vehicles with drivers, statutory contracts (insurance, permits, PUC, fitness, road tax), services, odometer readings and costs — linked to vendor bills and dispatch.

## Menus at a glance

### Where things are

| Menu | Use it to |
| --- | --- |
| **Fleet → Fleet → Fleet** | Add and manage vehicles (Kanban by status) |
| **Fleet → Fleet → Contracts** | Insurance, permits, PUC, fitness, road tax, leasing |
| **Fleet → Fleet → Services** | Repairs, oil changes, tyres, fuel and other service costs |
| **Fleet → Fleet → Odometers** | Odometer readings over time |
| **Fleet → Reporting → Costs / Odometers** | Cost and usage analysis |

## Vehicles and drivers

### Add a vehicle

1. **Fleet → Fleet → Fleet → New**.
2. Choose the **Model**; category, fuel type and capacity come from the model.
3. Enter the **License Plate** and **Chassis Number**.
4. Pick the **Driver (Employee)**; the driver contact fills in.
5. Fill **Order Date**, **Registration Date**, current **Odometer** and **Catalog Value**.
6. Add **Tags** if useful (Pool, Sales, Plant 1) and save.
7. Move the vehicle through statuses in the top bar.

### Change the driver

- **Immediately** — select the new **Driver (Employee)** and save. The change is logged in **Drivers History**.
- **Planned** — set **Future Driver** and **Available From**; on the date, click **Apply New Driver**.

## Contracts and compliance

### Record a contract

1. On the vehicle, click **Contracts → New**.
2. **Type** — Vehicle Insurance, National/State Permit, PUC Certificate, Fitness Certificate, Road Tax or Leasing.
3. Enter **Start Date**, **Expiration Date**, **Vendor** and **Responsible** (required for reminders).
4. Enter **Recurring Cost** and its frequency.
5. Save. Turbine schedules a **Contract to Renew** activity for the responsible person as expiry approaches.

To renew, create a new contract with the new dates, then open the old one and click **Close**.

## Services and costs

### Log a service

1. On the vehicle, click **Services → New**.
2. Choose the **Service Type** (Oil Change, Tyre Replacement, Fuel and so on).
3. Enter dates, **Cost**, **Vendor**, **Odometer** and a description.
4. Move the state New → Running → Done.

### Link vendor bills to vehicles

In **Accounting → Vendors → Bills**, fill the **Vehicle** column on the bill line. On accounts marked as requiring a vehicle, the column is mandatory. After posting, a service record appears on the vehicle, and the **Bills** smart button counts it. Open such services and set the right service type.

### Odometer readings

Update the **Odometer** on the vehicle, or add readings under **Fleet → Odometers**. Record readings at least monthly and at every service.

## Vehicles in dispatch

### Batch deliveries by vehicle

In **Inventory → Operations → Batch Transfers**, pick the **Vehicle** and **Driver**, add delivery orders, and watch weight and volume against the vehicle category's capacity. See [Inventory — batch dispatch](inventory.md#delivering-goods).

## Administration

### Set-up

- Vehicle brands, models and categories with weight and volume capacity.
- Contract types for Indian statutory documents.
- Service types.
- Accounts that require a vehicle on bill lines (fuel, vehicle repairs).

### Access rights

| Role | Can do |
| --- | --- |
| Fleet Officer | Manage vehicles, contracts and services |
| Fleet Administrator | Configure models and types; view cost reports |
