# InstalledMarketPlaceApplications

<!-- BEGIN:GENERATED entity=InstalledMarketPlaceApplications -->

An **InstalledMarketPlaceApplication** represents a marketplace application that has been installed for a business. Marketplace apps extend platform functionality with integrations, automations, and additional features.

InstalledMarketPlaceApplications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus installedmarketplaceapplications list --agent` | List all installedmarketplaceapplications |
| `nexudus installedmarketplaceapplications list --id <id> --agent` | Filter by single ID |
| `nexudus installedmarketplaceapplications list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus installedmarketplaceapplications list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus installedmarketplaceapplications list --market-place-application-id <value> --business-id <value> --agent` | Filter installedmarketplaceapplications by properties |
| `nexudus installedmarketplaceapplications list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus installedmarketplaceapplications list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus installedmarketplaceapplications get <id> --agent` | Get single installedmarketplaceapplication |
| `nexudus installedmarketplaceapplications create --market-place-application-id <value> --business-id <value> --agent` | Create installedmarketplaceapplication |
| `nexudus installedmarketplaceapplications update <id> --name "New Name" --agent` | Update installedmarketplaceapplication |
| `nexudus installedmarketplaceapplications delete <id> --yes --agent` | Delete installedmarketplaceapplication (no prompt) |

#### InstalledMarketPlaceApplication list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--market-place-application-id` | long | ID of the market place application linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--provide-products` | bool | Whether provide products is enabled |
| `--provide-resources` | bool | Whether provide resources is enabled |
| `--provide-events` | bool | Whether provide events is enabled |
| `--provide-tariffs` | bool | Whether provide tariffs is enabled |
| `--provide-resource-availability` | bool | Whether provide resource availability is enabled |
| `--provide-resource-prices` | bool | Whether provide resource prices is enabled |
| `--accept-bookings` | bool | Whether accept bookings is enabled |
| `--accept-event-signups` | bool | Whether accept event signups is enabled |
| `--accept-payment-requests` | bool | Whether accept payment requests is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### InstalledMarketPlaceApplication sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### InstalledMarketPlaceApplication create options

| Option | Type | Description |
| --- | --- | --- |
| `--market-place-application-id` | long, required | ID of the market place application linked to this record |
| `--business-id` | long, required | ID of the business linked to this record |
| `--provide-products` | bool | Whether provide products is enabled |
| `--provide-resources` | bool | Whether provide resources is enabled |
| `--provide-events` | bool | Whether provide events is enabled |
| `--provide-tariffs` | bool | Whether provide tariffs is enabled |
| `--provide-resource-availability` | bool | Whether provide resource availability is enabled |
| `--provide-resource-prices` | bool | Whether provide resource prices is enabled |
| `--accept-bookings` | bool | Whether accept bookings is enabled |
| `--accept-event-signups` | bool | Whether accept event signups is enabled |
| `--accept-payment-requests` | bool | Whether accept payment requests is enabled |

#### InstalledMarketPlaceApplication update options

| Option | Type | Description |
| --- | --- | --- |
| `--market-place-application-id` | long | ID of the market place application linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--provide-products` | bool | Whether provide products is enabled |
| `--provide-resources` | bool | Whether provide resources is enabled |
| `--provide-events` | bool | Whether provide events is enabled |
| `--provide-tariffs` | bool | Whether provide tariffs is enabled |
| `--provide-resource-availability` | bool | Whether provide resource availability is enabled |
| `--provide-resource-prices` | bool | Whether provide resource prices is enabled |
| `--accept-bookings` | bool | Whether accept bookings is enabled |
| `--accept-event-signups` | bool | Whether accept event signups is enabled |
| `--accept-payment-requests` | bool | Whether accept payment requests is enabled |

<!-- END:GENERATED entity=InstalledMarketPlaceApplications -->
