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

`--market-place-application-id`, `--business-id`, `--provide-products`, `--provide-resources`, `--provide-events`, `--provide-tariffs`, `--provide-resource-availability`, `--provide-resource-prices`, `--accept-bookings`, `--accept-event-signups`, `--accept-payment-requests`

#### InstalledMarketPlaceApplication create options

`--market-place-application-id` (required), `--business-id` (required), `--provide-products`, `--provide-resources`, `--provide-events`, `--provide-tariffs`, `--provide-resource-availability`, `--provide-resource-prices`, `--accept-bookings`, `--accept-event-signups`, `--accept-payment-requests`

#### InstalledMarketPlaceApplication update options

`--market-place-application-id`, `--business-id`, `--provide-products`, `--provide-resources`, `--provide-events`, `--provide-tariffs`, `--provide-resource-availability`, `--provide-resource-prices`, `--accept-bookings`, `--accept-event-signups`, `--accept-payment-requests`

<!-- END:GENERATED entity=InstalledMarketPlaceApplications -->
