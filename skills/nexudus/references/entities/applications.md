# Applications

<!-- BEGIN:GENERATED entity=Applications -->

An **Application** represents a third-party application that can be installed as an add-on in a Nexudus account.

Each application is owned by a developer and identified by a unique `ApplicationKey` and `SecretKey` pair. The `InstallUrl` is the endpoint Nexudus calls when a location installs the application.

Applications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus applications list --agent` | List all applications |
| `nexudus applications list --id <id> --agent` | Filter by single ID |
| `nexudus applications list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus applications list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus applications list --developer-id <value> --name <value> --agent` | Filter applications by properties |
| `nexudus applications list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus applications list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus applications get <id> --agent` | Get single application |
| `nexudus applications create --developer-id <value> --name <value> --short-description <value> --install-url <value> --agent` | Create application |
| `nexudus applications update <id> --name "New Name" --agent` | Update application |
| `nexudus applications delete <id> --yes --agent` | Delete application (no prompt) |

#### Application list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--developer-id` | long | ID of the developer linked to this record |
| `--name` | string | Display name of the application |
| `--published` | bool | Whether the application is published and available for installation |
| `--secret-key` | string | Secret key used to authenticate API calls from the application |
| `--short-description` | string | Brief summary of the application shown in listing views |
| `--description` | string | Full description of the application shown on the detail page |
| `--install-url` | string | URL that Nexudus calls when a location installs this application |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Application sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### Application create options

| Option | Type | Description |
| --- | --- | --- |
| `--developer-id` | long, required | ID of the developer linked to this record |
| `--name` | string, required | Display name of the application |
| `--published` | bool | Whether the application is published and available for installation |
| `--secret-key` | string | Secret key used to authenticate API calls from the application |
| `--short-description` | string, required | Brief summary of the application shown in listing views |
| `--description` | string | Full description of the application shown on the detail page |
| `--install-url` | string, required | URL that Nexudus calls when a location installs this application |
| `--required-roles` | list, repeat flag | List of required roles linked to this record |
| `--added-required-roles` | list, repeat flag | Roles to add to the required roles list (used in partial updates) |
| `--removed-required-roles` | list, repeat flag | Roles to remove from the required roles list (used in partial updates) |

#### Application update options

| Option | Type | Description |
| --- | --- | --- |
| `--developer-id` | long | ID of the developer linked to this record |
| `--name` | string | Display name of the application |
| `--published` | bool | Whether the application is published and available for installation |
| `--secret-key` | string | Secret key used to authenticate API calls from the application |
| `--short-description` | string | Brief summary of the application shown in listing views |
| `--description` | string | Full description of the application shown on the detail page |
| `--install-url` | string | URL that Nexudus calls when a location installs this application |
| `--required-roles` | list, repeat flag | List of required roles linked to this record |
| `--added-required-roles` | list, repeat flag | Roles to add to the required roles list (used in partial updates) |
| `--removed-required-roles` | list, repeat flag | Roles to remove from the required roles list (used in partial updates) |

**List properties (only returned by `get`, not by `list`):** `RequiredRoles`, `AddedRequiredRoles`, `RemovedRequiredRoles`

<!-- END:GENERATED entity=Applications -->
