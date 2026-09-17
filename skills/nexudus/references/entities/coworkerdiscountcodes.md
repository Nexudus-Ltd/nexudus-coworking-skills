# CoworkerDiscountCodes

<!-- BEGIN:GENERATED entity=CoworkerDiscountCodes -->

A customer discount code (internally CoworkerDiscountCode) is the link between one customer and one discount code offer. Nothing reduces a customer's price until this link exists. It is created when the customer claims a code at sign-up, on the members portal or against a booking, and an operator can also create one directly to give a named customer a discount without sharing a code anyone else could use. The assignment carries its own ValidFrom and ExpiresOn window, which applies on top of the offer's own validity window with the more restrictive of the two winning, and a read-only TimesUsed counter that the offer's per-customer and overall usage caps are checked against. Every other rule stays on the offer itself, so change the discount amount, audience or which purchases it covers on the DiscountCode rather than here. On a referral assignment the holder is the customer who made the referral and RefererGuid identifies the person they referred. BookingUniqueId, when set, reserves the discount for one specific booking.

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
| `--business-id` | long | ID of the location that issued this discount to the customer. When the customer claims a code themselves this is taken from the code's own location, or from the booking's location for a booking-specific claim |
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
| `--notes` | string | Free-text internal note about why the customer has this discount. Filled in automatically for a referral assignment to record who the customer referred |
| `--times-used` | int | Read-only count of how many times this customer has already used the discount. Maintained by invoicing and booking, and it can rise by more than one at a time because an invoice line adds its quantity. Cancelling a booking gives a use back. Checked against the offer's MaxUsesPerUser, and summed across all customers for its overall MaxUses |
| `--from-times-used` | range | |
| `--to-times-used` | range | |
| `--valid-from` | DateTime | UTC date and time from which this customer may use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Leave empty for no customer-specific start. The server rejects a value later than ExpiresOn |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--expires-on` | DateTime | UTC date and time after which this customer may no longer use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Calculated from the offer's ExpirationType and ExpiresIn when the customer claims a code themselves, but not when an operator assigns one directly, so set it explicitly if the discount should lapse. Leave empty for no customer-specific end |
| `--from-expires-on` | range | |
| `--to-expires-on` | range | |
| `--referer-guid` | string | System-managed unique identifier of the customer who was referred, meaning the person who signed up with the code, while the holder of this assignment is the one being rewarded. Set by the referral sign-up flow; a referral discount stops applying once the referred customer is no longer active. Do not set this by hand to simulate a referral |
| `--booking-unique-id` | string | System-managed unique identifier of the booking this discount is reserved for. When empty the discount can be used for any eligible purchase; when set it only applies to that one booking. Populated by the booking flow when a customer enters a code against a booking |
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
| `--business-id` | long, required | ID of the location that issued this discount to the customer. When the customer claims a code themselves this is taken from the code's own location, or from the booking's location for a booking-specific claim |
| `--discount-code-id` | long, required | ID of the discount code offer granted to the customer. Every rule on that offer still applies on top of this assignment, including its active flag, validity window, usage caps, audience and which kinds of purchase it pays for |
| `--notes` | string | Free-text internal note about why the customer has this discount. Filled in automatically for a referral assignment to record who the customer referred |
| `--valid-from` | DateTime | UTC date and time from which this customer may use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Leave empty for no customer-specific start. The server rejects a value later than ExpiresOn |
| `--expires-on` | DateTime | UTC date and time after which this customer may no longer use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Calculated from the offer's ExpirationType and ExpiresIn when the customer claims a code themselves, but not when an operator assigns one directly, so set it explicitly if the discount should lapse. Leave empty for no customer-specific end |
| `--referer-guid` | string | System-managed unique identifier of the customer who was referred, meaning the person who signed up with the code, while the holder of this assignment is the one being rewarded. Set by the referral sign-up flow; a referral discount stops applying once the referred customer is no longer active. Do not set this by hand to simulate a referral |
| `--booking-unique-id` | string | System-managed unique identifier of the booking this discount is reserved for. When empty the discount can be used for any eligible purchase; when set it only applies to that one booking. Populated by the booking flow when a customer enters a code against a booking |

#### CoworkerDiscountCode update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer who holds this discount and receives the reduced price. On a referral assignment this is the customer who made the referral, not the person who was referred |
| `--business-id` | long | ID of the location that issued this discount to the customer. When the customer claims a code themselves this is taken from the code's own location, or from the booking's location for a booking-specific claim |
| `--discount-code-id` | long | ID of the discount code offer granted to the customer. Every rule on that offer still applies on top of this assignment, including its active flag, validity window, usage caps, audience and which kinds of purchase it pays for |
| `--notes` | string | Free-text internal note about why the customer has this discount. Filled in automatically for a referral assignment to record who the customer referred |
| `--valid-from` | DateTime | UTC date and time from which this customer may use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Leave empty for no customer-specific start. The server rejects a value later than ExpiresOn |
| `--expires-on` | DateTime | UTC date and time after which this customer may no longer use the discount, on top of the offer's own validity window; the more restrictive of the two applies. Calculated from the offer's ExpirationType and ExpiresIn when the customer claims a code themselves, but not when an operator assigns one directly, so set it explicitly if the discount should lapse. Leave empty for no customer-specific end |
| `--referer-guid` | string | System-managed unique identifier of the customer who was referred, meaning the person who signed up with the code, while the holder of this assignment is the one being rewarded. Set by the referral sign-up flow; a referral discount stops applying once the referred customer is no longer active. Do not set this by hand to simulate a referral |
| `--booking-unique-id` | string | System-managed unique identifier of the booking this discount is reserved for. When empty the discount can be used for any eligible purchase; when set it only applies to that one booking. Populated by the booking flow when a customer enters a code against a booking |

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
