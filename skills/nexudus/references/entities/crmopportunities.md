# CrmOpportunities

<!-- BEGIN:GENERATED entity=CrmOpportunities -->

A **CrmOpportunity** represents a potential or existing deal linked to a customer record that moves through stages on a CRM board.

Opportunities track the lifecycle of a customer interaction — from initial enquiry or tour request through to a won or lost outcome. Each opportunity sits in a single CRM stage (`CrmBoardColumn`) and can be moved between stages manually or automatically via stage auto-assignment rules.

Key fields:

- **Status** — `InProgress`, `Won`, or `Lost`. Stages with `WinOpportunity` or `LoseOpportunity` update this automatically.
- **LeadSource** — how the opportunity was acquired (e.g. Web, Phone, Referral, Broker, GoogleSearch).
- **LossReason** — why the opportunity was lost (e.g. Price, Competition, Location). Only meaningful when Status is `Lost`.
- **Value** — expected revenue if the opportunity is won.
- **DueDate** — follow-up date for the opportunity.
- **UTM fields** — automatically populated from the URL the opportunity used to reach the sign-up or contact form.

There is a limit of 5,000 opportunities per location.

CrmOpportunities support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmopportunities list --agent` | List all crmopportunities |
| `nexudus crmopportunities list --id <id> --agent` | Filter by single ID |
| `nexudus crmopportunities list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmopportunities list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmopportunities list --name <value> --notes <value> --agent` | Filter crmopportunities by properties |
| `nexudus crmopportunities list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmopportunities get <id> --agent` | Get single crmopportunity |
| `nexudus crmopportunities create --crm-board-column-id <value> --coworker-id <value> --status <value> --position <value> --agent` | Create crmopportunity |
| `nexudus crmopportunities update <id> --name "New Name" --agent` | Update crmopportunity |
| `nexudus crmopportunities delete <id> --yes --agent` | Delete crmopportunity (no prompt) |

#### CrmOpportunity list filter options

`--name`, `--crm-board-column-id` (long), `--coworker-id` (long), `--team-id` (long), `--opportunity-type-id` (long), `--responsible-id` (long), `--referrer-id` (long), `--agent-id` (long), `--notes`, `--completed` (bool), `--due-date` (DateTime), `--from-due-date` (range), `--to-due-date` (range), `--value` (decimal), `--from-value` (range), `--to-value` (range), `--reminded` (bool), `--lead-source` (enum), `--loss-reason` (enum), `--status` (enum), `--won-on` (DateTime), `--from-won-on` (range), `--to-won-on` (range), `--lost-on` (DateTime), `--from-lost-on` (range), `--to-lost-on` (range), `--position` (int), `--from-position` (range), `--to-position` (range), `--utm-source`, `--utm-medium`, `--utm-campaign`, `--utm-content`, `--utm-term`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CrmOpportunity create options

`--name`, `--crm-board-column-id` (long, required), `--coworker-id` (long, required), `--team-id` (long), `--opportunity-type-id` (long), `--responsible-id` (long), `--referrer-id` (long), `--agent-id` (long), `--notes`, `--completed` (bool), `--due-date` (DateTime), `--value` (decimal), `--reminded` (bool), `--lead-source` (enum), `--loss-reason` (enum), `--status` (enum, required), `--won-on` (DateTime), `--lost-on` (DateTime), `--position` (int, required), `--utm-source`, `--utm-medium`, `--utm-campaign`, `--utm-content`, `--utm-term`

#### CrmOpportunity update options

`--name`, `--crm-board-column-id` (long), `--coworker-id` (long), `--team-id` (long), `--opportunity-type-id` (long), `--responsible-id` (long), `--referrer-id` (long), `--agent-id` (long), `--notes`, `--completed` (bool), `--due-date` (DateTime), `--value` (decimal), `--reminded` (bool), `--lead-source` (enum), `--loss-reason` (enum), `--status` (enum), `--won-on` (DateTime), `--lost-on` (DateTime), `--position` (int), `--utm-source`, `--utm-medium`, `--utm-campaign`, `--utm-content`, `--utm-term`

### CrmOpportunity (key fields)

`Id`, `Name`, `CrmBoardColumnName`, `CrmBoardColumnCrmBoardName`, `CrmBoardColumnCrmBoardBusinessName`, `CrmBoardColumnCrmBoardBusinessCurrencyCode`, `CoworkerFullName`, `CoworkerCompanyName`, `CoworkerEmail`, `TeamName`, `OpportunityTypeName`, `ResponsibleFullName`, `Notes`, `DueDate`, `Value`

#### CrmOpportunity enum values

| Option | Valid values |
| ------ | ------------ |
| `--status` | `1` InProgress, `2` Won, `3` Lost |

<!-- END:GENERATED entity=CrmOpportunities -->
