# Sales

Quotations, customer approval, sales orders, deliveries and invoicing — from the first quote to the final invoice, with GST applied by place of supply.

## Quote to cash

### How a sale flows

A quotation becomes a sales order when the customer signs (and pays an advance, if requested) on the customer portal, or when you click **Confirm**. The confirmed order then creates the delivery for the warehouse and drives the invoice. An advance is invoiced first and deducted automatically from the final invoice.

| Stage | Document | Who acts |
| --- | --- | --- |
| Quotation | Quotation (S number) | Salesperson |
| Customer approval | Online signature and optional advance payment | Customer |
| Order | Sales order — same S number | Salesperson |
| Fulfilment | Delivery order | Warehouse |
| Billing | Advance and final invoices | Salesperson / Accounts |

## Creating quotations

### Create a quotation

Start from a quotation template whenever one fits: it brings the lines, terms, validity, signature and advance rules in one click.

1. Go to **Sales → Orders → Quotations** and click **New**.
2. Pick the **Customer**. The pricelist, payment terms, invoice and delivery addresses fill in from the customer record. Check that the **Pricelist** is in INR for an Indian customer.
3. Choose a **Quotation Template** if you have one.
4. Add lines with **Add Line**, or click **Catalog** to add products from a grid of cards. Use **Add Section** to group lines and **Add Note** for text.
5. Save. The quotation keeps the number it receives on creation.

Good to know:

- **Tax Excl. / Tax Incl.** above the lines switches how prices are shown while you work.
- A section with its lines can be saved as a section template and reused.
- A quantity shown in orange with a chart icon means stock will not cover it on the delivery date; hover over it to see the forecast.

### Products with sizes, colours and packs

- For products with variants, picking the product opens a grid: type the quantity for each size and colour and click **Confirm**. Each combination becomes its own line.
- To sell in packs, change the **Unit** on the line to the pack (for example Box of 10). The delivery is created in base units automatically.
- Optional products go in a section marked optional, at quantity 0. The customer can add them when reviewing the quotation online.

## Prices, discounts and promotions

### Where prices and discounts come from

Prices come from the customer's pricelist. Discounts can come from the pricelist, a line, the whole order or a promotion.

- **Pricelist rules** — quantity breaks and customer-specific prices are defined on the pricelist and applied automatically.
- **Line discount** — type a percentage in **Disc.%** on any line.
- **Discount button** (under the lines) — **Global Discount** adds one discount line, **On All Order Lines** writes the percentage on every line, **Fixed Amount** adds a fixed discount line.
- **Promotions** — automatic promotions apply when you click **Reward**.
- **Coupon and discount codes** — click **Coupon Code** and type the code.

Good to know:

- Two order-wide percentage discounts do not add up: the better one replaces the other.
- Margin is shown under the totals as an amount and a percentage; check it before giving a discount.
- Promotions and codes are set up by your sales manager under **Promotions → Discount & Loyalty**.

## Customer approval

### Send the quotation and collect the signature

1. Click **Preview** to see exactly what the customer will see.
2. Click **Send** to email the quotation with its PDF and portal link, or **Download** for the PDF only.
3. On the portal, the customer can change quantities in the optional section, review discounts and click **Sign & Pay**. They type, draw or upload a signature and click **Accept & Sign**.
4. If an advance is required, the customer chooses **Down payment** or **Full amount** and one of the payment methods your company has published.
5. Signed and paid online, the order confirms automatically. Signed but unpaid, it stays a quotation that records who signed and when; confirm it once the money arrives.
6. If the customer clicks **Reject** and gives a reason, the quotation is cancelled and the reason is posted in its chatter.

**Pro forma invoice:** **Send PRO FORMA Invoice** sends a pro forma for customers who must pay before an order is raised.

Good to know: a quotation expires on its **Expiration** date (30 days by default, or as set on the template).

## Orders and delivery

### Confirm and deliver

1. Click **Confirm**. The number stays the same and the status becomes Sales Order. Stock is reserved and a delivery is created for the warehouse.
2. The **Delivery** smart button opens the delivery. The warehouse validates it; you do not need to.
3. For shipping charges, click **Shipping** under the lines and pick a delivery method; a delivery line is added to the order.
4. Products on the **Replenish on Order (MTO)** or **Dropship** route raise a purchase request on confirmation; the **Purchase** smart button shows it.

Good to know:

- Partial deliveries are normal. The delivered quantity on each line updates as the warehouse ships, and the remainder stays on a backorder.
- Set the **Delivery Date** on the order when the customer agrees to a later date than the earliest possible one.
- Your administrator can lock confirmed orders; a sales manager can still **Unlock** them.

## Invoicing

### Create invoices from the order

Each product invoices either what was ordered or what was delivered. **Create Invoice** on the order does the arithmetic, including advances already billed.

1. On a confirmed order, click **Create Invoice**.
2. Choose **Regular invoice** to bill what is due now, or **Down payment** as a percentage or a fixed amount.
3. Click **Create Draft**, check the invoice and post it.
4. For the final invoice, choose **Regular invoice** with **Deduct down payments** ticked.

| Invoicing policy (on the product) | What Create Invoice bills | Use for |
| --- | --- | --- |
| Ordered quantities | Everything on the order, delivered or not | Services, advance billing, made-to-order goods |
| Delivered quantities | Only what the warehouse has shipped | Stocked goods, partial deliveries |

Good to know:

- GST follows the place of supply: a customer in your own state gets CGST + SGST, a customer in another state gets IGST, with no manual tax selection.
- Invoice numbers follow the Indian financial year (for example INV/26-27/0001).
- The **To Invoice** card above the Quotations list shows orders waiting to be billed.

## Warnings and credit limits

### Warnings on customers and products

Warnings appear as banners at the top of the order as soon as you pick the customer or product. They inform but do not block.

- **Customer warning** — a note on the customer's sales warning, such as "Payment overdue — take advance before dispatch".
- **Product warning** — a product's sales note, such as a long lead time.
- **Credit limit** — when the customer's limit is exceeded, the banner shows the limit and the total due including open orders.

Blocking an invoice over the credit limit is handled in [Accounting](accounting.md#customer-invoices-and-credit-limits).

## Customer returns

### Returns requested from the portal

When your company allows it, customers start a return themselves from the order on the portal, within 14 days of delivery by default.

1. The customer opens the order online and clicks **Return**.
2. They choose items and quantities from what was delivered, pick a **Return reason** and click **Continue**.
3. They download and print the return label with your warehouse address.
4. The request appears in the sales order's chatter.
5. The warehouse creates the return from the delivery when the goods arrive (see [Inventory returns](inventory.md#returns)); Accounts then issues the credit note.

Good to know: a portal request on its own changes no stock and no invoice.

## Reports

### Dashboard and analysis

- **Quotations dashboard** — sales orders and revenue for the last 7 days, plus **To Confirm**, **To Deliver** and **To Invoice** cards that filter the list in one click.
- **Reporting → Sales** — revenue, quantity and margin grouped by product, customer, salesperson or month, in pivot, graph or list view.
- **Reporting → Salespersons, Products, Customers** — the same data opened on the matching grouping.

Reporting requires the Sales Administrator role.

## Administration

### Settings to review

| Setting | Purpose |
| --- | --- |
| Quotation Templates | Standard lines, validity, signature and advance rules |
| Online Signature / Online Payment | Customer approval on the portal |
| Discounts | Shows the **Disc.%** column on lines |
| Pricelists | Customer-specific and quantity-based prices |
| Variants and Units of Measure & Packagings | Grid entry and pack selling |
| Lock Confirmed Sales | Prevents edits after confirmation |
| Customer Returns | Lets customers request returns from the portal, with a time limit |

### Access rights

| Role | Can do |
| --- | --- |
| Sales User: Own Documents Only | Create and manage own quotations and orders |
| Sales User: All Documents | See every order in the company |
| Sales Administrator | Configure settings, pricelists and promotions; view reports |

## Troubleshooting

### Common issues

| Symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| Prices shown in dollars for an Indian customer | Customer uses a foreign-currency pricelist | Set the INR pricelist on the customer | Administrator |
| IGST on a local customer, or CGST/SGST on an out-of-state one | Wrong state or GSTIN on the customer | Correct the address and GSTIN, then recompute taxes | Salesperson |
| Create Invoice finds nothing to invoice | Product invoices on delivered quantities and nothing has shipped | Wait for delivery, or bill a down payment | Salesperson |
| Discount column missing | Discounts setting is off | Turn on Discounts in Sales settings | Administrator |
| Customer cannot pay online | No payment method published for the company | Publish a payment provider | Administrator |
| Quotation stays unconfirmed after signing | An advance was required and has not been paid | Confirm once money is received | Salesperson |
| Promotion not applied | Order below the minimum, or Reward not clicked | Click **Reward** after adding the last line | Salesperson |
| Size/colour grid does not open | Product variant selection is not set to grid entry | Set the product to matrix entry | Administrator |
| Cannot edit a confirmed order | Order is locked | Sales manager clicks **Unlock** | Sales manager |
