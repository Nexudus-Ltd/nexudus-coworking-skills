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

`--coworker-id` (long), `--business-id` (long), `--time-pass-id` (long), `--notes`, `--purchase-order`, `--used` (bool), `--free` (bool), `--price` (decimal), `--from-price` (range), `--to-price` (range), `--create-multiple` (int), `--from-create-multiple` (range), `--to-create-multiple` (range), `--expire-date` (DateTime), `--from-expire-date` (range), `--to-expire-date` (range), `--tariff-time-pass-unique-id`, `--coworker-product-unique-id`, `--coworker-contract-unique-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerTimePass create options

`--coworker-id` (long, required), `--business-id` (long, required), `--time-pass-id` (long, required), `--notes`, `--purchase-order`, `--used` (bool), `--free` (bool), `--price` (decimal), `--create-multiple` (int, required), `--expire-date` (DateTime), `--tariff-time-pass-unique-id`, `--coworker-product-unique-id`, `--coworker-contract-unique-id`

#### CoworkerTimePass update options

`--coworker-id` (long), `--business-id` (long), `--time-pass-id` (long), `--notes`, `--purchase-order`, `--used` (bool), `--free` (bool), `--price` (decimal), `--expire-date` (DateTime), `--tariff-time-pass-unique-id`, `--coworker-product-unique-id`, `--coworker-contract-unique-id`

<!-- END:GENERATED entity=CoworkerTimePasses -->
