# Point of Sale

GST-ready counter billing in any browser — PC, tablet or phone — that keeps working when the internet drops, with loyalty, discounts, multiple payment modes and cash control.

## Sessions

### Open a register

1. Go to **Point of Sale → Dashboard**. Each card is a shop or counter.
2. Click **Open Register**. If cash control is on, count the opening cash and confirm.
3. If employee login is enabled, select your name and enter your PIN.

### Close the register

1. Use **Cash In/Out** during the day for petty cash movements, with a reason.
2. At day end, click **Close Register**. Count the cash and review card and UPI totals.
3. Confirm. Turbine posts the session's journal entry in Accounting and prints the session report.

## Selling

### Make a sale

1. Tap products, search by name or barcode, or scan with a barcode scanner.
2. Change quantity, price or discount with the keypad (**Qty**, **Price**, **%**). Price changes may need a manager PIN.
3. Select a **Customer** to apply their pricelist and loyalty, or to issue a GST invoice.
4. Click **Payment** and choose one or more methods — Cash, Card, UPI, Online Payment or Customer Account.
5. Tick **Invoice** if the customer needs a tax invoice (a customer GSTIN is required for B2B).
6. Click **Validate**, then print or email the receipt.

Receipts show HSN-wise GST and your company GSTIN.

### Offline billing

If the connection drops, keep billing. Orders are stored on the device and synchronise automatically when the internet returns.

### Discounts, loyalty and coupons

- **Line discount** — select a line, press **%** and type the percentage.
- **Global discount** — press **Discount**; the default percentage is set per shop.
- **Loyalty and rewards** — after selecting the customer, eligible rewards appear; click **Reward**.
- **Coupon or promo code** — click **Enter Code**.
- **Gift card** — sell the gift card product; redeem by entering its code at payment.

### Refunds and exchanges

1. Click **Orders** (or **Refund**) and find the original order by receipt number or customer.
2. Select the lines and quantities to return and click **Refund**.
3. Pay the customer back, or add new items for an exchange, then validate.

### Customer credit

Choose **Customer Account** as the payment method to sell on credit to a known customer. The amount appears in the customer's receivables and can be settled later from the counter or from Accounting.

### Sales orders and repairs at the counter

Use **Quotation/Order** to load a sales order or repair order and collect a down payment or the full amount. **Ship later** lets the warehouse deliver goods after the sale.

## Reports

### Store reporting

- **Reporting → Orders** — sales by shop, product and cashier in pivot or graph view.
- **Reporting → Sales Details** — period summary (Z-report style).
- **Reporting → Session Report** — per-session totals by payment method.

Each closed session posts one summarised journal entry (sales by tax, payments by method); invoiced orders create individual invoices. Reconcile card and UPI settlements against the bank statement.

## Administration

### Shop configuration

**Point of Sale → Configuration → Settings**, choosing the shop at the top:

| Setting | Recommendation |
| --- | --- |
| Payment methods | One cash method per shop; UPI and card on bank journals |
| Pricelists | Enable if you have retail, wholesale or festival prices |
| Restrict categories | Show only relevant product categories per shop |
| Cash control and maximum difference | On, with a limit |
| Employee login | On for multi-cashier counters |
| Restrict price modification | Managers only |
| Global discount | Set the default percentage |
| Receipt header and footer | Company GSTIN, address, return policy |
| Invoicing | Allow tax invoices from the counter |
| Cash rounding | Round totals to ₹1 |

### Products

Mark products **Available in POS**, assign a POS category, and set HSN code, GST taxes and barcode. Use combo products for meal deals and attributes for size and colour variants.

### Hardware

- USB barcode scanners work without set-up.
- Receipts print through the browser; network receipt printers can be added under **Configuration → Printers**.
- The cash drawer opens through the receipt printer.

### Access rights

| Role | Can do |
| --- | --- |
| POS User | Open sessions, sell, refund |
| POS Administrator | Configure shops, close any session, view all reports |

## Troubleshooting

### Common issues

| Symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| Cannot change a price | Price changes restricted to managers | Manager enters PIN | Cashier |
| Invoice option missing | Invoicing not enabled for the shop | Enable invoicing in shop settings | Administrator |
| Session will not close | Cash difference above the allowed limit | Recount; manager approves the difference | Manager |
| Wrong GST on receipt | Product HSN or tax set incorrectly | Correct the product | Administrator |
| Product missing at the counter | Not available in POS, or category restricted | Mark it available and check categories | Administrator |
