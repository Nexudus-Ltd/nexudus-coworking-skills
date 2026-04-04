# Reports

<!-- BEGIN:GENERATED entity=Reports -->

Reports support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus reports list --agent` | List all reports |
| `nexudus reports list --id <id> --agent` | Filter by single ID |
| `nexudus reports list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus reports list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus reports list --business-id <value> --name <value> --agent` | Filter reports by properties |
| `nexudus reports list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reports get <id> --agent` | Get single report |
| `nexudus reports create --business-id <value> --name <value> --folder <value> --agent` | Create report |
| `nexudus reports update <id> --name "New Name" --agent` | Update report |
| `nexudus reports delete <id> --yes --agent` | Delete report (no prompt) |

#### Report list filter options

`--business-id`, `--name`, `--folder`, `--report-type`, `--report-xml`

#### Report create options

`--business-id` (required), `--name` (required), `--folder` (required), `--report-type`, `--report-xml`

#### Report update options

`--business-id`, `--name`, `--folder`, `--report-type`, `--report-xml`

<!-- END:GENERATED entity=Reports -->
