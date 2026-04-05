# LogEntries

<!-- BEGIN:GENERATED entity=LogEntries -->

LogEntries support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus logentries list --agent` | List all logentries |
| `nexudus logentries list --id <id> --agent` | Filter by single ID |
| `nexudus logentries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus logentries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus logentries list --business-id <value> --log-entry-type <value> --agent` | Filter logentries by properties |
| `nexudus logentries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus logentries get <id> --agent` | Get single logentry |

#### LogEntry list filter options

`--business-id`, `--log-entry-type`, `--description`, `--action-by`, `--entity-name`, `--entity-id`, `--from-entity-id` (range), `--to-entity-id` (range), `--obsolete`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

<!-- END:GENERATED entity=LogEntries -->
