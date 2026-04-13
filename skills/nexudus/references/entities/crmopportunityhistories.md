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

`--crm-opportunity-id` (long), `--old-crm-board-column-id` (long), `--from-time` (DateTime), `--from-from-time` (range), `--to-from-time` (range), `--to-time` (DateTime), `--from-to-time` (range), `--to-to-time` (range), `--new-crm-board-column-id` (long), `--user-id` (long), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CrmOpportunityHistory create options

`--crm-opportunity-id` (long), `--old-crm-board-column-id` (long), `--from-time` (DateTime), `--to-time` (DateTime), `--new-crm-board-column-id` (long, required), `--user-id` (long)

#### CrmOpportunityHistory update options

`--crm-opportunity-id` (long), `--old-crm-board-column-id` (long), `--from-time` (DateTime), `--to-time` (DateTime), `--new-crm-board-column-id` (long), `--user-id` (long)

### CrmOpportunityHistory (key fields)

`Id`, `OldCrmBoardColumnName`, `FromTime`, `ToTime`, `NewCrmBoardColumnName`, `UserFullName`

<!-- END:GENERATED entity=CrmOpportunityHistories -->
