# Expenses

Employee expense claims with receipts and GST, manager approval and reimbursement through Accounting — plus travel requests for trips that need approval before anyone books a ticket.

## Which to use

### Expenses or a travel request

| Situation | Use |
| --- | --- |
| A one-off spend in town — customer lunch, taxi, phone recharge | An expense claim |
| Tickets, hotels, more than one day away, or a cash advance | A travel request first, then expense claims linked to the trip |

Both end in the same Expenses approval and payment.

## Submitting expenses

### Record a claim

1. Open **Expenses → My Expenses → My Expenses** and click **New**.
2. Type a description and pick the category (Meals, Mileage, Communication, Travel & Accommodation and others). The GST tax on the category is filled in.
3. Enter the total and the date.
4. Choose **Employee** if you paid, or **Company** if a company card paid.
5. Click **Attach Receipt**, then **Submit**.
6. The status moves Draft → Approved → Posted → Paid.

Good to know:

- You can email a receipt to your company's expenses address to create a draft claim.
- **Split** divides one receipt across categories or projects.

## Approval and payment

### Manager and accounts

1. Managers approve claims in **Expenses → Expenses to Process** with **Approve**, or refuse with a reason.
2. Approval creates the accounting entry for the claim.
3. Accounts posts it and pays the employee with **Register Payment**; company-paid expenses are recorded without paying anyone twice.

## Travel requests

### Plan and approve a business trip

1. Before the trip, open **Travel Expense → Expense Request → New**. Enter the purpose, project, departure and return dates (days are counted automatically), from and to addresses, travel modes (Flight, Train, Bus, Car, Taxi), and visa or ticket agents if used.
2. Record any advance requested: amount, bank and cheque number.
3. Click **Confirm**. The travel approver clicks **Approve**; tickets can now be booked. A rejected request records the reason.
4. During or after the trip, click **Add Expense** on the approved request for each ticket, hotel or meal bill. Each expense carries the trip link.
5. Submit and approve each expense as usual in Expenses.
6. Click **Complete** on the request to close the trip. The request shows the trip's total and approved expense amounts.

Good to know: the advance on a travel request is recorded for information. Pay advances through [salary advance](employees.md#loans-and-salary-advance) or a bank payment, and settle any difference with Accounts.

## Reports

### Expense analysis

**Expenses → Reporting** analyses claims by employee, category and month. Group by trip or project to see the cost of client visits.

## Administration

### Set-up

- Expense categories with GST taxes and expense accounts (Meals, Mileage, Travel & Accommodation, Communication).
- Employee managers, so claims route to the right approver.
- The expenses email alias and outgoing mail server.
- For travel requests: give employees the Travel Employee group and the travel desk the Travel Administrator group; load travel modes.

### Access rights

| Role | Can do |
| --- | --- |
| Employee | Submit own claims and travel requests |
| Team Approver | Approve the team's claims |
| Expense Administrator | Approve all claims, configure categories |
| Accountant | Post and pay approved claims |

## Troubleshooting

### Common issues

| Symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| Claim not reaching the manager | Employee has no manager set | Set the manager on the employee record | HR |
| GST missing on a claim | Category has no tax | Add the tax to the category | Administrator |
| Emailed receipt created nothing | Expenses alias or incoming mail not configured | Configure the alias | Administrator |
| Cannot open Travel Expense | User not in a travel group | Add the user to the Travel Employee group | Administrator |
| Cannot complete a trip | The trip has no expenses | Add expenses first | Employee |
