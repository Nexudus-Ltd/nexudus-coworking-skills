# CoworkerBookingCredits

<!-- BEGIN:GENERATED entity=CoworkerBookingCredits -->

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

`--coworker-id`, `--business-id`, `--description`, `--total-credit`, `--valid-from`, `--expire-date`, `--cane-be-used-for-bookings`, `--cane-be-used-for-events`, `--is-universal-credit`, `--use-credit-price`, `--coworker-contract-unique-id`, `--applies-to-charges`

#### CoworkerBookingCredit create options

`--coworker-id` (required), `--business-id` (required), `--description`, `--elegible-resource-types` (list, repeat flag), `--added-elegible-resource-types` (list, repeat flag), `--removed-elegible-resource-types` (list, repeat flag), `--elegible-products` (list, repeat flag), `--added-elegible-products` (list, repeat flag), `--removed-elegible-products` (list, repeat flag), `--elegible-tariffs` (list, repeat flag), `--added-elegible-tariffs` (list, repeat flag), `--removed-elegible-tariffs` (list, repeat flag), `--total-credit` (required), `--valid-from`, `--expire-date`, `--cane-be-used-for-bookings`, `--cane-be-used-for-events`, `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--is-universal-credit`, `--coworker-booking-credit-uses` (list, repeat flag), `--added-coworker-booking-credit-uses` (list, repeat flag), `--removed-coworker-booking-credit-uses` (list, repeat flag), `--use-credit-price`, `--coworker-contract-unique-id`, `--elegible-passes` (list, repeat flag), `--added-elegible-passes` (list, repeat flag), `--removed-elegible-passes` (list, repeat flag), `--applies-to-charges`

#### CoworkerBookingCredit update options

`--coworker-id`, `--business-id`, `--description`, `--elegible-resource-types` (list, repeat flag), `--added-elegible-resource-types` (list, repeat flag), `--removed-elegible-resource-types` (list, repeat flag), `--elegible-products` (list, repeat flag), `--added-elegible-products` (list, repeat flag), `--removed-elegible-products` (list, repeat flag), `--elegible-tariffs` (list, repeat flag), `--added-elegible-tariffs` (list, repeat flag), `--removed-elegible-tariffs` (list, repeat flag), `--total-credit`, `--valid-from`, `--expire-date`, `--cane-be-used-for-bookings`, `--cane-be-used-for-events`, `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--is-universal-credit`, `--coworker-booking-credit-uses` (list, repeat flag), `--added-coworker-booking-credit-uses` (list, repeat flag), `--removed-coworker-booking-credit-uses` (list, repeat flag), `--use-credit-price`, `--coworker-contract-unique-id`, `--elegible-passes` (list, repeat flag), `--added-elegible-passes` (list, repeat flag), `--removed-elegible-passes` (list, repeat flag), `--applies-to-charges`

**List properties (only returned by `get`, not by `list`):** `ElegibleResourceTypes`, `AddedElegibleResourceTypes`, `RemovedElegibleResourceTypes`, `ElegibleProducts`, `AddedElegibleProducts`, `RemovedElegibleProducts`, `ElegibleTariffs`, `AddedElegibleTariffs`, `RemovedElegibleTariffs`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `CoworkerBookingCreditUses`, `AddedCoworkerBookingCreditUses`, `RemovedCoworkerBookingCreditUses`, `ElegiblePasses`, `AddedElegiblePasses`, `RemovedElegiblePasses`

<!-- END:GENERATED entity=CoworkerBookingCredits -->
