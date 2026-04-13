# CrmOpportunityImportFiles

<!-- BEGIN:GENERATED entity=CrmOpportunityImportFiles -->

CrmOpportunityImportFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmopportunityimportfiles list --agent` | List all crmopportunityimportfiles |
| `nexudus crmopportunityimportfiles list --id <id> --agent` | Filter by single ID |
| `nexudus crmopportunityimportfiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmopportunityimportfiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmopportunityimportfiles list --business-id <value> --new-file-data-url <value> --agent` | Filter crmopportunityimportfiles by properties |
| `nexudus crmopportunityimportfiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmopportunityimportfiles get <id> --agent` | Get single crmopportunityimportfile |
| `nexudus crmopportunityimportfiles create --business-id <value> --name <value> --agent` | Create crmopportunityimportfile |
| `nexudus crmopportunityimportfiles update <id> --name "New Name" --agent` | Update crmopportunityimportfile |
| `nexudus crmopportunityimportfiles delete <id> --yes --agent` | Delete crmopportunityimportfile (no prompt) |

#### CrmOpportunityImportFile list filter options

`--business-id` (long), `--new-file-data-url`, `--clear-file-data-file` (bool), `--name`, `--imported` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CrmOpportunityImportFile create options

`--business-id` (long, required), `--new-file-data-url`, `--clear-file-data-file` (bool), `--name` (required), `--imported` (bool)

#### CrmOpportunityImportFile update options

`--business-id` (long), `--new-file-data-url`, `--clear-file-data-file` (bool), `--name`, `--imported` (bool)

<!-- END:GENERATED entity=CrmOpportunityImportFiles -->
