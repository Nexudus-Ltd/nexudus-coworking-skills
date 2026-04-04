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
| `nexudus applications get <id> --agent` | Get single application |
| `nexudus applications create --developer-id <value> --name <value> --short-description <value> --install-url <value> --agent` | Create application |
| `nexudus applications update <id> --name "New Name" --agent` | Update application |
| `nexudus applications delete <id> --yes --agent` | Delete application (no prompt) |

#### Application list filter options

`--developer-id`, `--name`, `--published`, `--secret-key`, `--short-description`, `--description`, `--install-url`

#### Application create options

`--developer-id` (required), `--name` (required), `--published`, `--secret-key`, `--short-description` (required), `--description`, `--install-url` (required), `--required-roles` (list, repeat flag), `--added-required-roles` (list, repeat flag), `--removed-required-roles` (list, repeat flag)

#### Application update options

`--developer-id`, `--name`, `--published`, `--secret-key`, `--short-description`, `--description`, `--install-url`, `--required-roles` (list, repeat flag), `--added-required-roles` (list, repeat flag), `--removed-required-roles` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `RequiredRoles`, `AddedRequiredRoles`, `RemovedRequiredRoles`

<!-- END:GENERATED entity=Applications -->
