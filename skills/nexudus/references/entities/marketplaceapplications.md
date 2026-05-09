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

| Option | Type | Description |
| --- | --- | --- |
| `--developer-id` | long |  |
| `--name` | string |  |
| `--terms-and-conditions` | string |  |
| `--support-email` | string |  |
| `--developer-name` | string |  |
| `--published` | bool |  |
| `--secret-key` | string |  |
| `--short-description` | string |  |
| `--description` | string |  |
| `--notification-email` | string |  |
| `--notification-url` | string |  |
| `--new-logo-url` | string |  |
| `--clear-logo-file` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### MarketPlaceApplication create options

| Option | Type | Description |
| --- | --- | --- |
| `--developer-id` | long, required |  |
| `--name` | string, required |  |
| `--terms-and-conditions` | string |  |
| `--support-email` | string, required |  |
| `--developer-name` | string, required |  |
| `--published` | bool |  |
| `--secret-key` | string |  |
| `--short-description` | string, required |  |
| `--description` | string |  |
| `--notification-email` | string, required |  |
| `--notification-url` | string, required |  |
| `--new-logo-url` | string |  |
| `--clear-logo-file` | bool |  |

#### MarketPlaceApplication update options

| Option | Type | Description |
| --- | --- | --- |
| `--developer-id` | long |  |
| `--name` | string |  |
| `--terms-and-conditions` | string |  |
| `--support-email` | string |  |
| `--developer-name` | string |  |
| `--published` | bool |  |
| `--secret-key` | string |  |
| `--short-description` | string |  |
| `--description` | string |  |
| `--notification-email` | string |  |
| `--notification-url` | string |  |
| `--new-logo-url` | string |  |
| `--clear-logo-file` | bool |  |

<!-- END:GENERATED entity=MarketPlaceApplications -->
