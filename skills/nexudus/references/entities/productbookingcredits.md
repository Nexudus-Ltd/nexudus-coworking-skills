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

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Credit name |
| `--product-id` | long | ID of the product linked to this record |
| `--credit` | decimal | Credit amount |
| `--from-credit` | range | |
| `--to-credit` | range | |
| `--expire-time-in-months` | int | The expire time in months value for this product booking credit |
| `--from-expire-time-in-months` | range | |
| `--to-expire-time-in-months` | range | |
| `--expire-time-in-weeks` | int | The expire time in weeks value for this product booking credit |
| `--from-expire-time-in-weeks` | range | |
| `--to-expire-time-in-weeks` | range | |
| `--can-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types with --elegible-resource-types |
| `--can-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with --event-categories |
| `--expiration-type` | enum | Expiration type |
| `--expires-in` | int | Number of periods (of --expiration-type) until the released credit expires |
| `--from-expires-in` | range | |
| `--to-expires-in` | range | |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with --elegible-products, --elegible-passes and --applies-to-charges; if all are empty the credit applies to all products, passes and charges |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProductBookingCredit create options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string, required | Credit name |
| `--product-id` | long, required | ID of the product linked to this record |
| `--elegible-resource-types` | list, repeat flag | List of elegible resource types linked to this record |
| `--added-elegible-resource-types` | list, repeat flag | The added elegible resource types value for this product booking credit |
| `--removed-elegible-resource-types` | list, repeat flag | The removed elegible resource types value for this product booking credit |
| `--elegible-products` | list, repeat flag | List of elegible products linked to this record |
| `--added-elegible-products` | list, repeat flag | The added elegible products value for this product booking credit |
| `--removed-elegible-products` | list, repeat flag | The removed elegible products value for this product booking credit |
| `--elegible-tariffs` | list, repeat flag | List of elegible tariffs linked to this record |
| `--added-elegible-tariffs` | list, repeat flag | The added elegible tariffs value for this product booking credit |
| `--removed-elegible-tariffs` | list, repeat flag | The removed elegible tariffs value for this product booking credit |
| `--credit` | decimal, required | Credit amount |
| `--expire-time-in-months` | int | The expire time in months value for this product booking credit |
| `--expire-time-in-weeks` | int | The expire time in weeks value for this product booking credit |
| `--can-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types with --elegible-resource-types |
| `--can-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with --event-categories |
| `--event-categories` | list, repeat flag | List of event categories linked to this record |
| `--added-event-categories` | list, repeat flag | The added event categories value for this product booking credit |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this product booking credit |
| `--expiration-type` | enum | Expiration type |
| `--expires-in` | int | Number of periods (of --expiration-type) until the released credit expires |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with --elegible-products, --elegible-passes and --applies-to-charges; if all are empty the credit applies to all products, passes and charges |
| `--elegible-passes` | list, repeat flag | List of elegible passes linked to this record |
| `--added-elegible-passes` | list, repeat flag | The added elegible passes value for this product booking credit |
| `--removed-elegible-passes` | list, repeat flag | The removed elegible passes value for this product booking credit |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges |

#### ProductBookingCredit update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Credit name |
| `--product-id` | long | ID of the product linked to this record |
| `--elegible-resource-types` | list, repeat flag | List of elegible resource types linked to this record |
| `--added-elegible-resource-types` | list, repeat flag | The added elegible resource types value for this product booking credit |
| `--removed-elegible-resource-types` | list, repeat flag | The removed elegible resource types value for this product booking credit |
| `--elegible-products` | list, repeat flag | List of elegible products linked to this record |
| `--added-elegible-products` | list, repeat flag | The added elegible products value for this product booking credit |
| `--removed-elegible-products` | list, repeat flag | The removed elegible products value for this product booking credit |
| `--elegible-tariffs` | list, repeat flag | List of elegible tariffs linked to this record |
| `--added-elegible-tariffs` | list, repeat flag | The added elegible tariffs value for this product booking credit |
| `--removed-elegible-tariffs` | list, repeat flag | The removed elegible tariffs value for this product booking credit |
| `--credit` | decimal | Credit amount |
| `--expire-time-in-months` | int | The expire time in months value for this product booking credit |
| `--expire-time-in-weeks` | int | The expire time in weeks value for this product booking credit |
| `--can-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types with --elegible-resource-types |
| `--can-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with --event-categories |
| `--event-categories` | list, repeat flag | List of event categories linked to this record |
| `--added-event-categories` | list, repeat flag | The added event categories value for this product booking credit |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this product booking credit |
| `--expiration-type` | enum | Expiration type |
| `--expires-in` | int | Number of periods (of --expiration-type) until the released credit expires |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with --elegible-products, --elegible-passes and --applies-to-charges; if all are empty the credit applies to all products, passes and charges |
| `--elegible-passes` | list, repeat flag | List of elegible passes linked to this record |
| `--added-elegible-passes` | list, repeat flag | The added elegible passes value for this product booking credit |
| `--removed-elegible-passes` | list, repeat flag | The removed elegible passes value for this product booking credit |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges |

### ProductBookingCredit (key fields)

`Id`, `Name`, `ProductName`, `Credit`, `IsUniversalCredit`

**List properties (only returned by `get`, not by `list`):** `ElegibleResourceTypes`, `AddedElegibleResourceTypes`, `RemovedElegibleResourceTypes`, `ElegibleProducts`, `AddedElegibleProducts`, `RemovedElegibleProducts`, `ElegibleTariffs`, `AddedElegibleTariffs`, `RemovedElegibleTariffs`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `ElegiblePasses`, `AddedElegiblePasses`, `RemovedElegiblePasses`

<!-- END:GENERATED entity=ProductBookingCredits -->
