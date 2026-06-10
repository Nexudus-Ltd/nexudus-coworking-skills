# Countries

<!-- BEGIN:GENERATED entity=Countries -->

A **Country** is a read-only reference record that represents a country supported by the platform. Countries are used across the system to configure address formats, locale settings, and language preferences for a location.

The `TwoDigitsCode` is the ISO 3166-1 alpha-2 code (e.g. `GB`, `US`, `DE`) and is the standard identifier used when filtering or referencing a country from other entities.

The `Culture` field contains a BCP 47 language tag (e.g. `en-GB`, `en-US`, `de-DE`) that determines number formatting, date formatting, and language defaults for the location.

Countries support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus countries list --agent` | List all countries |
| `nexudus countries list --id <id> --agent` | Filter by single ID |
| `nexudus countries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus countries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus countries list --name <value> --two-digits-code <value> --agent` | Filter countries by properties |
| `nexudus countries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus countries list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus countries get <id> --agent` | Get single country |

#### Country list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Full display name of the country (e.g. "United Kingdom", "United States") |
| `--two-digits-code` | string | ISO 3166-1 alpha-2 country code (e.g. "GB", "US", "DE") |
| `--culture` | string | BCP 47 culture tag that controls date, number, and language formatting for the location (e.g. "en-GB", "en-US") |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Country sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

### Country (key fields)

`Id`, `Name`, `TwoDigitsCode`, `Culture`

<!-- END:GENERATED entity=Countries -->
