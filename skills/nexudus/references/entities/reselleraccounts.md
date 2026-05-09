# ResellerAccounts

<!-- BEGIN:GENERATED entity=ResellerAccounts -->

ResellerAccounts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus reselleraccounts list --agent` | List all reselleraccounts |
| `nexudus reselleraccounts list --id <id> --agent` | Filter by single ID |
| `nexudus reselleraccounts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus reselleraccounts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus reselleraccounts list --notes <value> --scope-of-work <value> --agent` | Filter reselleraccounts by properties |
| `nexudus reselleraccounts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reselleraccounts get <id> --agent` | Get single reselleraccount |
| `nexudus reselleraccounts create  --agent` | Create reselleraccount |
| `nexudus reselleraccounts update <id> --name "New Name" --agent` | Update reselleraccount |
| `nexudus reselleraccounts delete <id> --yes --agent` | Delete reselleraccount (no prompt) |

#### ResellerAccount list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--notes` | string |  |
| `--scope-of-work` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ResellerAccount create options

| Option | Type | Description |
| --- | --- | --- |
| `--notes` | string |  |
| `--scope-of-work` | string |  |

#### ResellerAccount update options

| Option | Type | Description |
| --- | --- | --- |
| `--notes` | string |  |
| `--scope-of-work` | string |  |

<!-- END:GENERATED entity=ResellerAccounts -->
