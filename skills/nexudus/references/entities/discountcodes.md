# DiscountCodes

<!-- BEGIN:GENERATED entity=DiscountCodes -->

A discount code (internally DiscountCode) is a code operators share with customers to take a percentage or a fixed amount off plan fees, bookings, products or event tickets. Each code belongs to a location, and a code on a network parent location also works at every location beneath it. Set either DiscountPercentage or DiscountAmount and leave the other null; any DiscountAmount value takes precedence and is capped at the price. The DiscountPricePlans, DiscountBookings, DiscountProducts and DiscountEvents flags choose which kinds of purchase the code reduces, and the matching Tariffs, ResourceTypes, Products and EventCategories lists narrow each one to specific items, where an empty list allows every item of that kind. On create, omitted booleans are saved as false, so send Active and at least one of those four flags as true or the code reduces nothing. On update each list replaces the whole collection, so send the complete intended set of IDs. PublishFrom/PublishTo control when customers can enter the code, while ValidFrom/ValidTo control when it reduces prices; usage caps (MaxUses, MaxUsesPerUser) and audience (OnlyForContacts, OnlyForMembers) limit it further. Entering a code creates a customer discount code (CoworkerDiscountCode) linking it to that customer, and ExpirationType with ExpiresIn sets how long the customer keeps it. When a customer holds several applicable codes, only the one giving the lowest price is applied to each charge. Set ReferralDiscount when the discount should reward the referring customer instead of the new customer.

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
| `--business-id` | long | ID of the location that owns this discount code. Customers can enter it at this location and at every location beneath it in the network, so a code on a network parent location works across the whole network |
| `--business-name` | string | Display value for Business.Name. |
| `--business-currency-code` | string | Display value for Business.Currency.Code. |
| `--code` | string | Text customers enter to claim the discount, typically a short alphanumeric string such as SUMMER25. Uniqueness is not enforced: at sign-up every published code with the same text at this location or its parent network locations is claimed together, which is how a referral code and a regular code reward both sides; otherwise keep codes distinct |
| `--description` | string | Customer-facing text shown when a valid code is entered and appended to the invoice line the discount reduces, for example 20% off your first month. Required, and translatable per language |
| `--active` | bool | Whether the code is switched on. When false customers cannot enter it and it stops reducing prices for customers who already claimed it, whatever the validity and publish dates. Omitting it on create saves false |
| `--publish-from` | DateTime | UTC date and time from which customers can enter the code on the members portal, website and app, at sign-up, checkout or when booking. Leave empty to publish immediately. This controls when the code can be entered; ValidFrom controls when it reduces prices |
| `--from-publish-from` | range | |
| `--to-publish-from` | range | |
| `--publish-to` | DateTime | UTC date and time after which customers can no longer enter the code on the members portal, website and app. Leave empty for no publish end date. Customers who already claimed the code keep it until ValidTo or their own expiry |
| `--from-publish-to` | range | |
| `--to-publish-to` | range | |
| `--discount-percentage` | decimal | Percentage taken off the price, entered as a whole number so 10 means 10% off, rounded to 2 decimals. Set either this or DiscountAmount and leave the other empty (null, not 0): any DiscountAmount value, even 0, takes precedence and this percentage is then ignored |
| `--from-discount-percentage` | range | |
| `--to-discount-percentage` | range | |
| `--discount-amount` | decimal | Fixed amount taken off each discounted price, in the location currency, for example 25 means 25 off. Capped at the price so the result is never negative. Set either this or DiscountPercentage and leave the other empty (null, not 0): any value here, even 0, takes precedence over DiscountPercentage |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--referral-discount` | bool | Whether the discount rewards the referring customer instead of the new customer who enters the code. When true, sign-up with this code fails unless the new customer arrived through a referral link, and the referrer's discount only applies while the referred customer's account stays active. To reward both sides, add a second non-referral code with the same Code value |
| `--discount-price-plans` | bool | Whether the code reduces plan fees on invoices. When false it never applies to a plan, whatever Tariffs contains. Omitting it on create saves false |
| `--discount-bookings` | bool | Whether the code reduces booking prices. When false it never applies to a booking, whatever ResourceTypes contains. Omitting it on create saves false |
| `--discount-products` | bool | Whether the code reduces product prices, including products bought in the store or added to a booking. When false it never applies to a product, whatever Products contains. Omitting it on create saves false |
| `--discount-events` | bool | Whether the code reduces event ticket prices. When false it never applies to an event, whatever EventCategories contains. Omitting it on create saves false |
| `--max-uses-per-user` | int | Maximum number of times the discount can be applied for one customer. Every discounted plan invoice, booking or event ticket counts as one use and a product counts once per unit bought, so 3 on a plan discount covers the first three plan invoices. Leave empty for no per-customer limit |
| `--from-max-uses-per-user` | range | |
| `--to-max-uses-per-user` | range | |
| `--max-uses` | int | Maximum number of uses across all customers, counted the same way as MaxUsesPerUser, after which the code stops being accepted or applied. Leave empty for no overall limit |
| `--from-max-uses` | range | |
| `--to-max-uses` | range | |
| `--only-for-contacts` | bool | Whether only contacts, meaning customers with no active contract, can use the code. Checked each time the discount applies, so it stops applying once the customer has an active contract. Set at most one of this and OnlyForMembers, since setting both blocks every customer; leave both false to allow everyone |
| `--only-for-members` | bool | Whether only members, meaning customers with at least one active contract, can use the code. Checked each time the discount applies. Set at most one of this and OnlyForContacts, since setting both blocks every customer; leave both false to allow everyone |
| `--valid-from` | DateTime | UTC date and time from which the discount reduces prices. Leave empty for no start date. Compared with the invoice period start for plans, the booking start for bookings and the purchase time for products and events, not with the moment the code was entered |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--valid-to` | DateTime | UTC date and time after which the discount no longer reduces prices, for customers who already claimed it too. Leave empty for no end date. Compared with the invoice period start for plans and the purchase time for products and events; a booking must end on or before this time |
| `--from-valid-to` | range | |
| `--to-valid-to` | range | |
| `--expiration-type` | enum | Unit for ExpiresIn (Day, Week, Month or Year) used to work out when a claimed code stops working for that customer. Ignored while ExpiresIn is empty, and when this is empty the claimed code never expires |
| `--expires-in` | int | How many ExpirationType periods a customer keeps the discount after claiming it, so 3 with ExpirationType Month expires it three months after the claim. The expiry date is stamped on the customer's claim, so changing this does not affect earlier claims. Leave empty so claimed codes never expire on their own |
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
| `--business-id` | long, required | ID of the location that owns this discount code. Customers can enter it at this location and at every location beneath it in the network, so a code on a network parent location works across the whole network |
| `--code` | string, required | Text customers enter to claim the discount, typically a short alphanumeric string such as SUMMER25. Uniqueness is not enforced: at sign-up every published code with the same text at this location or its parent network locations is claimed together, which is how a referral code and a regular code reward both sides; otherwise keep codes distinct |
| `--description` | string, required | Customer-facing text shown when a valid code is entered and appended to the invoice line the discount reduces, for example 20% off your first month. Required, and translatable per language |
| `--active` | bool | Whether the code is switched on. When false customers cannot enter it and it stops reducing prices for customers who already claimed it, whatever the validity and publish dates. Omitting it on create saves false |
| `--publish-from` | DateTime | UTC date and time from which customers can enter the code on the members portal, website and app, at sign-up, checkout or when booking. Leave empty to publish immediately. This controls when the code can be entered; ValidFrom controls when it reduces prices |
| `--publish-to` | DateTime | UTC date and time after which customers can no longer enter the code on the members portal, website and app. Leave empty for no publish end date. Customers who already claimed the code keep it until ValidTo or their own expiry |
| `--discount-percentage` | decimal | Percentage taken off the price, entered as a whole number so 10 means 10% off, rounded to 2 decimals. Set either this or DiscountAmount and leave the other empty (null, not 0): any DiscountAmount value, even 0, takes precedence and this percentage is then ignored |
| `--discount-amount` | decimal | Fixed amount taken off each discounted price, in the location currency, for example 25 means 25 off. Capped at the price so the result is never negative. Set either this or DiscountPercentage and leave the other empty (null, not 0): any value here, even 0, takes precedence over DiscountPercentage |
| `--referral-discount` | bool | Whether the discount rewards the referring customer instead of the new customer who enters the code. When true, sign-up with this code fails unless the new customer arrived through a referral link, and the referrer's discount only applies while the referred customer's account stays active. To reward both sides, add a second non-referral code with the same Code value |
| `--discount-price-plans` | bool | Whether the code reduces plan fees on invoices. When false it never applies to a plan, whatever Tariffs contains. Omitting it on create saves false |
| `--tariffs` | list, repeat flag | List of plan (tariff) IDs the discount is restricted to. An empty list allows every plan. Only has an effect while DiscountPricePlans is true |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--discount-bookings` | bool | Whether the code reduces booking prices. When false it never applies to a booking, whatever ResourceTypes contains. Omitting it on create saves false |
| `--resource-types` | list, repeat flag | List of resource type IDs the discount is restricted to; a booking qualifies when its resource has one of these types. An empty list allows every resource. Only has an effect while DiscountBookings is true |
| `--added-resource-types` | list, repeat flag | IDs added to the ResourceTypes relationship. |
| `--removed-resource-types` | list, repeat flag | IDs removed from the ResourceTypes relationship. |
| `--discount-products` | bool | Whether the code reduces product prices, including products bought in the store or added to a booking. When false it never applies to a product, whatever Products contains. Omitting it on create saves false |
| `--products` | list, repeat flag | List of product IDs the discount is restricted to. An empty list allows every product. Only has an effect while DiscountProducts is true |
| `--added-products` | list, repeat flag | IDs added to the Products relationship. |
| `--removed-products` | list, repeat flag | IDs removed from the Products relationship. |
| `--discount-events` | bool | Whether the code reduces event ticket prices. When false it never applies to an event, whatever EventCategories contains. Omitting it on create saves false |
| `--event-categories` | list, repeat flag | List of event category IDs the discount is restricted to; an event qualifies when it belongs to at least one listed category. An empty list allows every event. Only has an effect while DiscountEvents is true |
| `--added-event-categories` | list, repeat flag | IDs added to the EventCategories relationship. |
| `--removed-event-categories` | list, repeat flag | IDs removed from the EventCategories relationship. |
| `--max-uses-per-user` | int | Maximum number of times the discount can be applied for one customer. Every discounted plan invoice, booking or event ticket counts as one use and a product counts once per unit bought, so 3 on a plan discount covers the first three plan invoices. Leave empty for no per-customer limit |
| `--max-uses` | int | Maximum number of uses across all customers, counted the same way as MaxUsesPerUser, after which the code stops being accepted or applied. Leave empty for no overall limit |
| `--only-for-contacts` | bool | Whether only contacts, meaning customers with no active contract, can use the code. Checked each time the discount applies, so it stops applying once the customer has an active contract. Set at most one of this and OnlyForMembers, since setting both blocks every customer; leave both false to allow everyone |
| `--only-for-members` | bool | Whether only members, meaning customers with at least one active contract, can use the code. Checked each time the discount applies. Set at most one of this and OnlyForContacts, since setting both blocks every customer; leave both false to allow everyone |
| `--valid-from` | DateTime | UTC date and time from which the discount reduces prices. Leave empty for no start date. Compared with the invoice period start for plans, the booking start for bookings and the purchase time for products and events, not with the moment the code was entered |
| `--valid-to` | DateTime | UTC date and time after which the discount no longer reduces prices, for customers who already claimed it too. Leave empty for no end date. Compared with the invoice period start for plans and the purchase time for products and events; a booking must end on or before this time |
| `--expiration-type` | enum | Unit for ExpiresIn (Day, Week, Month or Year) used to work out when a claimed code stops working for that customer. Ignored while ExpiresIn is empty, and when this is empty the claimed code never expires |
| `--expires-in` | int | How many ExpirationType periods a customer keeps the discount after claiming it, so 3 with ExpirationType Month expires it three months after the claim. The expiry date is stamped on the customer's claim, so changing this does not affect earlier claims. Leave empty so claimed codes never expire on their own |

#### DiscountCode update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this discount code. Customers can enter it at this location and at every location beneath it in the network, so a code on a network parent location works across the whole network |
| `--code` | string | Text customers enter to claim the discount, typically a short alphanumeric string such as SUMMER25. Uniqueness is not enforced: at sign-up every published code with the same text at this location or its parent network locations is claimed together, which is how a referral code and a regular code reward both sides; otherwise keep codes distinct |
| `--description` | string | Customer-facing text shown when a valid code is entered and appended to the invoice line the discount reduces, for example 20% off your first month. Required, and translatable per language |
| `--active` | bool | Whether the code is switched on. When false customers cannot enter it and it stops reducing prices for customers who already claimed it, whatever the validity and publish dates. Omitting it on create saves false |
| `--publish-from` | DateTime | UTC date and time from which customers can enter the code on the members portal, website and app, at sign-up, checkout or when booking. Leave empty to publish immediately. This controls when the code can be entered; ValidFrom controls when it reduces prices |
| `--publish-to` | DateTime | UTC date and time after which customers can no longer enter the code on the members portal, website and app. Leave empty for no publish end date. Customers who already claimed the code keep it until ValidTo or their own expiry |
| `--discount-percentage` | decimal | Percentage taken off the price, entered as a whole number so 10 means 10% off, rounded to 2 decimals. Set either this or DiscountAmount and leave the other empty (null, not 0): any DiscountAmount value, even 0, takes precedence and this percentage is then ignored |
| `--discount-amount` | decimal | Fixed amount taken off each discounted price, in the location currency, for example 25 means 25 off. Capped at the price so the result is never negative. Set either this or DiscountPercentage and leave the other empty (null, not 0): any value here, even 0, takes precedence over DiscountPercentage |
| `--referral-discount` | bool | Whether the discount rewards the referring customer instead of the new customer who enters the code. When true, sign-up with this code fails unless the new customer arrived through a referral link, and the referrer's discount only applies while the referred customer's account stays active. To reward both sides, add a second non-referral code with the same Code value |
| `--discount-price-plans` | bool | Whether the code reduces plan fees on invoices. When false it never applies to a plan, whatever Tariffs contains. Omitting it on create saves false |
| `--tariffs` | list, repeat flag | List of plan (tariff) IDs the discount is restricted to. An empty list allows every plan. Only has an effect while DiscountPricePlans is true |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--discount-bookings` | bool | Whether the code reduces booking prices. When false it never applies to a booking, whatever ResourceTypes contains. Omitting it on create saves false |
| `--resource-types` | list, repeat flag | List of resource type IDs the discount is restricted to; a booking qualifies when its resource has one of these types. An empty list allows every resource. Only has an effect while DiscountBookings is true |
| `--added-resource-types` | list, repeat flag | IDs added to the ResourceTypes relationship. |
| `--removed-resource-types` | list, repeat flag | IDs removed from the ResourceTypes relationship. |
| `--discount-products` | bool | Whether the code reduces product prices, including products bought in the store or added to a booking. When false it never applies to a product, whatever Products contains. Omitting it on create saves false |
| `--products` | list, repeat flag | List of product IDs the discount is restricted to. An empty list allows every product. Only has an effect while DiscountProducts is true |
| `--added-products` | list, repeat flag | IDs added to the Products relationship. |
| `--removed-products` | list, repeat flag | IDs removed from the Products relationship. |
| `--discount-events` | bool | Whether the code reduces event ticket prices. When false it never applies to an event, whatever EventCategories contains. Omitting it on create saves false |
| `--event-categories` | list, repeat flag | List of event category IDs the discount is restricted to; an event qualifies when it belongs to at least one listed category. An empty list allows every event. Only has an effect while DiscountEvents is true |
| `--added-event-categories` | list, repeat flag | IDs added to the EventCategories relationship. |
| `--removed-event-categories` | list, repeat flag | IDs removed from the EventCategories relationship. |
| `--max-uses-per-user` | int | Maximum number of times the discount can be applied for one customer. Every discounted plan invoice, booking or event ticket counts as one use and a product counts once per unit bought, so 3 on a plan discount covers the first three plan invoices. Leave empty for no per-customer limit |
| `--max-uses` | int | Maximum number of uses across all customers, counted the same way as MaxUsesPerUser, after which the code stops being accepted or applied. Leave empty for no overall limit |
| `--only-for-contacts` | bool | Whether only contacts, meaning customers with no active contract, can use the code. Checked each time the discount applies, so it stops applying once the customer has an active contract. Set at most one of this and OnlyForMembers, since setting both blocks every customer; leave both false to allow everyone |
| `--only-for-members` | bool | Whether only members, meaning customers with at least one active contract, can use the code. Checked each time the discount applies. Set at most one of this and OnlyForContacts, since setting both blocks every customer; leave both false to allow everyone |
| `--valid-from` | DateTime | UTC date and time from which the discount reduces prices. Leave empty for no start date. Compared with the invoice period start for plans, the booking start for bookings and the purchase time for products and events, not with the moment the code was entered |
| `--valid-to` | DateTime | UTC date and time after which the discount no longer reduces prices, for customers who already claimed it too. Leave empty for no end date. Compared with the invoice period start for plans and the purchase time for products and events; a booking must end on or before this time |
| `--expiration-type` | enum | Unit for ExpiresIn (Day, Week, Month or Year) used to work out when a claimed code stops working for that customer. Ignored while ExpiresIn is empty, and when this is empty the claimed code never expires |
| `--expires-in` | int | How many ExpirationType periods a customer keeps the discount after claiming it, so 3 with ExpirationType Month expires it three months after the claim. The expiry date is stamped on the customer's claim, so changing this does not affect earlier claims. Leave empty so claimed codes never expire on their own |

### DiscountCode (key fields)

`Id`, `Code`, `Description`, `Active`, `DiscountPercentage`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `ResourceTypes`, `AddedResourceTypes`, `RemovedResourceTypes`, `Products`, `AddedProducts`, `RemovedProducts`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`

<!-- END:GENERATED entity=DiscountCodes -->
