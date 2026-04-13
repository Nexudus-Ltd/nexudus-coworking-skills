# InstalledApplications

<!-- BEGIN:GENERATED entity=InstalledApplications -->

InstalledApplications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus installedapplications list --agent` | List all installedapplications |
| `nexudus installedapplications list --id <id> --agent` | Filter by single ID |
| `nexudus installedapplications list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus installedapplications list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus installedapplications list --application-id <value> --business-id <value> --agent` | Filter installedapplications by properties |
| `nexudus installedapplications list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus installedapplications get <id> --agent` | Get single installedapplication |
| `nexudus installedapplications create --application-id <value> --business-id <value> --agent` | Create installedapplication |
| `nexudus installedapplications update <id> --name "New Name" --agent` | Update installedapplication |
| `nexudus installedapplications delete <id> --yes --agent` | Delete installedapplication (no prompt) |

#### InstalledApplication list filter options

`--application-id` (long), `--business-id` (long), `--requires-approval` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### InstalledApplication create options

`--application-id` (long, required), `--business-id` (long, required), `--requires-approval` (bool)

#### InstalledApplication update options

`--application-id` (long), `--business-id` (long), `--requires-approval` (bool)

<!-- END:GENERATED entity=InstalledApplications -->
