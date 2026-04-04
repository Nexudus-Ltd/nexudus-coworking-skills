# DataFiles

<!-- BEGIN:GENERATED entity=DataFiles -->

DataFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus datafiles list --agent` | List all datafiles |
| `nexudus datafiles list --id <id> --agent` | Filter by single ID |
| `nexudus datafiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus datafiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus datafiles list --business-id <value> --name <value> --agent` | Filter datafiles by properties |
| `nexudus datafiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus datafiles get <id> --agent` | Get single datafile |
| `nexudus datafiles create --business-id <value> --name <value> --agent` | Create datafile |
| `nexudus datafiles update <id> --name "New Name" --agent` | Update datafile |
| `nexudus datafiles delete <id> --yes --agent` | Delete datafile (no prompt) |

#### DataFile list filter options

`--business-id`, `--name`, `--description`, `--new-file-data-url`, `--clear-file-data-file`, `--file-size-bytes`

#### DataFile create options

`--business-id` (required), `--name` (required), `--description`, `--new-file-data-url`, `--clear-file-data-file`, `--file-size-bytes`

#### DataFile update options

`--business-id`, `--name`, `--description`, `--new-file-data-url`, `--clear-file-data-file`, `--file-size-bytes`

<!-- END:GENERATED entity=DataFiles -->
