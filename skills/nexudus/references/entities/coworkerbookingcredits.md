# CoworkerBookingCredits

<!-- BEGIN:GENERATED entity=CoworkerBookingCredits -->

A **CoworkerBookingCredit** is an amount of monetary credit assigned to a customer. Credits are typically created automatically when a customer's contract on a plan that includes a `TariffBookingCredit` renews, but can also be created manually.

Credit can be configured for two primary uses:

- **Bookings** — set `--cane-be-used-for-bookings` to allow the credit to pay for bookings. Use `--elegible-resource-types` to restrict the credit to specific resource types; if left empty the credit is valid for all resource types.
- **Events** — set `--cane-be-used-for-events` to allow the credit to pay for event sign-ups. Use `--event-categories` to restrict to specific event categories; if left empty the credit is valid for all events.

Setting `--is-universal-credit` enables the credit for products, time passes, and other charges. Use `--elegible-products`, `--elegible-passes`, and `--applies-to-charges` to restrict which products or passes the credit is valid for. If all restriction lists are empty the universal credit applies to all products, passes and charges.

Use `--valid-from` and `--expire-date` to control the validity window of the credit.

CoworkerBookingCredits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerbookingcredits list --agent` | List all coworkerbookingcredits |
| `nexudus coworkerbookingcredits list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerbookingcredits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerbookingcredits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerbookingcredits list --coworker-id <value> --business-id <value> --agent` | Filter coworkerbookingcredits by properties |
| `nexudus coworkerbookingcredits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerbookingcredits get <id> --agent` | Get single coworkerbookingcredit |
| `nexudus coworkerbookingcredits create --coworker-id <value> --business-id <value> --total-credit <value> --agent` | Create coworkerbookingcredit |
| `nexudus coworkerbookingcredits update <id> --name "New Name" --agent` | Update coworkerbookingcredit |
| `nexudus coworkerbookingcredits delete <id> --yes --agent` | Delete coworkerbookingcredit (no prompt) |

#### CoworkerBookingCredit list filter options

`--coworker-id` (long), `--business-id` (long), `--description`, `--total-credit` (decimal), `--from-total-credit` (range), `--to-total-credit` (range), `--valid-from` (DateTime), `--from-valid-from` (range), `--to-valid-from` (range), `--expire-date` (DateTime), `--from-expire-date` (range), `--to-expire-date` (range), `--cane-be-used-for-bookings` (bool), `--cane-be-used-for-events` (bool), `--is-universal-credit` (bool), `--use-credit-price` (bool), `--coworker-contract-unique-id`, `--applies-to-charges` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerBookingCredit create options

`--coworker-id` (long, required), `--business-id` (long, required), `--description`, `--elegible-resource-types` (list, repeat flag), `--added-elegible-resource-types` (list, repeat flag), `--removed-elegible-resource-types` (list, repeat flag), `--elegible-products` (list, repeat flag), `--added-elegible-products` (list, repeat flag), `--removed-elegible-products` (list, repeat flag), `--elegible-tariffs` (list, repeat flag), `--added-elegible-tariffs` (list, repeat flag), `--removed-elegible-tariffs` (list, repeat flag), `--total-credit` (decimal, required), `--valid-from` (DateTime), `--expire-date` (DateTime), `--cane-be-used-for-bookings` (bool), `--cane-be-used-for-events` (bool), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--is-universal-credit` (bool), `--use-credit-price` (bool), `--coworker-contract-unique-id`, `--elegible-passes` (list, repeat flag), `--added-elegible-passes` (list, repeat flag), `--removed-elegible-passes` (list, repeat flag), `--applies-to-charges` (bool)

#### CoworkerBookingCredit update options

`--coworker-id` (long), `--business-id` (long), `--description`, `--elegible-resource-types` (list, repeat flag), `--added-elegible-resource-types` (list, repeat flag), `--removed-elegible-resource-types` (list, repeat flag), `--elegible-products` (list, repeat flag), `--added-elegible-products` (list, repeat flag), `--removed-elegible-products` (list, repeat flag), `--elegible-tariffs` (list, repeat flag), `--added-elegible-tariffs` (list, repeat flag), `--removed-elegible-tariffs` (list, repeat flag), `--total-credit` (decimal), `--valid-from` (DateTime), `--expire-date` (DateTime), `--cane-be-used-for-bookings` (bool), `--cane-be-used-for-events` (bool), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--is-universal-credit` (bool), `--use-credit-price` (bool), `--coworker-contract-unique-id`, `--elegible-passes` (list, repeat flag), `--added-elegible-passes` (list, repeat flag), `--removed-elegible-passes` (list, repeat flag), `--applies-to-charges` (bool)

### CoworkerBookingCredit (key fields)

`Id`, `BusinessName`, `TariffBookingCreditName`

**List properties (only returned by `get`, not by `list`):** `ElegibleResourceTypes`, `AddedElegibleResourceTypes`, `RemovedElegibleResourceTypes`, `ElegibleProducts`, `AddedElegibleProducts`, `RemovedElegibleProducts`, `ElegibleTariffs`, `AddedElegibleTariffs`, `RemovedElegibleTariffs`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `ElegiblePasses`, `AddedElegiblePasses`, `RemovedElegiblePasses`

<!-- END:GENERATED entity=CoworkerBookingCredits -->
