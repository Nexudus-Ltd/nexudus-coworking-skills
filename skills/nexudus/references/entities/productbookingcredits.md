# ProductBookingCredits

<!-- BEGIN:GENERATED entity=ProductBookingCredits -->

A **ProductBookingCredit** represents an amount of credit linked to a `Product`. When a customer purchases the product, the credit is automatically released as a `CoworkerBookingCredit` on the customer's account.

Credit can be configured for two primary uses:

- **Bookings** — set `--can-be-used-for-bookings` to allow the credit to pay for bookings. Use `--elegible-resource-types` to restrict the credit to specific resource types; if left empty the credit is valid for all resource types.
- **Events** — set `--can-be-used-for-events` to allow the credit to pay for event sign-ups. Use `--event-categories` to restrict to specific event categories; if left empty the credit is valid for all events.

Setting `--is-universal-credit` enables the credit for products, time passes, and other charges. Use `--elegible-products`, `--elegible-passes`, and `--applies-to-charges` to restrict which products or passes the credit is valid for. If all restriction lists are empty the universal credit applies to all products, passes and charges.

Use `--expiration-type` and `--expires-in` to control when the released credit expires.

ProductBookingCredits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus productbookingcredits list --agent` | List all productbookingcredits |
| `nexudus productbookingcredits list --id <id> --agent` | Filter by single ID |
| `nexudus productbookingcredits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus productbookingcredits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus productbookingcredits list --name <value> --credit <value> --agent` | Filter productbookingcredits by properties |
| `nexudus productbookingcredits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus productbookingcredits get <id> --agent` | Get single productbookingcredit |
| `nexudus productbookingcredits create --name <value> --product-id <value> --credit <value> --agent` | Create productbookingcredit |
| `nexudus productbookingcredits update <id> --name "New Name" --agent` | Update productbookingcredit |
| `nexudus productbookingcredits delete <id> --yes --agent` | Delete productbookingcredit (no prompt) |

#### ProductBookingCredit list filter options

`--name`, `--product-id`, `--credit`, `--expire-time-in-months`, `--expire-time-in-weeks`, `--can-be-used-for-bookings`, `--can-be-used-for-events`, `--expiration-type`, `--expires-in`, `--is-universal-credit`, `--applies-to-charges`

#### ProductBookingCredit create options

`--name` (required), `--product-id` (required), `--elegible-resource-types` (list, repeat flag), `--added-elegible-resource-types` (list, repeat flag), `--removed-elegible-resource-types` (list, repeat flag), `--elegible-products` (list, repeat flag), `--added-elegible-products` (list, repeat flag), `--removed-elegible-products` (list, repeat flag), `--elegible-tariffs` (list, repeat flag), `--added-elegible-tariffs` (list, repeat flag), `--removed-elegible-tariffs` (list, repeat flag), `--credit` (required), `--expire-time-in-months`, `--expire-time-in-weeks`, `--can-be-used-for-bookings`, `--can-be-used-for-events`, `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--expiration-type`, `--expires-in`, `--is-universal-credit`, `--elegible-passes` (list, repeat flag), `--added-elegible-passes` (list, repeat flag), `--removed-elegible-passes` (list, repeat flag), `--applies-to-charges`

#### ProductBookingCredit update options

`--name`, `--product-id`, `--elegible-resource-types` (list, repeat flag), `--added-elegible-resource-types` (list, repeat flag), `--removed-elegible-resource-types` (list, repeat flag), `--elegible-products` (list, repeat flag), `--added-elegible-products` (list, repeat flag), `--removed-elegible-products` (list, repeat flag), `--elegible-tariffs` (list, repeat flag), `--added-elegible-tariffs` (list, repeat flag), `--removed-elegible-tariffs` (list, repeat flag), `--credit`, `--expire-time-in-months`, `--expire-time-in-weeks`, `--can-be-used-for-bookings`, `--can-be-used-for-events`, `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--expiration-type`, `--expires-in`, `--is-universal-credit`, `--elegible-passes` (list, repeat flag), `--added-elegible-passes` (list, repeat flag), `--removed-elegible-passes` (list, repeat flag), `--applies-to-charges`

### ProductBookingCredit (key fields)

`Id`, `Name`, `ProductName`, `Credit`, `IsUniversalCredit`

**List properties (only returned by `get`, not by `list`):** `ElegibleResourceTypes`, `AddedElegibleResourceTypes`, `RemovedElegibleResourceTypes`, `ElegibleProducts`, `AddedElegibleProducts`, `RemovedElegibleProducts`, `ElegibleTariffs`, `AddedElegibleTariffs`, `RemovedElegibleTariffs`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `ElegiblePasses`, `AddedElegiblePasses`, `RemovedElegiblePasses`

<!-- END:GENERATED entity=ProductBookingCredits -->
