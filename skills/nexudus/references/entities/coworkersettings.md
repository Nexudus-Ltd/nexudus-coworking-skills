# CoworkerSettings

<!-- BEGIN:GENERATED entity=CoworkerSettings -->

A **CoworkerSetting** is an internal name/value pair used to store arbitrary customer-related settings.

Settings are scoped to a single customer (`CoworkerId`) and identified by a unique `Name` key. The value can be stored as plain text (`Value`) or in encrypted form (`EncryptedValue`) for sensitive data.

CoworkerSettings can also be accessed and managed via the Members Portal and the App Public API in the context of the logged-in customer.

CoworkerSettings support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkersettings list --agent` | List all coworkersettings |
| `nexudus coworkersettings list --id <id> --agent` | Filter by single ID |
| `nexudus coworkersettings list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkersettings list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkersettings list --name <value> --agent` | Filter coworkersettings by properties |
| `nexudus coworkersettings list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkersettings list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkersettings get <id> --agent` | Get single coworkersetting |
| `nexudus coworkersettings create --coworker-id <value> --name <value> --agent` | Create coworkersetting |
| `nexudus coworkersettings update <id> --name "New Name" --agent` | Update coworkersetting |
| `nexudus coworkersettings delete <id> --yes --agent` | Delete coworkersetting (no prompt) |

#### CoworkerSetting list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | The customer this setting belongs to |
| `--name` | string | The setting key name |
| `--value` | string | The plain-text value for this setting |
| `--encrypted-value` | string | An encrypted version of the setting value, used for sensitive data |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerSetting sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerSetting create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | The customer this setting belongs to |
| `--name` | string, required | The setting key name |
| `--value` | string | The plain-text value for this setting |
| `--encrypted-value` | string | An encrypted version of the setting value, used for sensitive data |

#### CoworkerSetting update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | The customer this setting belongs to |
| `--name` | string | The setting key name |
| `--value` | string | The plain-text value for this setting |
| `--encrypted-value` | string | An encrypted version of the setting value, used for sensitive data |

### CoworkerSetting (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=CoworkerSettings -->
