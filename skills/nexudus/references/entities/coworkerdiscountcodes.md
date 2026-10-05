# CoworkerDiscountCodes

<!-- BEGIN:GENERATED entity=CoworkerDiscountCodes -->

A customer discount code (internally CoworkerDiscountCode) is the link between one customer and one discount code offer. Nothing reduces a customer's price until this link exists. It is created when the customer claims a code at sign-up, at checkout or against a booking, when a proposal carrying a discount code is accepted, or when an operator creates one directly to give a named customer a discount without sharing a code anyone else could use. It only reduces charges at its own location (Business) and the locations beneath it. The assignment carries its own ValidFrom and ExpiresOn window, which applies on top of the offer's own validity window with the more restrictive of the two winning, and a read-only TimesUsed counter that the offer's per-customer and overall usage caps are checked against. Every other rule stays on the offer itself, so change the discount amount, audience or which purchases it covers on the DiscountCode rather than here. On a referral assignment the holder is the customer who made the referral, Notes names the person they referred, and the reward stops once that referred customer is no longer active. BookingUniqueId, when set, limits the discount to that one booking among bookings.

CoworkerDiscountCodes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerdiscountcodes list --agent` | List all coworkerdiscountcodes |
| `nexudus coworkerdiscountcodes list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerdiscountcodes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerdiscountcodes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerdiscountcodes list --coworker-full-name <value> --discount-code-code <value> --agent` | Filter coworkerdiscountcodes by properties |
| `nexudus coworkerdiscountcodes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerdiscountcodes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerdiscountcodes get <id> --agent` | Get single coworkerdiscountcode |
| `nexudus coworkerdiscountcodes create --coworker-id <value> --business-id <value> --discount-code-id <value> --agent` | Create coworkerdiscountcode |
| `nexudus coworkerdiscountcodes update <id> --name "New Name" --agent` | Update coworkerdiscountcode |
| `nexudus coworkerdiscountcodes delete <id> --yes --agent` | Delete coworkerdiscountcode (no prompt) |

#### CoworkerDiscountCode list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer who holds this discount and receives the reduced price. On a referral assignment this is the customer who made the referral, not the person who was referred |
| `--coworker-coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--business-id` | long | ID of the location that issued this discount to the customer. The discount only reduces charges at this location and the locations beneath it in the network. When the customer claims a code themselves this is taken from the code's own location, or from the booking's location for a booking-specific claim |
| `--business-name` | string | Display value for Business.Name. |
| `--discount-code-id` | long | ID of the discount code offer granted to the customer. Every rule on that offer still applies on top of this assignment, including its active flag, validity window, usage caps, audience and which kinds of purchase it pays for |
| `--discount-code-code` | string | Display value for DiscountCode.Code. |
| `--discount-code-active` | bool | Display value for DiscountCode.Active. |
| `--discount-code-valid-from` | DateTime | Display value for DiscountCode.ValidFrom. |
| `--from-discount-code-valid-from` | range | |
| `--to-discount-code-valid-from` | range | |
| `--discount-code-valid-to` | DateTime | Display value for DiscountCode.ValidTo. |
| `--from-discount-code-valid-to` | range | |
| `--to-discount-code-valid-to` | range | |
| `--discount-code-max-uses-per-user` | int | Display value for DiscountCode.MaxUsesPerUser. |
| `--from-discount-code-max-uses-per-user` | range | |
| `--to-discount-code-max-uses-per-user` | range | |
| `--notes` | string | Free-text internal note about why the customer has this discount. Filled in automatically for a referral assignment to record who the customer referred |
| `--times-used` | int | Read-only count of how many times this customer has already used the discount. Maintained by invoicing and booking: each discounted plan invoice, booking or event ticket adds one and a product line adds its quantity, while reverting a booking's charges, for example on cancellation, gives a use back. Checked against the offer's MaxUsesPerUser, and summed across all customers for its overall MaxUses; a customer at the cap keeps this record but stops getting the discount |
| `--from-times-used` | range | |
| `--to-times-used` | range | |
| `--valid-from` | DateTime | UTC date and time from which this customer may use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Compared with the invoiced period start for plans, the booking start for bookings and the purchase time for products and events. Leave empty for no customer-specific start. The server rejects a value later than ExpiresOn |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--expires-on` | DateTime | UTC date and time after which this customer may no longer use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Compared the same way as ValidFrom and inclusive of this moment. Calculated from the offer's ExpirationType and ExpiresIn when the customer claims a code themselves, but not when an operator assigns one directly, so set it explicitly if the discount should lapse. Leave empty for no customer-specific end |
| `--from-expires-on` | range | |
| `--to-expires-on` | range | |
| `--referer-guid` | string | System-managed unique identifier of the customer who was referred, meaning the person who signed up with the code, while the holder of this assignment is the one being rewarded. Set by the referral sign-up flow and not shown in the Admin Panel or the agent tools, which see the referred customer's name in Notes instead; a referral discount stops applying once the referred customer is no longer active |
| `--booking-unique-id` | string | System-managed unique identifier of the booking this discount was claimed against. When set, that is the only booking the discount can reduce, although plan, product and event discounts do not check it; when empty it can reduce any eligible booking. Populated by the booking flow when a customer enters a code against a booking; leave it empty when assigning a discount by hand |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerDiscountCode sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerDiscountCode create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer who holds this discount and receives the reduced price. On a referral assignment this is the customer who made the referral, not the person who was referred |
| `--business-id` | long, required | ID of the location that issued this discount to the customer. The discount only reduces charges at this location and the locations beneath it in the network. When the customer claims a code themselves this is taken from the code's own location, or from the booking's location for a booking-specific claim |
| `--discount-code-id` | long, required | ID of the discount code offer granted to the customer. Every rule on that offer still applies on top of this assignment, including its active flag, validity window, usage caps, audience and which kinds of purchase it pays for |
| `--notes` | string | Free-text internal note about why the customer has this discount. Filled in automatically for a referral assignment to record who the customer referred |
| `--valid-from` | DateTime | UTC date and time from which this customer may use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Compared with the invoiced period start for plans, the booking start for bookings and the purchase time for products and events. Leave empty for no customer-specific start. The server rejects a value later than ExpiresOn |
| `--expires-on` | DateTime | UTC date and time after which this customer may no longer use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Compared the same way as ValidFrom and inclusive of this moment. Calculated from the offer's ExpirationType and ExpiresIn when the customer claims a code themselves, but not when an operator assigns one directly, so set it explicitly if the discount should lapse. Leave empty for no customer-specific end |
| `--referer-guid` | string | System-managed unique identifier of the customer who was referred, meaning the person who signed up with the code, while the holder of this assignment is the one being rewarded. Set by the referral sign-up flow and not shown in the Admin Panel or the agent tools, which see the referred customer's name in Notes instead; a referral discount stops applying once the referred customer is no longer active |
| `--booking-unique-id` | string | System-managed unique identifier of the booking this discount was claimed against. When set, that is the only booking the discount can reduce, although plan, product and event discounts do not check it; when empty it can reduce any eligible booking. Populated by the booking flow when a customer enters a code against a booking; leave it empty when assigning a discount by hand |

#### CoworkerDiscountCode update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer who holds this discount and receives the reduced price. On a referral assignment this is the customer who made the referral, not the person who was referred |
| `--business-id` | long | ID of the location that issued this discount to the customer. The discount only reduces charges at this location and the locations beneath it in the network. When the customer claims a code themselves this is taken from the code's own location, or from the booking's location for a booking-specific claim |
| `--discount-code-id` | long | ID of the discount code offer granted to the customer. Every rule on that offer still applies on top of this assignment, including its active flag, validity window, usage caps, audience and which kinds of purchase it pays for |
| `--notes` | string | Free-text internal note about why the customer has this discount. Filled in automatically for a referral assignment to record who the customer referred |
| `--valid-from` | DateTime | UTC date and time from which this customer may use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Compared with the invoiced period start for plans, the booking start for bookings and the purchase time for products and events. Leave empty for no customer-specific start. The server rejects a value later than ExpiresOn |
| `--expires-on` | DateTime | UTC date and time after which this customer may no longer use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Compared the same way as ValidFrom and inclusive of this moment. Calculated from the offer's ExpirationType and ExpiresIn when the customer claims a code themselves, but not when an operator assigns one directly, so set it explicitly if the discount should lapse. Leave empty for no customer-specific end |
| `--referer-guid` | string | System-managed unique identifier of the customer who was referred, meaning the person who signed up with the code, while the holder of this assignment is the one being rewarded. Set by the referral sign-up flow and not shown in the Admin Panel or the agent tools, which see the referred customer's name in Notes instead; a referral discount stops applying once the referred customer is no longer active |
| `--booking-unique-id` | string | System-managed unique identifier of the booking this discount was claimed against. When set, that is the only booking the discount can reduce, although plan, product and event discounts do not check it; when empty it can reduce any eligible booking. Populated by the booking flow when a customer enters a code against a booking; leave it empty when assigning a discount by hand |

#### CoworkerDiscountCode PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkerdiscountcodes update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerDiscountCode (key fields)

`Id`, `CoworkerFullName`, `DiscountCodeCode`

<!-- END:GENERATED entity=CoworkerDiscountCodes -->
