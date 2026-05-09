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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--source-url` | string | Source URL path to redirect from |
| `--destination-url` | string | Destination URL to redirect to |
| `--active` | bool | Whether the redirect is currently active |
| `--active-from` | DateTime | Date and time from which the redirect becomes active |
| `--from-active-from` | range | |
| `--to-active-from` | range | |
| `--active-to` | DateTime | Date and time after which the redirect is no longer active |
| `--from-active-to` | range | |
| `--to-active-to` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BusinessRedirection create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--source-url` | string, required | Source URL path to redirect from |
| `--destination-url` | string, required | Destination URL to redirect to |
| `--active` | bool | Whether the redirect is currently active |
| `--active-from` | DateTime | Date and time from which the redirect becomes active |
| `--active-to` | DateTime | Date and time after which the redirect is no longer active |

#### BusinessRedirection update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--source-url` | string | Source URL path to redirect from |
| `--destination-url` | string | Destination URL to redirect to |
| `--active` | bool | Whether the redirect is currently active |
| `--active-from` | DateTime | Date and time from which the redirect becomes active |
| `--active-to` | DateTime | Date and time after which the redirect is no longer active |

### BusinessRedirection (key fields)

`Id`, `SourceURL`, `DestinationURL`, `Active`

<!-- END:GENERATED entity=BusinessRedirections -->
