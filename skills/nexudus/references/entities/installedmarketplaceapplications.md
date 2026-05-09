# InstalledMarketPlaceApplications

<!-- BEGIN:GENERATED entity=InstalledMarketPlaceApplications -->

InstalledMarketPlaceApplications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus installedmarketplaceapplications list --agent` | List all installedmarketplaceapplications |
| `nexudus installedmarketplaceapplications list --id <id> --agent` | Filter by single ID |
| `nexudus installedmarketplaceapplications list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus installedmarketplaceapplications list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus installedmarketplaceapplications list --market-place-application-id <value> --business-id <value> --agent` | Filter installedmarketplaceapplications by properties |
| `nexudus installedmarketplaceapplications list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus installedmarketplaceapplications get <id> --agent` | Get single installedmarketplaceapplication |
| `nexudus installedmarketplaceapplications create --market-place-application-id <value> --business-id <value> --agent` | Create installedmarketplaceapplication |
| `nexudus installedmarketplaceapplications update <id> --name "New Name" --agent` | Update installedmarketplaceapplication |
| `nexudus installedmarketplaceapplications delete <id> --yes --agent` | Delete installedmarketplaceapplication (no prompt) |

#### InstalledMarketPlaceApplication list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--market-place-application-id` | long |  |
| `--business-id` | long |  |
| `--provide-products` | bool |  |
| `--provide-resources` | bool |  |
| `--provide-events` | bool |  |
| `--provide-tariffs` | bool |  |
| `--provide-resource-availability` | bool |  |
| `--provide-resource-prices` | bool |  |
| `--accept-bookings` | bool |  |
| `--accept-event-signups` | bool |  |
| `--accept-payment-requests` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### InstalledMarketPlaceApplication create options

| Option | Type | Description |
| --- | --- | --- |
| `--market-place-application-id` | long, required |  |
| `--business-id` | long, required |  |
| `--provide-products` | bool |  |
| `--provide-resources` | bool |  |
| `--provide-events` | bool |  |
| `--provide-tariffs` | bool |  |
| `--provide-resource-availability` | bool |  |
| `--provide-resource-prices` | bool |  |
| `--accept-bookings` | bool |  |
| `--accept-event-signups` | bool |  |
| `--accept-payment-requests` | bool |  |

#### InstalledMarketPlaceApplication update options

| Option | Type | Description |
| --- | --- | --- |
| `--market-place-application-id` | long |  |
| `--business-id` | long |  |
| `--provide-products` | bool |  |
| `--provide-resources` | bool |  |
| `--provide-events` | bool |  |
| `--provide-tariffs` | bool |  |
| `--provide-resource-availability` | bool |  |
| `--provide-resource-prices` | bool |  |
| `--accept-bookings` | bool |  |
| `--accept-event-signups` | bool |  |
| `--accept-payment-requests` | bool |  |

<!-- END:GENERATED entity=InstalledMarketPlaceApplications -->
