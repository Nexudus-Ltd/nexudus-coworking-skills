# DiscountCodes

<!-- BEGIN:GENERATED entity=DiscountCodes -->

A DiscountCode is a code operators share with customers to take a percentage or a fixed amount off a price. Each code belongs to a location, and a code owned by a network parent location can also be redeemed at every location in that network. Set either DiscountPercentage or DiscountAmount, not both; if both are set the fixed amount is used and it is capped at the item price. The DiscountPricePlans, DiscountBookings, DiscountProducts and DiscountEvents flags choose which kinds of purchase the code pays for, and the matching Tariffs, ResourceTypes, Products and EventCategories lists narrow each one to specific items, where an empty list means every item of that kind is allowed. On update each list replaces the whole collection, so send the complete intended set of IDs. Availability is further limited by Active, the validity window (ValidFrom/ValidTo), the portal publish window (PublishFrom/PublishTo), usage caps (MaxUses, MaxUsesPerUser) and audience (OnlyForContacts, OnlyForMembers). ExpirationType and ExpiresIn set how long a customer keeps the discount once they claim it. Claiming a code creates a CoworkerDiscountCode linking it to that customer; set ReferralDiscount when the discount should reward the referring customer instead of the person redeeming it.

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
| `--business-id` | long | ID of the location this discount code is available at. If the location is a network parent, the code can also be redeemed at every location in that network |
| `--business-name` | string | Display value for Business.Name. |
| `--business-currency-code` | string | Display value for Business.Currency.Code. |
| `--code` | string | The code customers type to claim the discount; must be unique within the location. Typically a short alphanumeric string such as SUMMER25 |
| `--description` | string | Short text shown to the customer when they enter a valid code, for example 20% off your first month. Required, and translatable per language |
| `--active` | bool | Whether the code can be redeemed at all. When false the code is ignored everywhere, regardless of its validity or publish dates |
| `--publish-from` | DateTime | UTC date and time from which the code can be redeemed on the members portal, website and app. Leave empty to publish immediately |
| `--from-publish-from` | range | |
| `--to-publish-from` | range | |
| `--publish-to` | DateTime | UTC date and time after which the code can no longer be redeemed on the members portal, website and app. Leave empty for no publish end date |
| `--from-publish-to` | range | |
| `--to-publish-to` | range | |
| `--discount-percentage` | decimal | Percentage taken off the price, entered as a whole number so 10 means 10% off. Set either this or DiscountAmount, not both; when both are set DiscountAmount wins |
| `--from-discount-percentage` | range | |
| `--to-discount-percentage` | range | |
| `--discount-amount` | decimal | Fixed amount taken off the price, in the location currency. Capped at the item price so the result is never negative. Set either this or DiscountPercentage, not both; when both are set this one wins |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--referral-discount` | bool | Whether the discount is granted to the referring customer instead of the person redeeming it. When true, sign-up fails unless the new customer arrived through a referral link, and the discount stops applying if the referrer becomes inactive. To reward both sides, add a second non-referral code using the same Code value |
| `--discount-price-plans` | bool | Whether the code can be used to pay for plans. When false the code never applies to a plan, whatever Tariffs contains |
| `--discount-bookings` | bool | Whether the code can be used to pay for bookings. When false the code never applies to a booking, whatever ResourceTypes contains |
| `--discount-products` | bool | Whether the code can be used to pay for products. When false the code never applies to a product, whatever Products contains |
| `--discount-events` | bool | Whether the code can be used to pay for event tickets. When false the code never applies to an event, whatever EventCategories contains |
| `--max-uses-per-user` | int | Maximum number of times one customer may redeem this code. Leave empty for no per-customer limit |
| `--from-max-uses-per-user` | range | |
| `--to-max-uses-per-user` | range | |
| `--max-uses` | int | Maximum number of redemptions across all customers, after which the code stops working. Leave empty for no overall limit |
| `--from-max-uses` | range | |
| `--to-max-uses` | range | |
| `--only-for-contacts` | bool | Whether the code is restricted to contacts, meaning customers with no active contract. Mutually exclusive with OnlyForMembers; leave both false to allow every customer |
| `--only-for-members` | bool | Whether the code is restricted to members, meaning customers with at least one active contract. Mutually exclusive with OnlyForContacts; leave both false to allow every customer |
| `--valid-from` | DateTime | UTC date and time from which the discount applies. Leave empty for no start date. For bookings this is compared against the booking start time rather than the moment of redemption |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--valid-to` | DateTime | UTC date and time after which the discount no longer applies. Leave empty for no end date. For bookings this is compared against the booking end time rather than the moment of redemption |
| `--from-valid-to` | range | |
| `--to-valid-to` | range | |
| `--expiration-type` | enum | Unit used together with ExpiresIn to work out when a claimed code stops working for that customer: Day, Week, Month or Year |
| `--expires-in` | int | How many ExpirationType periods a customer keeps the discount for after claiming it, so 3 with ExpirationType Month expires it three months after the customer claims the code. Leave empty so the discount never expires on its own |
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
| `--business-id` | long, required | ID of the location this discount code is available at. If the location is a network parent, the code can also be redeemed at every location in that network |
| `--code` | string, required | The code customers type to claim the discount; must be unique within the location. Typically a short alphanumeric string such as SUMMER25 |
| `--description` | string, required | Short text shown to the customer when they enter a valid code, for example 20% off your first month. Required, and translatable per language |
| `--active` | bool | Whether the code can be redeemed at all. When false the code is ignored everywhere, regardless of its validity or publish dates |
| `--publish-from` | DateTime | UTC date and time from which the code can be redeemed on the members portal, website and app. Leave empty to publish immediately |
| `--publish-to` | DateTime | UTC date and time after which the code can no longer be redeemed on the members portal, website and app. Leave empty for no publish end date |
| `--discount-percentage` | decimal | Percentage taken off the price, entered as a whole number so 10 means 10% off. Set either this or DiscountAmount, not both; when both are set DiscountAmount wins |
| `--discount-amount` | decimal | Fixed amount taken off the price, in the location currency. Capped at the item price so the result is never negative. Set either this or DiscountPercentage, not both; when both are set this one wins |
| `--referral-discount` | bool | Whether the discount is granted to the referring customer instead of the person redeeming it. When true, sign-up fails unless the new customer arrived through a referral link, and the discount stops applying if the referrer becomes inactive. To reward both sides, add a second non-referral code using the same Code value |
| `--discount-price-plans` | bool | Whether the code can be used to pay for plans. When false the code never applies to a plan, whatever Tariffs contains |
| `--tariffs` | list, repeat flag | List of plan (tariff) IDs the discount is restricted to. Leave empty to allow any plan. Only has an effect while DiscountPricePlans is true |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--discount-bookings` | bool | Whether the code can be used to pay for bookings. When false the code never applies to a booking, whatever ResourceTypes contains |
| `--resource-types` | list, repeat flag | List of resource type IDs the discount is restricted to. Leave empty to allow any resource type. Only has an effect while DiscountBookings is true, and once the list is set a booking with no resource is excluded |
| `--added-resource-types` | list, repeat flag | IDs added to the ResourceTypes relationship. |
| `--removed-resource-types` | list, repeat flag | IDs removed from the ResourceTypes relationship. |
| `--discount-products` | bool | Whether the code can be used to pay for products. When false the code never applies to a product, whatever Products contains |
| `--products` | list, repeat flag | List of product IDs the discount is restricted to. Leave empty to allow any product. Only has an effect while DiscountProducts is true |
| `--added-products` | list, repeat flag | IDs added to the Products relationship. |
| `--removed-products` | list, repeat flag | IDs removed from the Products relationship. |
| `--discount-events` | bool | Whether the code can be used to pay for event tickets. When false the code never applies to an event, whatever EventCategories contains |
| `--event-categories` | list, repeat flag | List of event category IDs the discount is restricted to. Leave empty to allow any event. Only has an effect while DiscountEvents is true, and an event matches when it belongs to at least one listed category |
| `--added-event-categories` | list, repeat flag | IDs added to the EventCategories relationship. |
| `--removed-event-categories` | list, repeat flag | IDs removed from the EventCategories relationship. |
| `--max-uses-per-user` | int | Maximum number of times one customer may redeem this code. Leave empty for no per-customer limit |
| `--max-uses` | int | Maximum number of redemptions across all customers, after which the code stops working. Leave empty for no overall limit |
| `--only-for-contacts` | bool | Whether the code is restricted to contacts, meaning customers with no active contract. Mutually exclusive with OnlyForMembers; leave both false to allow every customer |
| `--only-for-members` | bool | Whether the code is restricted to members, meaning customers with at least one active contract. Mutually exclusive with OnlyForContacts; leave both false to allow every customer |
| `--valid-from` | DateTime | UTC date and time from which the discount applies. Leave empty for no start date. For bookings this is compared against the booking start time rather than the moment of redemption |
| `--valid-to` | DateTime | UTC date and time after which the discount no longer applies. Leave empty for no end date. For bookings this is compared against the booking end time rather than the moment of redemption |
| `--expiration-type` | enum | Unit used together with ExpiresIn to work out when a claimed code stops working for that customer: Day, Week, Month or Year |
| `--expires-in` | int | How many ExpirationType periods a customer keeps the discount for after claiming it, so 3 with ExpirationType Month expires it three months after the customer claims the code. Leave empty so the discount never expires on its own |

#### DiscountCode update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this discount code is available at. If the location is a network parent, the code can also be redeemed at every location in that network |
| `--code` | string | The code customers type to claim the discount; must be unique within the location. Typically a short alphanumeric string such as SUMMER25 |
| `--description` | string | Short text shown to the customer when they enter a valid code, for example 20% off your first month. Required, and translatable per language |
| `--active` | bool | Whether the code can be redeemed at all. When false the code is ignored everywhere, regardless of its validity or publish dates |
| `--publish-from` | DateTime | UTC date and time from which the code can be redeemed on the members portal, website and app. Leave empty to publish immediately |
| `--publish-to` | DateTime | UTC date and time after which the code can no longer be redeemed on the members portal, website and app. Leave empty for no publish end date |
| `--discount-percentage` | decimal | Percentage taken off the price, entered as a whole number so 10 means 10% off. Set either this or DiscountAmount, not both; when both are set DiscountAmount wins |
| `--discount-amount` | decimal | Fixed amount taken off the price, in the location currency. Capped at the item price so the result is never negative. Set either this or DiscountPercentage, not both; when both are set this one wins |
| `--referral-discount` | bool | Whether the discount is granted to the referring customer instead of the person redeeming it. When true, sign-up fails unless the new customer arrived through a referral link, and the discount stops applying if the referrer becomes inactive. To reward both sides, add a second non-referral code using the same Code value |
| `--discount-price-plans` | bool | Whether the code can be used to pay for plans. When false the code never applies to a plan, whatever Tariffs contains |
| `--tariffs` | list, repeat flag | List of plan (tariff) IDs the discount is restricted to. Leave empty to allow any plan. Only has an effect while DiscountPricePlans is true |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--discount-bookings` | bool | Whether the code can be used to pay for bookings. When false the code never applies to a booking, whatever ResourceTypes contains |
| `--resource-types` | list, repeat flag | List of resource type IDs the discount is restricted to. Leave empty to allow any resource type. Only has an effect while DiscountBookings is true, and once the list is set a booking with no resource is excluded |
| `--added-resource-types` | list, repeat flag | IDs added to the ResourceTypes relationship. |
| `--removed-resource-types` | list, repeat flag | IDs removed from the ResourceTypes relationship. |
| `--discount-products` | bool | Whether the code can be used to pay for products. When false the code never applies to a product, whatever Products contains |
| `--products` | list, repeat flag | List of product IDs the discount is restricted to. Leave empty to allow any product. Only has an effect while DiscountProducts is true |
| `--added-products` | list, repeat flag | IDs added to the Products relationship. |
| `--removed-products` | list, repeat flag | IDs removed from the Products relationship. |
| `--discount-events` | bool | Whether the code can be used to pay for event tickets. When false the code never applies to an event, whatever EventCategories contains |
| `--event-categories` | list, repeat flag | List of event category IDs the discount is restricted to. Leave empty to allow any event. Only has an effect while DiscountEvents is true, and an event matches when it belongs to at least one listed category |
| `--added-event-categories` | list, repeat flag | IDs added to the EventCategories relationship. |
| `--removed-event-categories` | list, repeat flag | IDs removed from the EventCategories relationship. |
| `--max-uses-per-user` | int | Maximum number of times one customer may redeem this code. Leave empty for no per-customer limit |
| `--max-uses` | int | Maximum number of redemptions across all customers, after which the code stops working. Leave empty for no overall limit |
| `--only-for-contacts` | bool | Whether the code is restricted to contacts, meaning customers with no active contract. Mutually exclusive with OnlyForMembers; leave both false to allow every customer |
| `--only-for-members` | bool | Whether the code is restricted to members, meaning customers with at least one active contract. Mutually exclusive with OnlyForContacts; leave both false to allow every customer |
| `--valid-from` | DateTime | UTC date and time from which the discount applies. Leave empty for no start date. For bookings this is compared against the booking start time rather than the moment of redemption |
| `--valid-to` | DateTime | UTC date and time after which the discount no longer applies. Leave empty for no end date. For bookings this is compared against the booking end time rather than the moment of redemption |
| `--expiration-type` | enum | Unit used together with ExpiresIn to work out when a claimed code stops working for that customer: Day, Week, Month or Year |
| `--expires-in` | int | How many ExpirationType periods a customer keeps the discount for after claiming it, so 3 with ExpirationType Month expires it three months after the customer claims the code. Leave empty so the discount never expires on its own |

### DiscountCode (key fields)

`Id`, `Code`, `Description`, `Active`, `DiscountPercentage`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `ResourceTypes`, `AddedResourceTypes`, `RemovedResourceTypes`, `Products`, `AddedProducts`, `RemovedProducts`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`

<!-- END:GENERATED entity=DiscountCodes -->
