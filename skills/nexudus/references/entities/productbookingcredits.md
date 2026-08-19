# ProductBookingCredits

<!-- BEGIN:GENERATED entity=ProductBookingCredits -->

A ProductBookingCredit represents an amount of credit linked to a Product. When a customer purchases the product, the credit is automatically released as a CoworkerBookingCredit on the customer's account.

**When is the credit released?**
- **Admin sale (via CoworkerProduct):** An admin can choose to release the credit before payment by setting ActivateNow = true when selling the product.
- **Member purchase (online, active contract):** Credits are released immediately unless the Store.AlwaysInvoice business setting is enabled, in which case credits release after payment.
- **Contact purchase (online, no active contract):** Credits are released after the product is paid.

Credit can be configured for bookings (with CaneBeUsedForBookings and ElegibleResourceTypes), events (with CaneBeUsedForEvents and EventCategories), or as a universal credit (with IsUniversalCredit) applicable to products, time passes, and other charges. Use ExpirationType and ExpiresIn to control when the released credit expires.

ProductBookingCredits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus productbookingcredits list --agent` | List all productbookingcredits |
| `nexudus productbookingcredits list --id <id> --agent` | Filter by single ID |
| `nexudus productbookingcredits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus productbookingcredits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus productbookingcredits list --name <value> --product-name <value> --agent` | Filter productbookingcredits by properties |
| `nexudus productbookingcredits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus productbookingcredits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus productbookingcredits get <id> --agent` | Get single productbookingcredit |
| `nexudus productbookingcredits create --name <value> --product-id <value> --credit <value> --agent` | Create productbookingcredit |
| `nexudus productbookingcredits update <id> --name "New Name" --agent` | Update productbookingcredit |
| `nexudus productbookingcredits delete <id> --yes --agent` | Delete productbookingcredit (no prompt) |

#### ProductBookingCredit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Credit name |
| `--product-id` | long | ID of the product linked to this record |
| `--product-name` | string | Product name |
| `--product-business-currency-code` | string | Product business currency code |
| `--credit` | decimal | Credit amount that will be released to the customer's account as a CoworkerBookingCredit. Release timing depends on purchase method: admin sales can release before payment (ActivateNow), member purchases release immediately (unless Store.AlwaysInvoice is set), and contact purchases release after payment |
| `--from-credit` | range | |
| `--to-credit` | range | |
| `--can-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types with ElegibleResourceTypes |
| `--can-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with EventCategories |
| `--expiration-type` | enum | Expiration type: PricePlan (expires at end of billing period of the main contract - customer must have a main contract), Day, Week, Month, Year, or LastDayOfMonth |
| `--expires-in` | int | Number of periods (of ExpirationType) until the released credit expires |
| `--from-expires-in` | range | |
| `--to-expires-in` | range | |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with ElegibleProducts, ElegiblePasses and AppliesToCharges; if all are empty the credit applies to all products, passes and charges |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges beyond products and passes |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProductBookingCredit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ProductBookingCredit create options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string, required | Credit name |
| `--product-id` | long, required | ID of the product linked to this record |
| `--elegible-resource-types` | list, repeat flag | List of eligible resource types this credit can be used for. If empty, the credit is valid for all resource types |
| `--added-elegible-resource-types` | list, repeat flag | The added elegible resource types value for this product booking credit |
| `--removed-elegible-resource-types` | list, repeat flag | The removed elegible resource types value for this product booking credit |
| `--elegible-products` | list, repeat flag | List of eligible products this universal credit can be used to purchase. If empty and IsUniversalCredit is true, the credit applies to all products |
| `--added-elegible-products` | list, repeat flag | The added elegible products value for this product booking credit |
| `--removed-elegible-products` | list, repeat flag | The removed elegible products value for this product booking credit |
| `--elegible-tariffs` | list, repeat flag | List of eligible tariffs (plans) this credit is valid for |
| `--added-elegible-tariffs` | list, repeat flag | The added elegible tariffs value for this product booking credit |
| `--removed-elegible-tariffs` | list, repeat flag | The removed elegible tariffs value for this product booking credit |
| `--credit` | decimal, required | Credit amount that will be released to the customer's account as a CoworkerBookingCredit. Release timing depends on purchase method: admin sales can release before payment (ActivateNow), member purchases release immediately (unless Store.AlwaysInvoice is set), and contact purchases release after payment |
| `--can-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types with ElegibleResourceTypes |
| `--can-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with EventCategories |
| `--event-categories` | list, repeat flag | List of event categories this credit is valid for. If empty and CaneBeUsedForEvents is true, the credit is valid for all events |
| `--added-event-categories` | list, repeat flag | The added event categories value for this product booking credit |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this product booking credit |
| `--expiration-type` | enum | Expiration type: PricePlan (expires at end of billing period of the main contract - customer must have a main contract), Day, Week, Month, Year, or LastDayOfMonth |
| `--expires-in` | int | Number of periods (of ExpirationType) until the released credit expires |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with ElegibleProducts, ElegiblePasses and AppliesToCharges; if all are empty the credit applies to all products, passes and charges |
| `--elegible-passes` | list, repeat flag | List of eligible time passes this universal credit can be used to purchase. If empty and IsUniversalCredit is true, the credit applies to all passes |
| `--added-elegible-passes` | list, repeat flag | The added elegible passes value for this product booking credit |
| `--removed-elegible-passes` | list, repeat flag | The removed elegible passes value for this product booking credit |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges beyond products and passes |

#### ProductBookingCredit update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Credit name |
| `--product-id` | long | ID of the product linked to this record |
| `--elegible-resource-types` | list, repeat flag | List of eligible resource types this credit can be used for. If empty, the credit is valid for all resource types |
| `--added-elegible-resource-types` | list, repeat flag | The added elegible resource types value for this product booking credit |
| `--removed-elegible-resource-types` | list, repeat flag | The removed elegible resource types value for this product booking credit |
| `--elegible-products` | list, repeat flag | List of eligible products this universal credit can be used to purchase. If empty and IsUniversalCredit is true, the credit applies to all products |
| `--added-elegible-products` | list, repeat flag | The added elegible products value for this product booking credit |
| `--removed-elegible-products` | list, repeat flag | The removed elegible products value for this product booking credit |
| `--elegible-tariffs` | list, repeat flag | List of eligible tariffs (plans) this credit is valid for |
| `--added-elegible-tariffs` | list, repeat flag | The added elegible tariffs value for this product booking credit |
| `--removed-elegible-tariffs` | list, repeat flag | The removed elegible tariffs value for this product booking credit |
| `--credit` | decimal | Credit amount that will be released to the customer's account as a CoworkerBookingCredit. Release timing depends on purchase method: admin sales can release before payment (ActivateNow), member purchases release immediately (unless Store.AlwaysInvoice is set), and contact purchases release after payment |
| `--can-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types with ElegibleResourceTypes |
| `--can-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with EventCategories |
| `--event-categories` | list, repeat flag | List of event categories this credit is valid for. If empty and CaneBeUsedForEvents is true, the credit is valid for all events |
| `--added-event-categories` | list, repeat flag | The added event categories value for this product booking credit |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this product booking credit |
| `--expiration-type` | enum | Expiration type: PricePlan (expires at end of billing period of the main contract - customer must have a main contract), Day, Week, Month, Year, or LastDayOfMonth |
| `--expires-in` | int | Number of periods (of ExpirationType) until the released credit expires |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with ElegibleProducts, ElegiblePasses and AppliesToCharges; if all are empty the credit applies to all products, passes and charges |
| `--elegible-passes` | list, repeat flag | List of eligible time passes this universal credit can be used to purchase. If empty and IsUniversalCredit is true, the credit applies to all passes |
| `--added-elegible-passes` | list, repeat flag | The added elegible passes value for this product booking credit |
| `--removed-elegible-passes` | list, repeat flag | The removed elegible passes value for this product booking credit |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges beyond products and passes |

### ProductBookingCredit (key fields)

`Id`, `Name`, `ProductName`, `Credit`, `IsUniversalCredit`

**List properties (only returned by `get`, not by `list`):** `ElegibleResourceTypes`, `AddedElegibleResourceTypes`, `RemovedElegibleResourceTypes`, `ElegibleProducts`, `AddedElegibleProducts`, `RemovedElegibleProducts`, `ElegibleTariffs`, `AddedElegibleTariffs`, `RemovedElegibleTariffs`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `ElegiblePasses`, `AddedElegiblePasses`, `RemovedElegiblePasses`

<!-- END:GENERATED entity=ProductBookingCredits -->
