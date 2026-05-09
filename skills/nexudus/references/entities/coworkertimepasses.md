# CoworkerTimePasses

<!-- BEGIN:GENERATED entity=CoworkerTimePasses -->

A **CoworkerTimePass** represents a time pass assigned to a customer. Time passes can be assigned directly, granted by a product purchase (`CoworkerProductUniqueId`), or included in a pricing plan (`TariffTimePassUniqueId`).

Each time pass tracks its usage status (`Used`, `UsedDate`), remaining and total uses, and whether the customer is currently checked in. Time passes may have an expiration date and can be free or priced.

Use `CreateMultiple` when creating to issue several time passes at once. The `IsFromTariff` and `IsPayAsYouGo` flags indicate the origin and billing model of the time pass.

CoworkerTimePasses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkertimepasses list --agent` | List all coworkertimepasses |
| `nexudus coworkertimepasses list --id <id> --agent` | Filter by single ID |
| `nexudus coworkertimepasses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkertimepasses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkertimepasses list --coworker-id <value> --business-id <value> --agent` | Filter coworkertimepasses by properties |
| `nexudus coworkertimepasses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkertimepasses get <id> --agent` | Get single coworkertimepass |
| `nexudus coworkertimepasses create --coworker-id <value> --business-id <value> --time-pass-id <value> --create-multiple <value> --agent` | Create coworkertimepass |
| `nexudus coworkertimepasses update <id> --name "New Name" --agent` | Update coworkertimepass |
| `nexudus coworkertimepasses delete <id> --yes --agent` | Delete coworkertimepass (no prompt) |

#### CoworkerTimePass list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | The customer who owns this time pass |
| `--business-id` | long | The business (location) this time pass belongs to |
| `--time-pass-id` | long | The time pass definition this is an instance of |
| `--notes` | string | Optional notes for this time pass |
| `--purchase-order` | string | Purchase order reference |
| `--used` | bool | Whether this time pass has been used |
| `--free` | bool | Whether this time pass is free of charge |
| `--price` | decimal | Custom price for this time pass |
| `--from-price` | range | |
| `--to-price` | range | |
| `--create-multiple` | int | Number of time passes to create at once |
| `--from-create-multiple` | range | |
| `--to-create-multiple` | range | |
| `--expire-date` | DateTime | Expiration date for this time pass |
| `--from-expire-date` | range | |
| `--to-expire-date` | range | |
| `--tariff-time-pass-unique-id` | string | Unique identifier linking this time pass to a tariff time pass allocation |
| `--coworker-product-unique-id` | string | Unique identifier linking this time pass to a customer product purchase |
| `--coworker-contract-unique-id` | string | Unique identifier linking this time pass to a customer contract |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerTimePass create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | The customer who owns this time pass |
| `--business-id` | long, required | The business (location) this time pass belongs to |
| `--time-pass-id` | long, required | The time pass definition this is an instance of |
| `--notes` | string | Optional notes for this time pass |
| `--purchase-order` | string | Purchase order reference |
| `--used` | bool | Whether this time pass has been used |
| `--free` | bool | Whether this time pass is free of charge |
| `--price` | decimal | Custom price for this time pass |
| `--create-multiple` | int, required | Number of time passes to create at once |
| `--expire-date` | DateTime | Expiration date for this time pass |
| `--tariff-time-pass-unique-id` | string | Unique identifier linking this time pass to a tariff time pass allocation |
| `--coworker-product-unique-id` | string | Unique identifier linking this time pass to a customer product purchase |
| `--coworker-contract-unique-id` | string | Unique identifier linking this time pass to a customer contract |

#### CoworkerTimePass update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | The customer who owns this time pass |
| `--business-id` | long | The business (location) this time pass belongs to |
| `--time-pass-id` | long | The time pass definition this is an instance of |
| `--notes` | string | Optional notes for this time pass |
| `--purchase-order` | string | Purchase order reference |
| `--used` | bool | Whether this time pass has been used |
| `--free` | bool | Whether this time pass is free of charge |
| `--price` | decimal | Custom price for this time pass |
| `--expire-date` | DateTime | Expiration date for this time pass |
| `--tariff-time-pass-unique-id` | string | Unique identifier linking this time pass to a tariff time pass allocation |
| `--coworker-product-unique-id` | string | Unique identifier linking this time pass to a customer product purchase |
| `--coworker-contract-unique-id` | string | Unique identifier linking this time pass to a customer contract |

<!-- END:GENERATED entity=CoworkerTimePasses -->
