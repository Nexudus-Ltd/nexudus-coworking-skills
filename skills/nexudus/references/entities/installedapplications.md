# InstalledApplications

<!-- BEGIN:GENERATED entity=InstalledApplications -->

An **InstalledApplication** represents a third-party or internal application that has been installed and configured for a specific business location.

InstalledApplications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus installedapplications list --agent` | List all installedapplications |
| `nexudus installedapplications list --id <id> --agent` | Filter by single ID |
| `nexudus installedapplications list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus installedapplications list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus installedapplications list --application-id <value> --business-id <value> --agent` | Filter installedapplications by properties |
| `nexudus installedapplications list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus installedapplications list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus installedapplications get <id> --agent` | Get single installedapplication |
| `nexudus installedapplications create --application-id <value> --business-id <value> --agent` | Create installedapplication |
| `nexudus installedapplications update <id> --name "New Name" --agent` | Update installedapplication |
| `nexudus installedapplications delete <id> --yes --agent` | Delete installedapplication (no prompt) |

#### InstalledApplication list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--application-id` | long | ID of the application linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--requires-approval` | bool | Whether requires approval is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### InstalledApplication sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### InstalledApplication create options

| Option | Type | Description |
| --- | --- | --- |
| `--application-id` | long, required | ID of the application linked to this record |
| `--business-id` | long, required | ID of the business linked to this record |
| `--requires-approval` | bool | Whether requires approval is enabled |

#### InstalledApplication update options

| Option | Type | Description |
| --- | --- | --- |
| `--application-id` | long | ID of the application linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--requires-approval` | bool | Whether requires approval is enabled |

<!-- END:GENERATED entity=InstalledApplications -->
