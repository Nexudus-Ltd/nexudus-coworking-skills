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
| `nexudus crmopportunities list --name <value> --crm-board-column-name <value> --agent` | Filter crmopportunities by properties |
| `nexudus crmopportunities list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmopportunities list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus crmopportunities get <id> --agent` | Get single crmopportunity |
| `nexudus crmopportunities create --crm-board-column-id <value> --coworker-id <value> --status <value> --position <value> --agent` | Create crmopportunity |
| `nexudus crmopportunities update <id> --name "New Name" --agent` | Update crmopportunity |
| `nexudus crmopportunities delete <id> --yes --agent` | Delete crmopportunity (no prompt) |

#### CrmOpportunity list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Optional tag to identify this opportunity, useful when the same customer appears in multiple boards |
| `--crm-board-column-id` | long | ID of the crm board column linked to this record |
| `--crm-board-column-name` | string | CRM stage name |
| `--crm-board-column-crm-board-id` | int | CRM board ID |
| `--from-crm-board-column-crm-board-id` | range | |
| `--to-crm-board-column-crm-board-id` | range | |
| `--crm-board-column-crm-board-name` | string | CRM board name |
| `--crm-board-column-crm-board-business-id` | int | Business ID of the CRM board |
| `--from-crm-board-column-crm-board-business-id` | range | |
| `--to-crm-board-column-crm-board-business-id` | range | |
| `--crm-board-column-crm-board-business-name` | string | Business name of the CRM board |
| `--crm-board-column-crm-board-business-currency-id` | int | Currency ID of the CRM board's business |
| `--from-crm-board-column-crm-board-business-currency-id` | range | |
| `--to-crm-board-column-crm-board-business-currency-id` | range | |
| `--crm-board-column-crm-board-business-currency-code` | string | Currency code of the CRM board's business |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--coworker-full-name` | string | Customer full name |
| `--coworker-coworker-type` | string | Customer record type |
| `--coworker-company-name` | string | Customer company name |
| `--coworker-email` | string | Customer email address |
| `--team-id` | long | ID of the team linked to this record |
| `--team-name` | string | Team name |
| `--team-description` | string | Team description |
| `--team-profile-website` | string | Team profile website |
| `--opportunity-type-id` | long | Opportunity type used to categorise and auto-populate general notes from a template |
| `--opportunity-type-name` | string | Opportunity type name |
| `--responsible-id` | long | Admin user responsible for managing this opportunity |
| `--responsible-full-name` | string | Responsible admin full name |
| `--referrer-id` | long | Customer who referred this opportunity |
| `--agent-id` | long | External agent or broker who brought this opportunity |
| `--notes` | string | General notes visible to admins when viewing the opportunity. Auto-populated from the opportunity type template if a type is assigned |
| `--completed` | bool | Whether the opportunity has been completed (won or lost) |
| `--due-date` | DateTime | Follow-up date for the opportunity |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--value` | decimal | Expected revenue if the opportunity is won |
| `--from-value` | range | |
| `--to-value` | range | |
| `--reminded` | bool | Whether a follow-up reminder has been sent for this opportunity |
| `--lead-source` | enum | How the opportunity was acquired (e.g. Web, Phone, Referral, Broker, GoogleSearch) |
| `--loss-reason` | enum | Why the opportunity was lost (e.g. Price, Competition, Location). Only relevant when Status is Lost |
| `--status` | enum | Opportunity status: InProgress (still active), Won (led to a sale), or Lost (did not lead to a sale) |
| `--won-on` | DateTime | Date when the opportunity was marked as won |
| `--from-won-on` | range | |
| `--to-won-on` | range | |
| `--lost-on` | DateTime | Date when the opportunity was marked as lost |
| `--from-lost-on` | range | |
| `--to-lost-on` | range | |
| `--crm-updated-on` | DateTime | Timestamp of the last CRM-related update to this opportunity |
| `--from-crm-updated-on` | range | |
| `--to-crm-updated-on` | range | |
| `--position` | int | Display order of the opportunity within its current stage |
| `--from-position` | range | |
| `--to-position` | range | |
| `--utm-source` | string | UTM source parameter captured from the URL the opportunity used |
| `--utm-medium` | string | UTM medium parameter captured from the URL the opportunity used |
| `--utm-campaign` | string | UTM campaign parameter captured from the URL the opportunity used |
| `--utm-content` | string | UTM content parameter captured from the URL the opportunity used |
| `--utm-term` | string | UTM term parameter captured from the URL the opportunity used |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CrmOpportunity sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CrmOpportunity create options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Optional tag to identify this opportunity, useful when the same customer appears in multiple boards |
| `--crm-board-column-id` | long, required | ID of the crm board column linked to this record |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--team-id` | long | ID of the team linked to this record |
| `--opportunity-type-id` | long | Opportunity type used to categorise and auto-populate general notes from a template |
| `--responsible-id` | long | Admin user responsible for managing this opportunity |
| `--referrer-id` | long | Customer who referred this opportunity |
| `--agent-id` | long | External agent or broker who brought this opportunity |
| `--notes` | string | General notes visible to admins when viewing the opportunity. Auto-populated from the opportunity type template if a type is assigned |
| `--completed` | bool | Whether the opportunity has been completed (won or lost) |
| `--due-date` | DateTime | Follow-up date for the opportunity |
| `--value` | decimal | Expected revenue if the opportunity is won |
| `--reminded` | bool | Whether a follow-up reminder has been sent for this opportunity |
| `--lead-source` | enum | How the opportunity was acquired (e.g. Web, Phone, Referral, Broker, GoogleSearch) |
| `--loss-reason` | enum | Why the opportunity was lost (e.g. Price, Competition, Location). Only relevant when Status is Lost |
| `--status` | enum, required | Opportunity status: InProgress (still active), Won (led to a sale), or Lost (did not lead to a sale) |
| `--won-on` | DateTime | Date when the opportunity was marked as won |
| `--lost-on` | DateTime | Date when the opportunity was marked as lost |
| `--position` | int, required | Display order of the opportunity within its current stage |
| `--utm-source` | string | UTM source parameter captured from the URL the opportunity used |
| `--utm-medium` | string | UTM medium parameter captured from the URL the opportunity used |
| `--utm-campaign` | string | UTM campaign parameter captured from the URL the opportunity used |
| `--utm-content` | string | UTM content parameter captured from the URL the opportunity used |
| `--utm-term` | string | UTM term parameter captured from the URL the opportunity used |

#### CrmOpportunity update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Optional tag to identify this opportunity, useful when the same customer appears in multiple boards |
| `--crm-board-column-id` | long | ID of the crm board column linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--team-id` | long | ID of the team linked to this record |
| `--opportunity-type-id` | long | Opportunity type used to categorise and auto-populate general notes from a template |
| `--responsible-id` | long | Admin user responsible for managing this opportunity |
| `--referrer-id` | long | Customer who referred this opportunity |
| `--agent-id` | long | External agent or broker who brought this opportunity |
| `--notes` | string | General notes visible to admins when viewing the opportunity. Auto-populated from the opportunity type template if a type is assigned |
| `--completed` | bool | Whether the opportunity has been completed (won or lost) |
| `--due-date` | DateTime | Follow-up date for the opportunity |
| `--value` | decimal | Expected revenue if the opportunity is won |
| `--reminded` | bool | Whether a follow-up reminder has been sent for this opportunity |
| `--lead-source` | enum | How the opportunity was acquired (e.g. Web, Phone, Referral, Broker, GoogleSearch) |
| `--loss-reason` | enum | Why the opportunity was lost (e.g. Price, Competition, Location). Only relevant when Status is Lost |
| `--status` | enum | Opportunity status: InProgress (still active), Won (led to a sale), or Lost (did not lead to a sale) |
| `--won-on` | DateTime | Date when the opportunity was marked as won |
| `--lost-on` | DateTime | Date when the opportunity was marked as lost |
| `--position` | int | Display order of the opportunity within its current stage |
| `--utm-source` | string | UTM source parameter captured from the URL the opportunity used |
| `--utm-medium` | string | UTM medium parameter captured from the URL the opportunity used |
| `--utm-campaign` | string | UTM campaign parameter captured from the URL the opportunity used |
| `--utm-content` | string | UTM content parameter captured from the URL the opportunity used |
| `--utm-term` | string | UTM term parameter captured from the URL the opportunity used |

#### CrmOpportunity PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--responsible-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus crmopportunities update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CrmOpportunity (key fields)

`Id`, `Name`, `CrmBoardColumnName`, `CrmBoardColumnCrmBoardName`, `CrmBoardColumnCrmBoardBusinessName`, `CrmBoardColumnCrmBoardBusinessCurrencyCode`, `CoworkerFullName`, `CoworkerCompanyName`, `CoworkerEmail`, `TeamName`, `OpportunityTypeName`, `ResponsibleFullName`, `Notes`, `DueDate`, `Value`

#### CrmOpportunity enum values

| Option | Valid values |
| ------ | ------------ |
| `--status` | `1` InProgress, `2` Won, `3` Lost |

<!-- END:GENERATED entity=CrmOpportunities -->
