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
| `nexudus discountcodes get <id> --agent` | Get single discountcode |
| `nexudus discountcodes create --business-id <value> --code <value> --description <value> --agent` | Create discountcode |
| `nexudus discountcodes update <id> --name "New Name" --agent` | Update discountcode |
| `nexudus discountcodes delete <id> --yes --agent` | Delete discountcode (no prompt) |

#### DiscountCode list filter options

`--business-id` (long), `--code`, `--description`, `--active` (bool), `--publish-from` (DateTime), `--from-publish-from` (range), `--to-publish-from` (range), `--publish-to` (DateTime), `--from-publish-to` (range), `--to-publish-to` (range), `--discount-percentage` (decimal), `--from-discount-percentage` (range), `--to-discount-percentage` (range), `--discount-amount` (decimal), `--from-discount-amount` (range), `--to-discount-amount` (range), `--referral-discount` (bool), `--discount-price-plans` (bool), `--discount-bookings` (bool), `--discount-products` (bool), `--discount-events` (bool), `--max-uses-per-user` (int), `--from-max-uses-per-user` (range), `--to-max-uses-per-user` (range), `--max-uses` (int), `--from-max-uses` (range), `--to-max-uses` (range), `--only-for-contacts` (bool), `--only-for-members` (bool), `--valid-from` (DateTime), `--from-valid-from` (range), `--to-valid-from` (range), `--valid-to` (DateTime), `--from-valid-to` (range), `--to-valid-to` (range), `--expiration-type` (enum), `--expires-in` (int), `--from-expires-in` (range), `--to-expires-in` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### DiscountCode create options

`--business-id` (long, required), `--code` (required), `--description` (required), `--active` (bool), `--publish-from` (DateTime), `--publish-to` (DateTime), `--discount-percentage` (decimal), `--discount-amount` (decimal), `--referral-discount` (bool), `--discount-price-plans` (bool), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--discount-bookings` (bool), `--resource-types` (list, repeat flag), `--added-resource-types` (list, repeat flag), `--removed-resource-types` (list, repeat flag), `--discount-products` (bool), `--products` (list, repeat flag), `--added-products` (list, repeat flag), `--removed-products` (list, repeat flag), `--discount-events` (bool), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--max-uses-per-user` (int), `--max-uses` (int), `--only-for-contacts` (bool), `--only-for-members` (bool), `--valid-from` (DateTime), `--valid-to` (DateTime), `--expiration-type` (enum), `--expires-in` (int)

#### DiscountCode update options

`--business-id` (long), `--code`, `--description`, `--active` (bool), `--publish-from` (DateTime), `--publish-to` (DateTime), `--discount-percentage` (decimal), `--discount-amount` (decimal), `--referral-discount` (bool), `--discount-price-plans` (bool), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--discount-bookings` (bool), `--resource-types` (list, repeat flag), `--added-resource-types` (list, repeat flag), `--removed-resource-types` (list, repeat flag), `--discount-products` (bool), `--products` (list, repeat flag), `--added-products` (list, repeat flag), `--removed-products` (list, repeat flag), `--discount-events` (bool), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--max-uses-per-user` (int), `--max-uses` (int), `--only-for-contacts` (bool), `--only-for-members` (bool), `--valid-from` (DateTime), `--valid-to` (DateTime), `--expiration-type` (enum), `--expires-in` (int)

### DiscountCode (key fields)

`Id`, `Code`, `Description`, `Active`, `DiscountPercentage`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `ResourceTypes`, `AddedResourceTypes`, `RemovedResourceTypes`, `Products`, `AddedProducts`, `RemovedProducts`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`

<!-- END:GENERATED entity=DiscountCodes -->
