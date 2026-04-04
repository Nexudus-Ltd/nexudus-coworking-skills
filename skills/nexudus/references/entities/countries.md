# Countries

<!-- BEGIN:GENERATED entity=Countries -->

Countries support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus countries list --agent` | List all countries |
| `nexudus countries list --id <id> --agent` | Filter by single ID |
| `nexudus countries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus countries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus countries list --name <value> --two-digits-code <value> --agent` | Filter countries by properties |
| `nexudus countries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus countries get <id> --agent` | Get single country |

#### Country list filter options

`--name`, `--two-digits-code`, `--culture`

### Country (key fields)

`Id`, `Name`, `TwoDigitsCode`, `Culture`

<!-- END:GENERATED entity=Countries -->
