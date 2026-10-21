# CRM

Capture enquiries from every channel, work them through a visual pipeline, follow up on time and turn won deals into quotations.

## Leads and opportunities

### The difference

A **lead** is an unqualified enquiry. Once qualified, you convert it to an **opportunity**, which appears in the pipeline with expected revenue, probability and stages.

| Record | Where | Purpose |
| --- | --- | --- |
| Lead | **CRM → Leads** | New enquiries waiting to be qualified |
| Opportunity | **CRM → Sales → My Pipeline** | Qualified deals being worked towards a close |

### Where leads come from

- **Email** — messages sent to your sales team's email alias (for example sales@yourcompany.com) create leads automatically in that team.
- **Website** — the Contact Us form creates leads.
- **Surveys and events** — responses and registrations can generate leads (see [Surveys](surveys.md#survey-to-lead)).
- **Import** — bulk upload from a spreadsheet during go-live.
- **Manual entry** — salespeople create leads from calls, walk-ins and trade shows.

### Create and qualify a lead

1. Go to **CRM → Leads** and click **New**.
2. Enter the subject, contact name, company, email, phone and the source (campaign, medium, source).
3. Review the **Probability** suggested by predictive scoring.
4. Click **Convert to Opportunity**. Choose the salesperson and team, and whether to create a new customer or link an existing one. Turbine warns you about similar leads and lets you merge them.
5. If the enquiry is not worth pursuing, click **Lost** and select a lost reason.

## Working the pipeline

### Move deals through stages

1. Open **CRM → Sales → My Pipeline** (Kanban view). Use the **+** at the top of a stage to add an opportunity quickly.
2. Fill **Expected Revenue**, **Probability**, **Expected Closing** and **Tags**.
3. For AMC or recurring service contracts, fill **Recurring Revenue** and **Recurring Plan** (monthly, yearly).
4. Drag cards to the next stage — for example New → Qualified → Proposition → Won.
5. Close the deal with **Won** or **Lost**.

### Predictive lead scoring

Turbine calculates each lead's probability of winning from your own won and lost history, using fields such as stage, state, source, tags and the quality of the email and phone details. Scores improve as more deals are closed. Your administrator chooses which fields the score uses.

### Automatic lead assignment

Leads can be distributed to sales teams and salespeople by rules — for example by state or product interest — with a maximum number of leads per person every 30 days. Assignment runs on demand with **Assign Leads** or on a schedule.

## Activities and follow-up

### Schedule follow-ups

- Click the clock icon on a card, or **Activities** in the chatter, to schedule a call, meeting, email or to-do with a due date.
- Apply an **Activity Plan** (for example "Qualification: call + email + meeting") to schedule several steps at once.
- Overdue activities show in red; **CRM → Sales → My Activities** lists everything due.
- The **Meeting** button opens the calendar with the customer filled in; the meeting stays linked to the opportunity.

## Quotations from opportunities

### From deal to order

Click **New Quotation** on the opportunity. The quotation is linked to it and continues in [Sales](sales.md). When the quotation is confirmed, mark the opportunity **Won**. The **Quotations** smart button lists every quote linked to the opportunity.

## Reports

### Pipeline analysis

| Report | Answers |
| --- | --- |
| **Reporting → Pipeline** | Pipeline value by stage, salesperson and month |
| **Reporting → Forecast** | Expected revenue by closing month |
| **Reporting → Leads** | Conversion rate and lead sources |
| **Reporting → Activities** | Completed and overdue activities per salesperson |

Lost reasons recorded on closed deals feed win/loss analysis; keep the list of reasons short and specific.

## Administration

### Settings

| Setting | Purpose |
| --- | --- |
| Leads | Adds the lead qualification step before the pipeline |
| Recurring Revenues | Recurring revenue and plans on opportunities |
| Rule-Based Assignment | Distributes leads by rules and capacity, manually or on a schedule |
| Predictive Lead Scoring | Chooses the fields that drive the probability score |
| Multi-teams | Allows a salesperson to belong to several teams |
| Lead Enrichment | Optional; adds company data to leads using paid credits |

### Sales teams and pipeline

- **CRM → Configuration → Sales Teams** — tick **Leads** and **Pipeline**, set the team's email alias, add members and their assignment limits.
- **Configuration → Stages** — mark the Won stage; teams can have their own stages.
- **Configuration** also holds Tags, Lost Reasons, Recurring Plans, Activity Types and Activity Plans.

### Access rights

| Role | Can do |
| --- | --- |
| Sales User: Own Documents Only | Sees own leads and opportunities |
| Sales User: All Documents | Sees the whole pipeline |
| Sales Administrator | Configures CRM, teams and assignment rules |

### Importing open opportunities

Use these columns when migrating from spreadsheets: opportunity name, type (lead or opportunity), customer, contact name, email, phone, sales team, salesperson, stage, expected revenue, probability, expected closing date, source, medium, campaign and tags.

## Troubleshooting

### Common issues

| Symptom | Cause | Fix | Who |
| --- | --- | --- | --- |
| Emails to the sales alias create no lead | Alias not set on the team, or no incoming mail server | Set the alias and check incoming mail | Administrator |
| Leads menu missing | Leads setting is off | Turn on Leads in CRM settings | Administrator |
| Leads not distributed | Assignment runs manually | Click **Assign Leads**, or set it to run on a schedule | Sales manager |
| Salesperson cannot see a colleague's deals | Access is Own Documents Only | Change to All Documents if appropriate | Administrator |
| Probability seems wrong | Few closed deals yet, or scoring fields unsuitable | Review scoring fields after 4–8 weeks of use | Sales manager |
