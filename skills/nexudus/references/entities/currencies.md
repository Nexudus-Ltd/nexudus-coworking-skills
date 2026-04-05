# Currencies

<!-- BEGIN:GENERATED entity=Currencies -->

Currencies support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus currencies list --agent` | List all currencies |
| `nexudus currencies list --id <id> --agent` | Filter by single ID |
| `nexudus currencies list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus currencies list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus currencies list --name <value> --code <value> --agent` | Filter currencies by properties |
| `nexudus currencies list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus currencies get <id> --agent` | Get single currency |

#### Currency list filter options

`--name`, `--code`, `--format`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

### Currency (key fields)

`Id`, `Name`, `Code`, `Format`

<!-- END:GENERATED entity=Currencies -->
