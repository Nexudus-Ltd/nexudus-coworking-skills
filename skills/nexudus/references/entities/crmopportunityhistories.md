# CrmOpportunityHistories

<!-- BEGIN:GENERATED entity=CrmOpportunityHistories -->

A **CrmOpportunityHistory** records a single stage transition for a CRM opportunity. Each time an opportunity moves from one CRM stage to another, a history entry is created capturing the previous stage, the new stage, when the move happened, and which admin user triggered it.

Use this entity to audit the movement of opportunities across a CRM board over time. The History tab on an opportunity in the Nexudus UI displays these records.

CrmOpportunityHistories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmopportunityhistories list --agent` | List all crmopportunityhistories |
| `nexudus crmopportunityhistories list --id <id> --agent` | Filter by single ID |
| `nexudus crmopportunityhistories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmopportunityhistories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmopportunityhistories list --from-time <value> --to-time <value> --agent` | Filter crmopportunityhistories by properties |
| `nexudus crmopportunityhistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmopportunityhistories get <id> --agent` | Get single crmopportunityhistory |
| `nexudus crmopportunityhistories create --new-crm-board-column-id <value> --agent` | Create crmopportunityhistory |
| `nexudus crmopportunityhistories update <id> --name "New Name" --agent` | Update crmopportunityhistory |
| `nexudus crmopportunityhistories delete <id> --yes --agent` | Delete crmopportunityhistory (no prompt) |

#### CrmOpportunityHistory list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--crm-opportunity-id` | long | The opportunity this history entry belongs to |
| `--old-crm-board-column-id` | long | CRM stage the opportunity moved from (null for the initial placement) |
| `--from-time` | DateTime | When the opportunity entered the previous stage |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | When the opportunity left the previous stage and entered the new one |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--new-crm-board-column-id` | long | CRM stage the opportunity moved to |
| `--user-id` | long | Admin user who triggered the stage transition (null if moved automatically) |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CrmOpportunityHistory create options

| Option | Type | Description |
| --- | --- | --- |
| `--crm-opportunity-id` | long | The opportunity this history entry belongs to |
| `--old-crm-board-column-id` | long | CRM stage the opportunity moved from (null for the initial placement) |
| `--from-time` | DateTime | When the opportunity entered the previous stage |
| `--to-time` | DateTime | When the opportunity left the previous stage and entered the new one |
| `--new-crm-board-column-id` | long, required | CRM stage the opportunity moved to |
| `--user-id` | long | Admin user who triggered the stage transition (null if moved automatically) |

#### CrmOpportunityHistory update options

| Option | Type | Description |
| --- | --- | --- |
| `--crm-opportunity-id` | long | The opportunity this history entry belongs to |
| `--old-crm-board-column-id` | long | CRM stage the opportunity moved from (null for the initial placement) |
| `--from-time` | DateTime | When the opportunity entered the previous stage |
| `--to-time` | DateTime | When the opportunity left the previous stage and entered the new one |
| `--new-crm-board-column-id` | long | CRM stage the opportunity moved to |
| `--user-id` | long | Admin user who triggered the stage transition (null if moved automatically) |

#### CrmOpportunityHistory PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus crmopportunityhistories update <id> --user-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CrmOpportunityHistory (key fields)

`Id`, `OldCrmBoardColumnName`, `FromTime`, `ToTime`, `NewCrmBoardColumnName`, `UserFullName`

<!-- END:GENERATED entity=CrmOpportunityHistories -->
