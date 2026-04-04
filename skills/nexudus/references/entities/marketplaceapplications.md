# MarketPlaceApplications

<!-- BEGIN:GENERATED entity=MarketPlaceApplications -->

MarketPlaceApplications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus marketplaceapplications list --agent` | List all marketplaceapplications |
| `nexudus marketplaceapplications list --id <id> --agent` | Filter by single ID |
| `nexudus marketplaceapplications list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus marketplaceapplications list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus marketplaceapplications list --developer-id <value> --name <value> --agent` | Filter marketplaceapplications by properties |
| `nexudus marketplaceapplications list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus marketplaceapplications get <id> --agent` | Get single marketplaceapplication |
| `nexudus marketplaceapplications create --developer-id <value> --name <value> --support-email <value> --developer-name <value> --short-description <value> --notification-email <value> --notification-url <value> --agent` | Create marketplaceapplication |
| `nexudus marketplaceapplications update <id> --name "New Name" --agent` | Update marketplaceapplication |
| `nexudus marketplaceapplications delete <id> --yes --agent` | Delete marketplaceapplication (no prompt) |

#### MarketPlaceApplication list filter options

`--developer-id`, `--name`, `--terms-and-conditions`, `--support-email`, `--developer-name`, `--published`, `--secret-key`, `--short-description`, `--description`, `--notification-email`, `--notification-url`, `--new-logo-url`, `--clear-logo-file`

#### MarketPlaceApplication create options

`--developer-id` (required), `--name` (required), `--terms-and-conditions`, `--support-email` (required), `--developer-name` (required), `--published`, `--secret-key`, `--short-description` (required), `--description`, `--notification-email` (required), `--notification-url` (required), `--new-logo-url`, `--clear-logo-file`, `--installations` (list, repeat flag), `--added-installations` (list, repeat flag), `--removed-installations` (list, repeat flag)

#### MarketPlaceApplication update options

`--developer-id`, `--name`, `--terms-and-conditions`, `--support-email`, `--developer-name`, `--published`, `--secret-key`, `--short-description`, `--description`, `--notification-email`, `--notification-url`, `--new-logo-url`, `--clear-logo-file`, `--installations` (list, repeat flag), `--added-installations` (list, repeat flag), `--removed-installations` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Installations`, `AddedInstallations`, `RemovedInstallations`

<!-- END:GENERATED entity=MarketPlaceApplications -->
