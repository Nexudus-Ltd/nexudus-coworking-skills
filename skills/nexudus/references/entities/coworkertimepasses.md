# CoworkerTimePasses

<!-- BEGIN:GENERATED entity=CoworkerTimePasses -->

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

`--coworker-id`, `--business-id`, `--time-pass-id`, `--notes`, `--purchase-order`, `--used`, `--free`, `--price`, `--create-multiple`, `--expire-date`, `--tariff-time-pass-unique-id`, `--coworker-product-unique-id`, `--coworker-contract-unique-id`

#### CoworkerTimePass create options

`--coworker-id` (required), `--business-id` (required), `--time-pass-id` (required), `--notes`, `--purchase-order`, `--used`, `--free`, `--price`, `--create-multiple` (required), `--expire-date`, `--tariff-time-pass-unique-id`, `--coworker-product-unique-id`, `--coworker-contract-unique-id`

#### CoworkerTimePass update options

`--coworker-id`, `--business-id`, `--time-pass-id`, `--notes`, `--purchase-order`, `--used`, `--free`, `--price`, `--expire-date`, `--tariff-time-pass-unique-id`, `--coworker-product-unique-id`, `--coworker-contract-unique-id`

<!-- END:GENERATED entity=CoworkerTimePasses -->
