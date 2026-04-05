# CrmOpportunityHistories

<!-- BEGIN:GENERATED entity=CrmOpportunityHistories -->

CrmOpportunityHistories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmopportunityhistories list --agent` | List all crmopportunityhistories |
| `nexudus crmopportunityhistories list --id <id> --agent` | Filter by single ID |
| `nexudus crmopportunityhistories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmopportunityhistories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmopportunityhistories list --crm-opportunity-id <value> --old-crm-board-column-id <value> --agent` | Filter crmopportunityhistories by properties |
| `nexudus crmopportunityhistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmopportunityhistories get <id> --agent` | Get single crmopportunityhistory |
| `nexudus crmopportunityhistories create --new-crm-board-column-id <value> --agent` | Create crmopportunityhistory |
| `nexudus crmopportunityhistories update <id> --name "New Name" --agent` | Update crmopportunityhistory |
| `nexudus crmopportunityhistories delete <id> --yes --agent` | Delete crmopportunityhistory (no prompt) |

#### CrmOpportunityHistory list filter options

`--crm-opportunity-id`, `--old-crm-board-column-id`, `--from-time`, `--from-from-time` (range), `--to-from-time` (range), `--to-time`, `--from-to-time` (range), `--to-to-time` (range), `--new-crm-board-column-id`, `--user-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CrmOpportunityHistory create options

`--crm-opportunity-id`, `--old-crm-board-column-id`, `--from-time`, `--to-time`, `--new-crm-board-column-id` (required), `--user-id`

#### CrmOpportunityHistory update options

`--crm-opportunity-id`, `--old-crm-board-column-id`, `--from-time`, `--to-time`, `--new-crm-board-column-id`, `--user-id`

<!-- END:GENERATED entity=CrmOpportunityHistories -->
