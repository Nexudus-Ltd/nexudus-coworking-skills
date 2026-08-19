# CoworkerBookingCredits

<!-- BEGIN:GENERATED entity=CoworkerBookingCredits -->

A booking credit (internally CoworkerBookingCredit) is a monetary balance assigned to a customer that can pay for bookings, event sign-ups, or, when universal credit is enabled, products, plans, passes, and selected one-off charges. It can be created manually or released from a plan or product benefit, and its availability can be limited by eligibility and a validity period.

CoworkerBookingCredits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerbookingcredits list --agent` | List all coworkerbookingcredits |
| `nexudus coworkerbookingcredits list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerbookingcredits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerbookingcredits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerbookingcredits list --business-name <value> --tariff-booking-credit-name <value> --agent` | Filter coworkerbookingcredits by properties |
| `nexudus coworkerbookingcredits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerbookingcredits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerbookingcredits get <id> --agent` | Get single coworkerbookingcredit |
| `nexudus coworkerbookingcredits create --coworker-id <value> --business-id <value> --total-credit <value> --agent` | Create coworkerbookingcredit |
| `nexudus coworkerbookingcredits update <id> --name "New Name" --agent` | Update coworkerbookingcredit |
| `nexudus coworkerbookingcredits delete <id> --yes --agent` | Delete coworkerbookingcredit (no prompt) |

#### CoworkerBookingCredit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer this booking credit belongs to |
| `--coworker-full-name` | string | Full name of the customer this booking credit belongs to |
| `--business-id` | long | ID of the location that issued and owns this booking credit |
| `--business-name` | string | Location name |
| `--business-currency-code` | string | Currency code of the location |
| `--description` | string | Optional operator-facing label or description for this booking credit |
| `--tariff-booking-credit-id` | long | Read-only ID of the plan booking-credit definition that created this credit, if applicable |
| `--tariff-booking-credit-name` | string | Name of the plan credit template that originated this credit |
| `--remaining-credit` | decimal | Read-only monetary amount still available; the system initializes it from TotalCredit and changes it through credit use or an adjustment |
| `--from-remaining-credit` | range | |
| `--to-remaining-credit` | range | |
| `--total-credit` | decimal | Total monetary amount assigned when this credit is created; it sets the initial RemainingCredit |
| `--from-total-credit` | range | |
| `--to-total-credit` | range | |
| `--valid-from` | DateTime | Optional UTC date and time when this credit becomes usable; blank means it is usable immediately |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--expire-date` | DateTime | Optional UTC date and time when this credit stops being usable; blank means no expiry, and when set it must be later than ValidFrom |
| `--from-expire-date` | range | |
| `--to-expire-date` | range | |
| `--cane-be-used-for-bookings` | bool | Whether this credit can pay for bookings; use ElegibleResourceTypes to limit eligible resource types |
| `--cane-be-used-for-events` | bool | Whether this credit can pay for event sign-ups; use EventCategories to limit eligible event categories |
| `--is-universal-credit` | bool | Whether this credit can pay for products, plans, passes, and eligible charges; use the eligibility lists and AppliesToCharges to restrict those uses |
| `--coworker-product-unique-id` | string | Internal unique ID linking this credit to the product purchase that created it |
| `--use-credit-price` | bool | System-calculated flag indicating whether any eligible resource type has a booking rate with a credit price |
| `--coworker-contract-unique-id` | string | Internal unique ID linking this credit to the contract that originated it |
| `--applies-to-charges` | bool | Whether this universal credit can pay for one-off charges in addition to products, plans, and passes |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerBookingCredit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerBookingCredit create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer this booking credit belongs to |
| `--business-id` | long, required | ID of the location that issued and owns this booking credit |
| `--description` | string | Optional operator-facing label or description for this booking credit |
| `--elegible-resource-types` | list, repeat flag | List of resource-type IDs this credit can pay for when CaneBeUsedForBookings is true; an empty list allows every resource type |
| `--added-elegible-resource-types` | list, repeat flag | Resource type IDs to add to ElegibleResourceTypes |
| `--removed-elegible-resource-types` | list, repeat flag | Resource type IDs to remove from ElegibleResourceTypes |
| `--elegible-products` | list, repeat flag | List of product IDs this universal credit can pay for; when IsUniversalCredit is true, an empty list allows every product |
| `--added-elegible-products` | list, repeat flag | Product IDs to add to ElegibleProducts |
| `--removed-elegible-products` | list, repeat flag | Product IDs to remove from ElegibleProducts |
| `--elegible-tariffs` | list, repeat flag | List of plan IDs this universal credit can pay for; when IsUniversalCredit is true, an empty list allows every plan |
| `--added-elegible-tariffs` | list, repeat flag | Plan IDs to add to ElegibleTariffs |
| `--removed-elegible-tariffs` | list, repeat flag | Plan IDs to remove from ElegibleTariffs |
| `--total-credit` | decimal, required | Total monetary amount assigned when this credit is created; it sets the initial RemainingCredit |
| `--valid-from` | DateTime | Optional UTC date and time when this credit becomes usable; blank means it is usable immediately |
| `--expire-date` | DateTime | Optional UTC date and time when this credit stops being usable; blank means no expiry, and when set it must be later than ValidFrom |
| `--cane-be-used-for-bookings` | bool | Whether this credit can pay for bookings; use ElegibleResourceTypes to limit eligible resource types |
| `--cane-be-used-for-events` | bool | Whether this credit can pay for event sign-ups; use EventCategories to limit eligible event categories |
| `--event-categories` | list, repeat flag | List of event-category IDs this credit can pay for when CaneBeUsedForEvents is true; an empty list allows every event category |
| `--added-event-categories` | list, repeat flag | Event category IDs to add to EventCategories |
| `--removed-event-categories` | list, repeat flag | Event category IDs to remove from EventCategories |
| `--is-universal-credit` | bool | Whether this credit can pay for products, plans, passes, and eligible charges; use the eligibility lists and AppliesToCharges to restrict those uses |
| `--coworker-contract-unique-id` | string | Internal unique ID linking this credit to the contract that originated it |
| `--elegible-passes` | list, repeat flag | List of pass IDs this universal credit can pay for; when IsUniversalCredit is true, an empty list allows every pass |
| `--added-elegible-passes` | list, repeat flag | Pass IDs to add to ElegiblePasses |
| `--removed-elegible-passes` | list, repeat flag | Pass IDs to remove from ElegiblePasses |
| `--applies-to-charges` | bool | Whether this universal credit can pay for one-off charges in addition to products, plans, and passes |

#### CoworkerBookingCredit update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer this booking credit belongs to |
| `--business-id` | long | ID of the location that issued and owns this booking credit |
| `--description` | string | Optional operator-facing label or description for this booking credit |
| `--elegible-resource-types` | list, repeat flag | List of resource-type IDs this credit can pay for when CaneBeUsedForBookings is true; an empty list allows every resource type |
| `--added-elegible-resource-types` | list, repeat flag | Resource type IDs to add to ElegibleResourceTypes |
| `--removed-elegible-resource-types` | list, repeat flag | Resource type IDs to remove from ElegibleResourceTypes |
| `--elegible-products` | list, repeat flag | List of product IDs this universal credit can pay for; when IsUniversalCredit is true, an empty list allows every product |
| `--added-elegible-products` | list, repeat flag | Product IDs to add to ElegibleProducts |
| `--removed-elegible-products` | list, repeat flag | Product IDs to remove from ElegibleProducts |
| `--elegible-tariffs` | list, repeat flag | List of plan IDs this universal credit can pay for; when IsUniversalCredit is true, an empty list allows every plan |
| `--added-elegible-tariffs` | list, repeat flag | Plan IDs to add to ElegibleTariffs |
| `--removed-elegible-tariffs` | list, repeat flag | Plan IDs to remove from ElegibleTariffs |
| `--total-credit` | decimal | Total monetary amount assigned when this credit is created; it sets the initial RemainingCredit |
| `--valid-from` | DateTime | Optional UTC date and time when this credit becomes usable; blank means it is usable immediately |
| `--expire-date` | DateTime | Optional UTC date and time when this credit stops being usable; blank means no expiry, and when set it must be later than ValidFrom |
| `--cane-be-used-for-bookings` | bool | Whether this credit can pay for bookings; use ElegibleResourceTypes to limit eligible resource types |
| `--cane-be-used-for-events` | bool | Whether this credit can pay for event sign-ups; use EventCategories to limit eligible event categories |
| `--event-categories` | list, repeat flag | List of event-category IDs this credit can pay for when CaneBeUsedForEvents is true; an empty list allows every event category |
| `--added-event-categories` | list, repeat flag | Event category IDs to add to EventCategories |
| `--removed-event-categories` | list, repeat flag | Event category IDs to remove from EventCategories |
| `--is-universal-credit` | bool | Whether this credit can pay for products, plans, passes, and eligible charges; use the eligibility lists and AppliesToCharges to restrict those uses |
| `--coworker-contract-unique-id` | string | Internal unique ID linking this credit to the contract that originated it |
| `--elegible-passes` | list, repeat flag | List of pass IDs this universal credit can pay for; when IsUniversalCredit is true, an empty list allows every pass |
| `--added-elegible-passes` | list, repeat flag | Pass IDs to add to ElegiblePasses |
| `--removed-elegible-passes` | list, repeat flag | Pass IDs to remove from ElegiblePasses |
| `--applies-to-charges` | bool | Whether this universal credit can pay for one-off charges in addition to products, plans, and passes |

#### CoworkerBookingCredit PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coworkerbookingcredits update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerBookingCredit (key fields)

`Id`, `BusinessName`, `TariffBookingCreditName`

**List properties (only returned by `get`, not by `list`):** `ElegibleResourceTypes`, `AddedElegibleResourceTypes`, `RemovedElegibleResourceTypes`, `ElegibleProducts`, `AddedElegibleProducts`, `RemovedElegibleProducts`, `ElegibleTariffs`, `AddedElegibleTariffs`, `RemovedElegibleTariffs`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `ElegiblePasses`, `AddedElegiblePasses`, `RemovedElegiblePasses`

<!-- END:GENERATED entity=CoworkerBookingCredits -->
