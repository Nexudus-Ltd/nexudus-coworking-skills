# Charges

<!-- BEGIN:GENERATED entity=Charges -->

A **Charge** is a generic debit item applied to a customer account. Prefer more specific entities when available — use `CoworkerProduct` for product sales, `Booking` for room/resource bookings, `EventAttendee` for event registrations, and `CoworkerContract` for recurring plan charges.

Charges can reference the originating sale from another entity via its `UniqueId` (a GUID, not an integer ID). This is how items billed to a non-paying team member are passed through to the team's paying member: the charge appears on the paying member's account with a `UniqueId` reference back to the original `CoworkerProduct`, `Booking`, `EventAttendee`, or `CoworkerTimePass`.

Booking-related extra-service charges are represented by `CoworkerExtraService` records and referenced via `CoworkerExtraServiceUniqueId`.

Charges support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus charges list --agent` | List all charges |
| `nexudus charges list --id <id> --agent` | Filter by single ID |
| `nexudus charges list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus charges list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus charges list --description <value> --total-amount <value> --agent` | Filter charges by properties |
| `nexudus charges list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus charges list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus charges get <id> --agent` | Get single charge |
| `nexudus charges create --coworker-id <value> --business-id <value> --quantity <value> --discount-amount <value> --credit-amount <value> --total-amount <value> --agent` | Create charge |
| `nexudus charges update <id> --name "New Name" --agent` | Update charge |
| `nexudus charges delete <id> --yes --agent` | Delete charge (no prompt) |

#### Charge list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--quantity` | int | Number of units |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--description` | string | Free-text description of this charge |
| `--invoice-line-display-as` | string | Display text on invoice line |
| `--regular-charge` | bool | Whether this is a regular charge |
| `--discount-amount` | decimal | Discount amount |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--credit-amount` | decimal | Credit amount |
| `--from-credit-amount` | range | |
| `--to-credit-amount` | range | |
| `--due-date` | DateTime | Due date |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--total-amount` | decimal | Total amount |
| `--from-total-amount` | range | |
| `--to-total-amount` | range | |
| `--purchase-order` | string | Purchase order |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--invoiced` | bool | Whether the charge has been invoiced |
| `--sale-date` | DateTime | Sale date |
| `--from-sale-date` | range | |
| `--to-sale-date` | range | |
| `--from-team-member` | bool | Whether from team member is enabled |
| `--coworker-extra-service-name` | string | The coworker extra service name value for this charge |
| `--coworker-time-pass-name` | string | The coworker time pass name value for this charge |
| `--coworker-product-name` | string | The coworker product name value for this charge |
| `--tariff-name` | string | The tariff name value for this charge |
| `--coworker-product-unique-id` | string | ID of the coworker product unique associated with this record |
| `--booking-unique-id` | string | ID of the booking unique associated with this record |
| `--repeat-from` | DateTime | Repeat from date |
| `--from-repeat-from` | range | |
| `--to-repeat-from` | range | |
| `--repeat-until` | DateTime | Repeat until date |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Charge sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Charge create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--business-id` | long, required | ID of the business linked to this record |
| `--quantity` | int, required | Number of units |
| `--description` | string | Free-text description of this charge |
| `--invoice-line-display-as` | string | Display text on invoice line |
| `--regular-charge` | bool | Whether this is a regular charge |
| `--discount-amount` | decimal, required | Discount amount |
| `--credit-amount` | decimal, required | Credit amount |
| `--due-date` | DateTime | Due date |
| `--total-amount` | decimal, required | Total amount |
| `--purchase-order` | string | Purchase order |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--invoiced` | bool | Whether the charge has been invoiced |
| `--sale-date` | DateTime | Sale date |
| `--from-team-member` | bool | Whether from team member is enabled |
| `--coworker-extra-service-name` | string | The coworker extra service name value for this charge |
| `--coworker-time-pass-name` | string | The coworker time pass name value for this charge |
| `--coworker-product-name` | string | The coworker product name value for this charge |
| `--tariff-name` | string | The tariff name value for this charge |
| `--coworker-product-unique-id` | string | ID of the coworker product unique associated with this record |
| `--booking-unique-id` | string | ID of the booking unique associated with this record |
| `--repeat-from` | DateTime | Repeat from date |
| `--repeat-until` | DateTime | Repeat until date |

#### Charge update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--quantity` | int | Number of units |
| `--description` | string | Free-text description of this charge |
| `--invoice-line-display-as` | string | Display text on invoice line |
| `--regular-charge` | bool | Whether this is a regular charge |
| `--discount-amount` | decimal | Discount amount |
| `--credit-amount` | decimal | Credit amount |
| `--due-date` | DateTime | Due date |
| `--total-amount` | decimal | Total amount |
| `--purchase-order` | string | Purchase order |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--invoiced` | bool | Whether the charge has been invoiced |
| `--sale-date` | DateTime | Sale date |
| `--from-team-member` | bool | Whether from team member is enabled |
| `--coworker-extra-service-name` | string | The coworker extra service name value for this charge |
| `--coworker-time-pass-name` | string | The coworker time pass name value for this charge |
| `--coworker-product-name` | string | The coworker product name value for this charge |
| `--tariff-name` | string | The tariff name value for this charge |
| `--coworker-product-unique-id` | string | ID of the coworker product unique associated with this record |
| `--booking-unique-id` | string | ID of the booking unique associated with this record |
| `--repeat-from` | DateTime | Repeat from date |
| `--repeat-until` | DateTime | Repeat until date |

### Charge (key fields)

`Id`, `ChargeNumber`, `Description`, `TotalAmount`, `Invoiced`

<!-- END:GENERATED entity=Charges -->
