# BusinessRedirections

<!-- BEGIN:GENERATED entity=BusinessRedirections -->

A **BusinessRedirection** is an internal entity representing an automatic URL redirect configured for a location's portal or app.

Each redirect maps a source URL to a destination URL. Redirects can be activated or deactivated, and optionally limited to a specific date range using `ActiveFrom` and `ActiveTo`.

BusinessRedirections support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus businessredirections list --agent` | List all businessredirections |
| `nexudus businessredirections list --id <id> --agent` | Filter by single ID |
| `nexudus businessredirections list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus businessredirections list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus businessredirections list --source-url <value> --destination-url <value> --agent` | Filter businessredirections by properties |
| `nexudus businessredirections list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus businessredirections get <id> --agent` | Get single businessredirection |
| `nexudus businessredirections create --business-id <value> --source-url <value> --destination-url <value> --agent` | Create businessredirection |
| `nexudus businessredirections update <id> --name "New Name" --agent` | Update businessredirection |
| `nexudus businessredirections delete <id> --yes --agent` | Delete businessredirection (no prompt) |

#### BusinessRedirection list filter options

`--business-id`, `--source-url`, `--destination-url`, `--active`, `--active-from`, `--active-to`

#### BusinessRedirection create options

`--business-id` (required), `--source-url` (required), `--destination-url` (required), `--active`, `--active-from`, `--active-to`

#### BusinessRedirection update options

`--business-id`, `--source-url`, `--destination-url`, `--active`, `--active-from`, `--active-to`

### BusinessRedirection (key fields)

`Id`, `SourceURL`, `DestinationURL`, `Active`

<!-- END:GENERATED entity=BusinessRedirections -->
