# Turbine v1.0 Documentation

User and administrator guides for every application in Turbine v1.0 — one integrated system for manufacturing, inventory, sales, purchase, accounting with GST, HR and customer management, built for Indian manufacturers and growing businesses.

## Overview

### What Turbine v1.0 covers

Turbine replaces the usual mix of Tally, spreadsheets and separate departmental software with one shared database. When a salesperson confirms an order, the warehouse, production floor, purchasing and accounts see it at the same moment, and Turbine creates the follow-up documents — delivery, manufacturing order, purchase request and invoice — automatically.

### How to use these guides

Each application has its own page. Pages are written for the people who use the application every day, with a short administration section at the end for the person who sets it up.

- Menu paths are written as **App → Menu → Item**, for example **Sales → Orders → Quotations**.
- **Bold text** is a button, field or message exactly as it appears on screen.
- "Good to know" notes describe behaviour that commonly surprises new users.
- Each page ends with a troubleshooting table: the symptom, the cause and who fixes it.

## Applications in this release

### Sales and customers

- [CRM](crm.md) — leads, pipeline, activities and sales forecasting
- [Sales](sales.md) — quotations, online approval, orders, delivery and invoicing
- [Point of Sale](point-of-sale.md) — GST-ready counter billing, online or offline
- [Surveys](surveys.md) — feedback forms, assessments, certifications and survey-to-lead

### Supply chain and manufacturing

- [Purchase](purchase.md) — RFQs, purchase orders, vendor pricing and receipts
- [Inventory](inventory.md) — receipts, deliveries, lots and expiry, replenishment, Indian transport documents
- [Manufacturing](manufacturing.md) — bills of materials, manufacturing and work orders, job work
- [Quality](quality.md) — inspection plans and quality alerts on receipts and deliveries
- [Maintenance](maintenance.md) — equipment register, breakdowns, preventive schedules and repair orders

### Finance

- [Accounting](accounting.md) — invoices, bills, bank reconciliation, TDS/TCS, assets, budgets and closing
- [Expenses](expenses.md) — employee claims, receipts, approvals, reimbursement and travel requests

### People

- [Employees](employees.md) — HR dashboard, employee records, loans, advances, custody and exit
- [Attendances](attendances.md) — check-in, check-out and kiosk mode
- [Time Off](time-off.md) — leave requests, allocations and approvals
- [Payroll](payroll.md) — salary structures, payslip batches and payroll accounting
- [Recruitment](recruitment.md) — job positions, applicant pipeline and interview forms
- [Fleet](fleet.md) — vehicles, drivers, statutory contracts, services and costs

### Services and productivity

- [Project](project.md) — tasks, milestones, timesheets, billing and profitability
- [Documents](documents.md) — company licences and certificates with expiry tracking

## Common basics

### Finding your way around

Every Turbine application follows the same pattern: pick the app from the home screen, pick a menu, find a record in a list, open it, and act with the buttons at the top.

| Screen element | Where | What it does |
| --- | --- | --- |
| Apps icon | Top left | Switches to another application |
| Search box | Top of every list | Finds records as you type; the arrow opens **Filters**, **Group By** and **Favorites** |
| View switcher | Top right of a list | List, Kanban (cards), Calendar, Pivot, Graph and Activity views |
| Status bar | Top right of a document | Shows the stage, such as Draft → Confirmed → Done |
| Smart buttons | Top centre of a document | Open linked records — deliveries, invoices, purchases |
| Chatter | Bottom of a document | **Send message**, **Log note** and **Activity**; keeps the full history of changes |
| Company switcher | Top right | Selects which company's records you are working on |

If a list looks empty, a filter is usually the reason: remove the grey filter chips in the search box.

### Contacts: one master for every application

Customers, vendors, delivery addresses and employees' addresses are all contacts, and every application reads from the same record. Updating a phone number or GSTIN once updates it everywhere.

- For Indian B2B customers and vendors, fill **GST Treatment** (for example Registered Business – Regular) and a valid **GSTIN**. Taxes on orders and invoices, e-invoices and GST returns all depend on these two fields.
- Add separate **Invoice Address** and **Delivery Address** entries under the company; Turbine proposes the right one on each order.
- Merge duplicates from the list view with **Actions → Merge**; documents move to the record you keep.
- Archive contacts you no longer use instead of deleting them, so history stays intact.

### Calendar and activities

Meetings booked from an opportunity, a contact or any document stay linked to that record. Activities (calls, emails, to-dos) appear under the clock icon in the top bar, and overdue activities are shown in red.

### Mobile access

Turbine runs in any modern browser on desktop, tablet and phone. Approvals, check-in, expense claims, maintenance requests and the CRM pipeline work on a phone screen without a separate app.

### Multi-company

One Turbine database can hold several companies — for example, separate legal entities or GST registrations. Tick the companies you need in the company switcher before you print reports or create documents; each document belongs to the company that was active when it was created.

## Getting help

### Before you contact support

- Check the troubleshooting table at the end of the relevant application page.
- Note the document number (for example the sales order or invoice number) and the exact message on screen.
- Tell your Turbine administrator which company was selected in the company switcher.
