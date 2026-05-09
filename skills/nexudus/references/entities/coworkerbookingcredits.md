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

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer this credit is assigned to |
| `--business-id` | long | ID of the location issuing the credit |
| `--description` | string | Optional description or label for this credit |
| `--total-credit` | decimal | Total credit amount originally assigned |
| `--from-total-credit` | range | |
| `--to-total-credit` | range | |
| `--valid-from` | DateTime | Date from which this credit is valid |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--expire-date` | DateTime | Date on which this credit expires |
| `--from-expire-date` | range | |
| `--to-expire-date` | range | |
| `--cane-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types with --elegible-resource-types |
| `--cane-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with --event-categories |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with --elegible-products, --elegible-passes and --applies-to-charges; if all are empty the credit applies to all products, passes and charges |
| `--use-credit-price` | bool | Whether to use the credit price instead of the standard booking price when this credit is applied |
| `--coworker-contract-unique-id` | string | Unique ID of the contract that originated this credit |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerBookingCredit create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer this credit is assigned to |
| `--business-id` | long, required | ID of the location issuing the credit |
| `--description` | string | Optional description or label for this credit |
| `--elegible-resource-types` | list, repeat flag | Resource types this credit can be used for. If empty, the credit is valid for all resource types |
| `--added-elegible-resource-types` | list, repeat flag | Resource type IDs to add to ElegibleResourceTypes |
| `--removed-elegible-resource-types` | list, repeat flag | Resource type IDs to remove from ElegibleResourceTypes |
| `--elegible-products` | list, repeat flag | Products this credit can be used for. If empty, applies to all products |
| `--added-elegible-products` | list, repeat flag | Product IDs to add to ElegibleProducts |
| `--removed-elegible-products` | list, repeat flag | Product IDs to remove from ElegibleProducts |
| `--elegible-tariffs` | list, repeat flag | Plans (tariffs) this credit is restricted to. If empty, applies to customers on any plan |
| `--added-elegible-tariffs` | list, repeat flag | Plan IDs to add to ElegibleTariffs |
| `--removed-elegible-tariffs` | list, repeat flag | Plan IDs to remove from ElegibleTariffs |
| `--total-credit` | decimal, required | Total credit amount originally assigned |
| `--valid-from` | DateTime | Date from which this credit is valid |
| `--expire-date` | DateTime | Date on which this credit expires |
| `--cane-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types with --elegible-resource-types |
| `--cane-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with --event-categories |
| `--event-categories` | list, repeat flag | Event categories this credit can be used for. If empty, applies to all event categories |
| `--added-event-categories` | list, repeat flag | Event category IDs to add to EventCategories |
| `--removed-event-categories` | list, repeat flag | Event category IDs to remove from EventCategories |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with --elegible-products, --elegible-passes and --applies-to-charges; if all are empty the credit applies to all products, passes and charges |
| `--use-credit-price` | bool | Whether to use the credit price instead of the standard booking price when this credit is applied |
| `--coworker-contract-unique-id` | string | Unique ID of the contract that originated this credit |
| `--elegible-passes` | list, repeat flag | Time passes this credit can be used for. If empty, applies to all passes |
| `--added-elegible-passes` | list, repeat flag | Pass IDs to add to ElegiblePasses |
| `--removed-elegible-passes` | list, repeat flag | Pass IDs to remove from ElegiblePasses |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges |

#### CoworkerBookingCredit update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer this credit is assigned to |
| `--business-id` | long | ID of the location issuing the credit |
| `--description` | string | Optional description or label for this credit |
| `--elegible-resource-types` | list, repeat flag | Resource types this credit can be used for. If empty, the credit is valid for all resource types |
| `--added-elegible-resource-types` | list, repeat flag | Resource type IDs to add to ElegibleResourceTypes |
| `--removed-elegible-resource-types` | list, repeat flag | Resource type IDs to remove from ElegibleResourceTypes |
| `--elegible-products` | list, repeat flag | Products this credit can be used for. If empty, applies to all products |
| `--added-elegible-products` | list, repeat flag | Product IDs to add to ElegibleProducts |
| `--removed-elegible-products` | list, repeat flag | Product IDs to remove from ElegibleProducts |
| `--elegible-tariffs` | list, repeat flag | Plans (tariffs) this credit is restricted to. If empty, applies to customers on any plan |
| `--added-elegible-tariffs` | list, repeat flag | Plan IDs to add to ElegibleTariffs |
| `--removed-elegible-tariffs` | list, repeat flag | Plan IDs to remove from ElegibleTariffs |
| `--total-credit` | decimal | Total credit amount originally assigned |
| `--valid-from` | DateTime | Date from which this credit is valid |
| `--expire-date` | DateTime | Date on which this credit expires |
| `--cane-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types with --elegible-resource-types |
| `--cane-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with --event-categories |
| `--event-categories` | list, repeat flag | Event categories this credit can be used for. If empty, applies to all event categories |
| `--added-event-categories` | list, repeat flag | Event category IDs to add to EventCategories |
| `--removed-event-categories` | list, repeat flag | Event category IDs to remove from EventCategories |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with --elegible-products, --elegible-passes and --applies-to-charges; if all are empty the credit applies to all products, passes and charges |
| `--use-credit-price` | bool | Whether to use the credit price instead of the standard booking price when this credit is applied |
| `--coworker-contract-unique-id` | string | Unique ID of the contract that originated this credit |
| `--elegible-passes` | list, repeat flag | Time passes this credit can be used for. If empty, applies to all passes |
| `--added-elegible-passes` | list, repeat flag | Pass IDs to add to ElegiblePasses |
| `--removed-elegible-passes` | list, repeat flag | Pass IDs to remove from ElegiblePasses |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges |

### CoworkerBookingCredit (key fields)

`Id`, `BusinessName`, `TariffBookingCreditName`

**List properties (only returned by `get`, not by `list`):** `ElegibleResourceTypes`, `AddedElegibleResourceTypes`, `RemovedElegibleResourceTypes`, `ElegibleProducts`, `AddedElegibleProducts`, `RemovedElegibleProducts`, `ElegibleTariffs`, `AddedElegibleTariffs`, `RemovedElegibleTariffs`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `ElegiblePasses`, `AddedElegiblePasses`, `RemovedElegiblePasses`

<!-- END:GENERATED entity=CoworkerBookingCredits -->
