# Payroll

Salary structures and rules, monthly payslip batches, loan and advance recovery, and salary journal entries posted to Accounting.

## Monthly payroll

### Run a payslip batch

1. Go to **Payroll → Payslips Batches → New**. Enter a name, the period and your company's **Salary Journal**.
2. Click **Run**, choose the salary structure, tick the employees and click **Generate**.
3. Open payslips to check worked days and inputs. Loan instalments and advance recoveries appear automatically.
4. Click **Compute Sheet**.
5. Click **Validate Payslips** to create the salary journal entry. Accounts posts the entry and pays.
6. Print with **Payslip Details**, or email payslips with **Send Mail**.

Good to know:

- Always check that the batch's salary journal belongs to the company you are paying.
- Validated entries remain drafts until Accounts posts them.
- Do not cancel a validated payslip that recovered a loan instalment without telling HR; the instalment must be corrected on the loan.

## Salary structures and Indian components

### How pay is calculated

A salary structure is a set of rules applied in sequence — for example Basic, HRA, Special Allowance, Gross, deductions and Net. Each rule is a percentage, fixed amount or formula, and each deduction is mapped to its payable account.

Typical Indian rules configured for your company:

| Rule | Typical basis |
| --- | --- |
| Basic | Percentage of CTC or gross |
| HRA | Percentage of Basic |
| Special allowance | Balancing figure |
| Provident Fund (employee and employer) | 12% of PF wages, with the wage ceiling your policy follows |
| ESI (employee and employer) | Percentage of gross, for employees within the ESI wage limit |
| Professional Tax | State slab |

Rates, ceilings and state slabs are configured as data during implementation and should be reviewed by your payroll consultant whenever the law changes.

### Statutory filings

Payroll computes contributions and posts them to the PF, ESI and Professional Tax payable accounts. Use the payslip and contribution reports to prepare the EPFO ECR, ESIC and Professional Tax returns on the respective portals.

## Payroll accounting

### Journal entries

Validating payslips creates one salary entry per batch: gross salary and employer contributions as expenses, and net pay, PF, ESI, Professional Tax, loan recoveries and TDS on salary as liabilities. Accounts posts the entry and pays net salaries from the bank.

## Administration

### Set-up checklist

- Salary structure and rules for each employee category, with debit and credit accounts on each rule.
- Employee contracts with wage and structure.
- A Salaries journal per company with Salary Payable as its default account.
- Loan and advance input rules linked to the HR loan and advance requests.
- A parallel run against the previous payroll for at least one month before go-live.

### Access rights

| Role | Can do |
| --- | --- |
| Payroll Officer | Generate and compute payslips |
| Payroll Manager | Validate payslips, configure structures and rules |

## Troubleshooting

### Common issues

| Message or problem | Why | What to do |
| --- | --- | --- |
| "Missing required field Salary Journal" | Batch has no journal | Pick your company's Salaries journal |
| Deduction posted on the wrong side | Payable account on the wrong field of the rule | Payroll manager corrects the rule's accounts |
| Loan instalment not on the payslip | Loan not approved, or instalment date outside the period | Check the loan schedule |
| Payslip computes for the wrong company | Structure or journal belongs to another company | Use the company's own structure and journal |
