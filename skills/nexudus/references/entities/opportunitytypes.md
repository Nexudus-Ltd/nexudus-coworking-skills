# OpportunityTypes

<!-- BEGIN:GENERATED entity=OpportunityTypes -->

An **OpportunityType** defines a category for CRM opportunities, such as 'New Member', 'Event Booking', or 'Office Rental'. Types help classify and filter sales pipeline items.

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
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this opportunity type |
| `--notes-template` | string | The notes template value for this opportunity type |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### OpportunityType create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this opportunity type |
| `--notes-template` | string | The notes template value for this opportunity type |

#### OpportunityType update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this opportunity type |
| `--notes-template` | string | The notes template value for this opportunity type |

<!-- END:GENERATED entity=OpportunityTypes -->
