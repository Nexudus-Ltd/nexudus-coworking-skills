# CrmOpportunityImportFiles

<!-- BEGIN:GENERATED entity=CrmOpportunityImportFiles -->

A **CrmOpportunityImportFile** represents a file uploaded to bulk-import CRM opportunities into the system. Each record tracks the import file metadata and processing status.

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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--new-file-data-url` | string | URL of a new file to upload as the file data |
| `--clear-file-data-file` | bool | Set to true to remove the current file data file |
| `--name` | string | The name value for this crm opportunity import file |
| `--imported` | bool | Whether imported is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CrmOpportunityImportFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--new-file-data-url` | string | URL of a new file to upload as the file data |
| `--clear-file-data-file` | bool | Set to true to remove the current file data file |
| `--name` | string, required | The name value for this crm opportunity import file |
| `--imported` | bool | Whether imported is enabled |

#### CrmOpportunityImportFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--new-file-data-url` | string | URL of a new file to upload as the file data |
| `--clear-file-data-file` | bool | Set to true to remove the current file data file |
| `--name` | string | The name value for this crm opportunity import file |
| `--imported` | bool | Whether imported is enabled |

<!-- END:GENERATED entity=CrmOpportunityImportFiles -->
