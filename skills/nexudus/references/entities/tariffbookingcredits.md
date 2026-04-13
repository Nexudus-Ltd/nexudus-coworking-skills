# TariffBookingCredits

<!-- BEGIN:GENERATED entity=TariffBookingCredits -->

A **TariffBookingCredit** represents an amount of credit linked to a plan (`Tariff`). When a customer's contract on that plan renews, the credit is automatically released as a `CoworkerBookingCredit` on the customer's account.

Credit can be configured for two primary uses:

- **Bookings** — set `--can-be-used-for-bookings` to allow the credit to pay for bookings. Use `--elegible-resource-types` to restrict the credit to specific resource types; if left empty the credit is valid for all resource types.
- **Events** — set `--can-be-used-for-events` to allow the credit to pay for event sign-ups. Use `--event-categories` to restrict to specific event categories; if left empty the credit is valid for all events.

Setting `--is-universal-credit` enables the credit for products, time passes, and other charges. Use `--elegible-products`, `--elegible-passes`, and `--applies-to-charges` to restrict which products or passes the credit is valid for. If all restriction lists are empty the universal credit applies to all products, passes and charges.

Use `--service-renewal-time` to control how often the credit is renewed (e.g. weekly, monthly).

TariffBookingCredits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffbookingcredits list --agent` | List all tariffbookingcredits |
| `nexudus tariffbookingcredits list --id <id> --agent` | Filter by single ID |
| `nexudus tariffbookingcredits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffbookingcredits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffbookingcredits list --name <value> --credit <value> --agent` | Filter tariffbookingcredits by properties |
| `nexudus tariffbookingcredits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffbookingcredits get <id> --agent` | Get single tariffbookingcredit |
| `nexudus tariffbookingcredits create --name <value> --tariff-id <value> --credit <value> --service-renewal-time <value> --agent` | Create tariffbookingcredit |
| `nexudus tariffbookingcredits update <id> --name "New Name" --agent` | Update tariffbookingcredit |
| `nexudus tariffbookingcredits delete <id> --yes --agent` | Delete tariffbookingcredit (no prompt) |

#### TariffBookingCredit list filter options

`--name`, `--tariff-id` (long), `--credit` (decimal), `--from-credit` (range), `--to-credit` (range), `--can-be-used-for-bookings` (bool), `--can-be-used-for-events` (bool), `--service-renewal-time` (enum), `--is-universal-credit` (bool), `--applies-to-charges` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### TariffBookingCredit create options

`--name` (required), `--tariff-id` (long, required), `--elegible-resource-types` (list, repeat flag), `--added-elegible-resource-types` (list, repeat flag), `--removed-elegible-resource-types` (list, repeat flag), `--elegible-products` (list, repeat flag), `--added-elegible-products` (list, repeat flag), `--removed-elegible-products` (list, repeat flag), `--elegible-tariffs` (list, repeat flag), `--added-elegible-tariffs` (list, repeat flag), `--removed-elegible-tariffs` (list, repeat flag), `--credit` (decimal, required), `--can-be-used-for-bookings` (bool), `--can-be-used-for-events` (bool), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--service-renewal-time` (enum, required), `--is-universal-credit` (bool), `--elegible-passes` (list, repeat flag), `--added-elegible-passes` (list, repeat flag), `--removed-elegible-passes` (list, repeat flag), `--applies-to-charges` (bool)

#### TariffBookingCredit update options

`--name`, `--tariff-id` (long), `--elegible-resource-types` (list, repeat flag), `--added-elegible-resource-types` (list, repeat flag), `--removed-elegible-resource-types` (list, repeat flag), `--elegible-products` (list, repeat flag), `--added-elegible-products` (list, repeat flag), `--removed-elegible-products` (list, repeat flag), `--elegible-tariffs` (list, repeat flag), `--added-elegible-tariffs` (list, repeat flag), `--removed-elegible-tariffs` (list, repeat flag), `--credit` (decimal), `--can-be-used-for-bookings` (bool), `--can-be-used-for-events` (bool), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--service-renewal-time` (enum), `--is-universal-credit` (bool), `--elegible-passes` (list, repeat flag), `--added-elegible-passes` (list, repeat flag), `--removed-elegible-passes` (list, repeat flag), `--applies-to-charges` (bool)

### TariffBookingCredit (key fields)

`Id`, `Name`, `TariffName`, `Credit`, `ServiceRenewalTime`

**List properties (only returned by `get`, not by `list`):** `ElegibleResourceTypes`, `AddedElegibleResourceTypes`, `RemovedElegibleResourceTypes`, `ElegibleProducts`, `AddedElegibleProducts`, `RemovedElegibleProducts`, `ElegibleTariffs`, `AddedElegibleTariffs`, `RemovedElegibleTariffs`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `ElegiblePasses`, `AddedElegiblePasses`, `RemovedElegiblePasses`

#### TariffBookingCredit enum values

| Option | Valid values |
| ------ | ------------ |
| `--service-renewal-time` | `1` Week, `2` CalendarMonth, `3` TariffMonth, `4` Year, `5` Day |

<!-- END:GENERATED entity=TariffBookingCredits -->
