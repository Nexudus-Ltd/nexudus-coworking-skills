# DiscountCodes

<!-- BEGIN:GENERATED entity=DiscountCodes -->

A **DiscountCode** represents a discount registered in the system. Each discount code belongs to a `Business` (location) and defines a percentage or fixed-amount discount that can be applied to different item types: price plans (tariffs), bookings, products, and/or events.

Use the boolean flags (`DiscountPricePlans`, `DiscountBookings`, `DiscountProducts`, `DiscountEvents`) to control which item categories the discount applies to. For each enabled category, associate the specific eligible items via the corresponding ID list (e.g. `Tariffs`, `ResourceTypes`, `Products`, `EventCategories`). Use the `Added*` and `Removed*` list variants for incremental updates without replacing the full list.

A discount can specify either `DiscountPercentage` (e.g. 10 for 10% off) or `DiscountAmount` (a fixed monetary amount off), but not both.

Discount codes can be assigned to individual customers via `CoworkerDiscountCode`. Availability can be further restricted by validity dates (`ValidFrom`/`ValidTo`), publish window (`PublishFrom`/`PublishTo`), usage caps (`MaxUses`, `MaxUsesPerUser`), audience (`OnlyForContacts`, `OnlyForMembers`), and expiration rules (`ExpirationType`, `ExpiresIn`).

DiscountCodes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus discountcodes list --agent` | List all discountcodes |
| `nexudus discountcodes list --id <id> --agent` | Filter by single ID |
| `nexudus discountcodes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus discountcodes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus discountcodes list --code <value> --description <value> --agent` | Filter discountcodes by properties |
| `nexudus discountcodes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus discountcodes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus discountcodes get <id> --agent` | Get single discountcode |
| `nexudus discountcodes create --business-id <value> --code <value> --description <value> --agent` | Create discountcode |
| `nexudus discountcodes update <id> --name "New Name" --agent` | Update discountcode |
| `nexudus discountcodes delete <id> --yes --agent` | Delete discountcode (no prompt) |

#### DiscountCode list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--business-name` | string | Name of the business (location) this discount code belongs to |
| `--business-currency-code` | string | Currency code of the business (e.g. USD, EUR) |
| `--code` | string | The unique alphanumeric code customers enter to apply the discount |
| `--description` | string | Human-readable description of what this discount code is for |
| `--active` | bool | Whether this discount code is currently active and can be redeemed |
| `--publish-from` | DateTime | Date from which this discount code is visible/published to customers |
| `--from-publish-from` | range | |
| `--to-publish-from` | range | |
| `--publish-to` | DateTime | Date until which this discount code is visible/published to customers |
| `--from-publish-to` | range | |
| `--to-publish-to` | range | |
| `--discount-percentage` | decimal | Percentage discount to apply (e.g. 10 for 10% off). Mutually exclusive with DiscountAmount |
| `--from-discount-percentage` | range | |
| `--to-discount-percentage` | range | |
| `--discount-amount` | decimal | Fixed monetary amount to discount. Mutually exclusive with DiscountPercentage |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--referral-discount` | bool | Whether this discount code is used as part of the referral program |
| `--discount-price-plans` | bool | Whether this discount can be applied to price plans (tariffs). When true, use Tariffs to restrict to specific plans |
| `--discount-bookings` | bool | Whether this discount can be applied to resource bookings. When true, use ResourceTypes to restrict to specific resource types |
| `--discount-products` | bool | Whether this discount can be applied to products. When true, use Products to restrict to specific products |
| `--discount-events` | bool | Whether this discount can be applied to events. When true, use EventCategories to restrict to specific event categories |
| `--max-uses-per-user` | int | Maximum number of times a single customer can redeem this discount code |
| `--from-max-uses-per-user` | range | |
| `--to-max-uses-per-user` | range | |
| `--max-uses` | int | Maximum total number of times this discount code can be redeemed across all customers |
| `--from-max-uses` | range | |
| `--to-max-uses` | range | |
| `--only-for-contacts` | bool | When true, only contacts (non-member customers) can use this discount code |
| `--only-for-members` | bool | When true, only members (customers with an active plan) can use this discount code |
| `--valid-from` | DateTime | Start date from which this discount code can be redeemed |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--valid-to` | DateTime | End date after which this discount code can no longer be redeemed |
| `--from-valid-to` | range | |
| `--to-valid-to` | range | |
| `--expiration-type` | enum | Unit of the expiration period (Day, Week, Month, Year). Used with ExpiresIn to determine when the discount expires after being assigned to a customer |
| `--expires-in` | int | Number of ExpirationType periods after assignment until the discount expires for a customer |
| `--from-expires-in` | range | |
| `--to-expires-in` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### DiscountCode sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Code` ascending. If no `--order-by` is specified, the API returns results ordered by `Code` (ascending).

#### DiscountCode create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--code` | string, required | The unique alphanumeric code customers enter to apply the discount |
| `--description` | string, required | Human-readable description of what this discount code is for |
| `--active` | bool | Whether this discount code is currently active and can be redeemed |
| `--publish-from` | DateTime | Date from which this discount code is visible/published to customers |
| `--publish-to` | DateTime | Date until which this discount code is visible/published to customers |
| `--discount-percentage` | decimal | Percentage discount to apply (e.g. 10 for 10% off). Mutually exclusive with DiscountAmount |
| `--discount-amount` | decimal | Fixed monetary amount to discount. Mutually exclusive with DiscountPercentage |
| `--referral-discount` | bool | Whether this discount code is used as part of the referral program |
| `--discount-price-plans` | bool | Whether this discount can be applied to price plans (tariffs). When true, use Tariffs to restrict to specific plans |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this discount code |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this discount code |
| `--discount-bookings` | bool | Whether this discount can be applied to resource bookings. When true, use ResourceTypes to restrict to specific resource types |
| `--resource-types` | list, repeat flag | List of resource types linked to this record |
| `--added-resource-types` | list, repeat flag | The added resource types value for this discount code |
| `--removed-resource-types` | list, repeat flag | The removed resource types value for this discount code |
| `--discount-products` | bool | Whether this discount can be applied to products. When true, use Products to restrict to specific products |
| `--products` | list, repeat flag | List of products linked to this record |
| `--added-products` | list, repeat flag | The added products value for this discount code |
| `--removed-products` | list, repeat flag | The removed products value for this discount code |
| `--discount-events` | bool | Whether this discount can be applied to events. When true, use EventCategories to restrict to specific event categories |
| `--event-categories` | list, repeat flag | List of event categories linked to this record |
| `--added-event-categories` | list, repeat flag | The added event categories value for this discount code |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this discount code |
| `--max-uses-per-user` | int | Maximum number of times a single customer can redeem this discount code |
| `--max-uses` | int | Maximum total number of times this discount code can be redeemed across all customers |
| `--only-for-contacts` | bool | When true, only contacts (non-member customers) can use this discount code |
| `--only-for-members` | bool | When true, only members (customers with an active plan) can use this discount code |
| `--valid-from` | DateTime | Start date from which this discount code can be redeemed |
| `--valid-to` | DateTime | End date after which this discount code can no longer be redeemed |
| `--expiration-type` | enum | Unit of the expiration period (Day, Week, Month, Year). Used with ExpiresIn to determine when the discount expires after being assigned to a customer |
| `--expires-in` | int | Number of ExpirationType periods after assignment until the discount expires for a customer |

#### DiscountCode update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--code` | string | The unique alphanumeric code customers enter to apply the discount |
| `--description` | string | Human-readable description of what this discount code is for |
| `--active` | bool | Whether this discount code is currently active and can be redeemed |
| `--publish-from` | DateTime | Date from which this discount code is visible/published to customers |
| `--publish-to` | DateTime | Date until which this discount code is visible/published to customers |
| `--discount-percentage` | decimal | Percentage discount to apply (e.g. 10 for 10% off). Mutually exclusive with DiscountAmount |
| `--discount-amount` | decimal | Fixed monetary amount to discount. Mutually exclusive with DiscountPercentage |
| `--referral-discount` | bool | Whether this discount code is used as part of the referral program |
| `--discount-price-plans` | bool | Whether this discount can be applied to price plans (tariffs). When true, use Tariffs to restrict to specific plans |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this discount code |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this discount code |
| `--discount-bookings` | bool | Whether this discount can be applied to resource bookings. When true, use ResourceTypes to restrict to specific resource types |
| `--resource-types` | list, repeat flag | List of resource types linked to this record |
| `--added-resource-types` | list, repeat flag | The added resource types value for this discount code |
| `--removed-resource-types` | list, repeat flag | The removed resource types value for this discount code |
| `--discount-products` | bool | Whether this discount can be applied to products. When true, use Products to restrict to specific products |
| `--products` | list, repeat flag | List of products linked to this record |
| `--added-products` | list, repeat flag | The added products value for this discount code |
| `--removed-products` | list, repeat flag | The removed products value for this discount code |
| `--discount-events` | bool | Whether this discount can be applied to events. When true, use EventCategories to restrict to specific event categories |
| `--event-categories` | list, repeat flag | List of event categories linked to this record |
| `--added-event-categories` | list, repeat flag | The added event categories value for this discount code |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this discount code |
| `--max-uses-per-user` | int | Maximum number of times a single customer can redeem this discount code |
| `--max-uses` | int | Maximum total number of times this discount code can be redeemed across all customers |
| `--only-for-contacts` | bool | When true, only contacts (non-member customers) can use this discount code |
| `--only-for-members` | bool | When true, only members (customers with an active plan) can use this discount code |
| `--valid-from` | DateTime | Start date from which this discount code can be redeemed |
| `--valid-to` | DateTime | End date after which this discount code can no longer be redeemed |
| `--expiration-type` | enum | Unit of the expiration period (Day, Week, Month, Year). Used with ExpiresIn to determine when the discount expires after being assigned to a customer |
| `--expires-in` | int | Number of ExpirationType periods after assignment until the discount expires for a customer |

### DiscountCode (key fields)

`Id`, `Code`, `Description`, `Active`, `DiscountPercentage`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `ResourceTypes`, `AddedResourceTypes`, `RemovedResourceTypes`, `Products`, `AddedProducts`, `RemovedProducts`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`

<!-- END:GENERATED entity=DiscountCodes -->
