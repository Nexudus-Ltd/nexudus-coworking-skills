# OpportunityTypes

<!-- BEGIN:GENERATED entity=OpportunityTypes -->

OpportunityTypes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus opportunitytypes list --agent` | List all opportunitytypes |
| `nexudus opportunitytypes list --id <id> --agent` | Filter by single ID |
| `nexudus opportunitytypes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus opportunitytypes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus opportunitytypes list --business-id <value> --name <value> --agent` | Filter opportunitytypes by properties |
| `nexudus opportunitytypes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus opportunitytypes get <id> --agent` | Get single opportunitytype |
| `nexudus opportunitytypes create --business-id <value> --name <value> --agent` | Create opportunitytype |
| `nexudus opportunitytypes update <id> --name "New Name" --agent` | Update opportunitytype |
| `nexudus opportunitytypes delete <id> --yes --agent` | Delete opportunitytype (no prompt) |

#### OpportunityType list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--notes-template` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### OpportunityType create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required |  |
| `--notes-template` | string |  |

#### OpportunityType update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--notes-template` | string |  |

<!-- END:GENERATED entity=OpportunityTypes -->
