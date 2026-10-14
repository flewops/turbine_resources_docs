# Inventory

Warehouses, stock moves and replenishment. New in v2.0.

## Warehouses

### Set up locations

Create warehouses and storage locations before receiving stock.

![A warehouse with racks and locations](images/inventory-warehouse.jpg "Warehouse locations")

### Receive goods

1. Open the receipt created from the purchase order.
2. Scan or enter received quantities.
3. Validate — stock is updated immediately.

## Replenishment

### Reorder rules

Set a minimum and maximum quantity per product and location. When stock drops below the minimum, Turbine creates a draft purchase order.

```text
Product: Steel bracket
Location: WH/Stock
Min: 50   Max: 200
```

> Inventory is not available in v1.1. Switch the version to v1.1 to see how the Resources page handles a missing app.
