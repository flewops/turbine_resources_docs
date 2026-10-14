# Turbine Docs

Documentation for the Resources page of the Turbine website (`/resources`).
The site reads these files straight from this repository, so pushing here updates the docs — no website deploy needed.

> **This is dummy content for testing.** Replace it with real documentation before going live.

## Layout

```
versions.json        ← list of release versions, newest first
v2.0/
  index.md           ← overview shown when no app is selected
  crm.md             ← one file per app, named by its app id
  sales.md
  images/            ← images used by the markdown in this version
v1.1/
  …
```

## versions.json

```json
{
  "versions": [
    { "id": "v2.0", "label": "v2.0", "released": "2026-09-15", "apps": ["crm", "sales"] }
  ]
}
```

- `id` must match the folder name.
- The **first** version in the list is the default ("latest").
- `apps` lists the app ids that have a `<id>.md` file in that folder. Ids must match the website's app ids
  (e.g. `crm`, `sales`, `inventory`, `accounting`) — see the full list below.

## Writing a doc

- `# Title` — page title (first paragraph under it becomes the description)
- `## Section` — appears in the "On this page" sidebar
- `### Article` — a card inside the section
- Supported: paragraphs, **bold**, *italic*, `code`, lists, tables, code blocks, `> quotes`, `---` rules, `#### small headings`
- Images: `![Alt text](images/file.jpg "Caption")` — paths are relative to the markdown file
- Link to another app's doc: `[Sales](sales.md)`, or a section: `[Capture leads](crm.md#capture-leads)`
- Link to another version: `[v1.1 CRM](../v1.1/crm.md)`

## Adding a release

1. Copy the latest folder, e.g. `v2.0/` → `v2.1/`, and edit the files.
2. Add the new version at the **top** of `versions.json` with its `apps` list.
3. Commit and push. GitHub may cache files for up to ~5 minutes.

## Valid app ids

Use these ids in `versions.json` and as file names (`<id>.md`).

| App id | App | Category |
| --- | --- | --- |
| `accounting` | Accounting | finance |
| `expenses` | Expenses | finance |
| `spreadsheet` | Spreadsheet | finance |
| `crm` | CRM | sales |
| `sales` | Sales | sales |
| `point-of-sale` | Point of Sale | sales |
| `rental` | Rental | sales |
| `subscriptions` | Subscriptions | sales |
| `inventory` | Inventory | supply-chain |
| `manufacturing` | Manufacturing | supply-chain |
| `purchase` | Purchase | supply-chain |
| `maintenance` | Maintenance | supply-chain |
| `quality` | Quality | supply-chain |
| `plm` | PLM | supply-chain |
| `website` | Website | websites |
| `ecommerce` | eCommerce | websites |
| `live-chat` | Live Chat | websites |
| `elearning` | eLearning | websites |
| `employees` | Employees | human-resources |
| `recruitment` | Recruitment | human-resources |
| `time-off` | Time Off | human-resources |
| `payroll` | Payroll | human-resources |
| `appraisals` | Appraisals | human-resources |
| `referrals` | Referrals | human-resources |
| `approvals` | Approvals | human-resources |
| `attendances` | Attendances | human-resources |
| `fleet` | Fleet | human-resources |
| `email-marketing` | Email Marketing | marketing |
| `sms-marketing` | SMS Marketing | marketing |
| `social-marketing` | Social Marketing | marketing |
| `marketing-automation` | Marketing Automation | marketing |
| `events` | Events | marketing |
| `surveys` | Surveys | marketing |
| `project` | Project | services |
| `timesheets` | Timesheets | services |
| `helpdesk` | Helpdesk | services |
| `field-service` | Field Service | services |
| `planning` | Planning | services |
| `documents` | Documents | productivity |
| `sign` | Sign | productivity |
| `discuss` | Discuss | productivity |
| `knowledge` | Knowledge | productivity |
| `appointments` | Appointments | productivity |
| `whatsapp` | WhatsApp | productivity |
