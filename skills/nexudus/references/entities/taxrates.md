# TaxRates

<!-- BEGIN:GENERATED entity=TaxRates -->

TaxRates support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus taxrates list --agent` | List all taxrates |
| `nexudus taxrates list --id <id> --agent` | Filter by single ID |
| `nexudus taxrates list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus taxrates list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus taxrates list --business-id <value> --name <value> --agent` | Filter taxrates by properties |
| `nexudus taxrates list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus taxrates get <id> --agent` | Get single taxrate |
| `nexudus taxrates create --business-id <value> --name <value> --rate <value> --agent` | Create taxrate |
| `nexudus taxrates update <id> --name "New Name" --agent` | Update taxrate |
| `nexudus taxrates delete <id> --yes --agent` | Delete taxrate (no prompt) |

#### TaxRate list filter options

`--business-id`, `--name`, `--rate`, `--from-rate` (range), `--to-rate` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### TaxRate create options

`--business-id` (required), `--name` (required), `--rate` (required)

#### TaxRate update options

`--business-id`, `--name`, `--rate`

<!-- END:GENERATED entity=TaxRates -->
