# DataFiles

<!-- BEGIN:GENERATED entity=DataFiles -->

A **DataFile** stores a general-purpose file that can be referenced in the members portal, invoices, or email messages and templates sent to customers.

URLs for stored files are public. Use `NewFileDataUrl` to attach a file from a URL during create or update, and `ClearFileDataFile` to remove the currently attached file.

DataFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus datafiles list --agent` | List all datafiles |
| `nexudus datafiles list --id <id> --agent` | Filter by single ID |
| `nexudus datafiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus datafiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus datafiles list --name <value> --agent` | Filter datafiles by properties |
| `nexudus datafiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus datafiles get <id> --agent` | Get single datafile |
| `nexudus datafiles create --business-id <value> --name <value> --agent` | Create datafile |
| `nexudus datafiles update <id> --name "New Name" --agent` | Update datafile |
| `nexudus datafiles delete <id> --yes --agent` | Delete datafile (no prompt) |

#### DataFile list filter options

`--business-id` (long), `--name`, `--description`, `--new-file-data-url`, `--clear-file-data-file` (bool), `--file-size-bytes` (int), `--from-file-size-bytes` (range), `--to-file-size-bytes` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### DataFile create options

`--business-id` (long, required), `--name` (required), `--description`, `--new-file-data-url`, `--clear-file-data-file` (bool), `--file-size-bytes` (int)

#### DataFile update options

`--business-id` (long), `--name`, `--description`, `--new-file-data-url`, `--clear-file-data-file` (bool), `--file-size-bytes` (int)

### DataFile (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=DataFiles -->
