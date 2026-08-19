# CoworkerDiscountCodes

<!-- BEGIN:GENERATED entity=CoworkerDiscountCodes -->

A **CoworkerDiscountCode** assigns a `DiscountCode` to a specific customer, allowing the system to track per-customer redemption history and enforce individual validity windows.

Use `ValidFrom` and `ExpiresOn` to set customer-specific validity dates. These are distinct from the discount code's own `ValidFrom`/`ValidTo` and `ExpirationType`/`ExpiresIn` fields — the system enforces whichever constraint is more restrictive.

When the discount is part of the referral programme, `RefererGuid` identifies the referring customer. `BookingUniqueId` links the assignment to the specific booking where the code was originally applied.

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
| `--coworker-id` | long | ID of the customer this discount code is assigned to |
| `--coworker-coworker-type` | string | Whether the customer is an individual or a company |
| `--coworker-full-name` | string | Full name of the customer this discount code is assigned to |
| `--coworker-billing-name` | string | Billing name of the customer |
| `--coworker-company-name` | string | Company name of the customer |
| `--business-id` | long | ID of the location this assignment belongs to |
| `--business-name` | string | Name of the location this assignment belongs to |
| `--discount-code-id` | long | ID of the discount code assigned to this customer |
| `--discount-code-code` | string | The alphanumeric code customers enter to apply the discount |
| `--discount-code-active` | bool | Whether the discount code is currently active and can be redeemed |
| `--discount-code-valid-from` | DateTime | Start date from which the discount code itself can be redeemed (set on the discount code) |
| `--from-discount-code-valid-from` | range | |
| `--to-discount-code-valid-from` | range | |
| `--discount-code-valid-to` | DateTime | End date after which the discount code itself can no longer be redeemed (set on the discount code) |
| `--from-discount-code-valid-to` | range | |
| `--to-discount-code-valid-to` | range | |
| `--notes` | string | Optional notes about this discount code assignment |
| `--times-used` | int | Number of times this customer has redeemed the discount code |
| `--from-times-used` | range | |
| `--to-times-used` | range | |
| `--valid-from` | DateTime | Customer-specific date from which this discount code assignment becomes valid |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--expires-on` | DateTime | Customer-specific date after which this discount code assignment expires |
| `--from-expires-on` | range | |
| `--to-expires-on` | range | |
| `--referer-guid` | string | Unique identifier of the customer who referred this customer, when the discount is part of the referral programme |
| `--booking-unique-id` | string | Unique identifier of the booking to which this discount code was applied |
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
| `--coworker-id` | long, required | ID of the customer this discount code is assigned to |
| `--business-id` | long, required | ID of the location this assignment belongs to |
| `--discount-code-id` | long, required | ID of the discount code assigned to this customer |
| `--notes` | string | Optional notes about this discount code assignment |
| `--valid-from` | DateTime | Customer-specific date from which this discount code assignment becomes valid |
| `--expires-on` | DateTime | Customer-specific date after which this discount code assignment expires |
| `--referer-guid` | string | Unique identifier of the customer who referred this customer, when the discount is part of the referral programme |
| `--booking-unique-id` | string | Unique identifier of the booking to which this discount code was applied |

#### CoworkerDiscountCode update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer this discount code is assigned to |
| `--business-id` | long | ID of the location this assignment belongs to |
| `--discount-code-id` | long | ID of the discount code assigned to this customer |
| `--notes` | string | Optional notes about this discount code assignment |
| `--valid-from` | DateTime | Customer-specific date from which this discount code assignment becomes valid |
| `--expires-on` | DateTime | Customer-specific date after which this discount code assignment expires |
| `--referer-guid` | string | Unique identifier of the customer who referred this customer, when the discount is part of the referral programme |
| `--booking-unique-id` | string | Unique identifier of the booking to which this discount code was applied |

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
