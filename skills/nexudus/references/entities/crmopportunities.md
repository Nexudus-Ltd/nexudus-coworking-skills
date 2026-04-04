# CrmOpportunities

<!-- BEGIN:GENERATED entity=CrmOpportunities -->

CrmOpportunities support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmopportunities list --agent` | List all crmopportunities |
| `nexudus crmopportunities list --id <id> --agent` | Filter by single ID |
| `nexudus crmopportunities list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmopportunities list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmopportunities list --name <value> --crm-board-column-id <value> --agent` | Filter crmopportunities by properties |
| `nexudus crmopportunities list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmopportunities get <id> --agent` | Get single crmopportunity |
| `nexudus crmopportunities create --crm-board-column-id <value> --coworker-id <value> --position <value> --agent` | Create crmopportunity |
| `nexudus crmopportunities update <id> --name "New Name" --agent` | Update crmopportunity |
| `nexudus crmopportunities delete <id> --yes --agent` | Delete crmopportunity (no prompt) |

#### CrmOpportunity list filter options

`--name`, `--crm-board-column-id`, `--coworker-id`, `--team-id`, `--opportunity-type-id`, `--responsible-id`, `--referrer-id`, `--agent-id`, `--notes`, `--completed`, `--due-date`, `--value`, `--reminded`, `--lead-source`, `--loss-reason`, `--status`, `--won-on`, `--lost-on`, `--position`, `--utm-source`, `--utm-medium`, `--utm-campaign`, `--utm-content`, `--utm-term`

#### CrmOpportunity create options

`--name`, `--crm-board-column-id` (required), `--coworker-id` (required), `--team-id`, `--opportunity-type-id`, `--responsible-id`, `--referrer-id`, `--agent-id`, `--notes`, `--completed`, `--due-date`, `--value`, `--reminded`, `--lead-source`, `--loss-reason`, `--status`, `--won-on`, `--lost-on`, `--histories` (list, repeat flag), `--added-histories` (list, repeat flag), `--removed-histories` (list, repeat flag), `--position` (required), `--utm-source`, `--utm-medium`, `--utm-campaign`, `--utm-content`, `--utm-term`

#### CrmOpportunity update options

`--name`, `--crm-board-column-id`, `--coworker-id`, `--team-id`, `--opportunity-type-id`, `--responsible-id`, `--referrer-id`, `--agent-id`, `--notes`, `--completed`, `--due-date`, `--value`, `--reminded`, `--lead-source`, `--loss-reason`, `--status`, `--won-on`, `--lost-on`, `--histories` (list, repeat flag), `--added-histories` (list, repeat flag), `--removed-histories` (list, repeat flag), `--position`, `--utm-source`, `--utm-medium`, `--utm-campaign`, `--utm-content`, `--utm-term`

**List properties (only returned by `get`, not by `list`):** `Histories`, `AddedHistories`, `RemovedHistories`

<!-- END:GENERATED entity=CrmOpportunities -->
