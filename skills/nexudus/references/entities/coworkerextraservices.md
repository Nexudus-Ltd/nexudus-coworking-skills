# CoworkerExtraServices

<!-- BEGIN:GENERATED entity=CoworkerExtraServices -->

A **CoworkerExtraService** records a charge or credit assigned to a customer. It covers three use cases:

- **Booking charges** — charges associated with bookings (e.g., meeting room usage fees). These are linked to a specific booking via `BookingId` and track the resource, time range, and price.
- **Time credit** — booking time allowances for specific resource types. Customers can spend these credits when booking resources of the matching type. The unit of credit depends on the `ChargePeriod` of the linked extra service (minutes, days, uses, etc.). `TotalUses` and `RemainingUses` track the allowance.
- **Printing credit** — credits for printing integrations such as PaperCut or Ezeep. The linked extra service has `IsPrintingCredit = true`. `TotalUses` and `RemainingUses` track the number of print jobs or pages available.

Records can be created manually or added automatically from a plan (tariff). When `IsFromTariff` is `true`, the record was provisioned by a customer's contract (CoworkerContract) and is linked via `CoworkerContractUniqueId`.

CoworkerExtraServices support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerextraservices list --agent` | List all coworkerextraservices |
| `nexudus coworkerextraservices list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerextraservices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerextraservices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerextraservices list --price <value> --agent` | Filter coworkerextraservices by properties |
| `nexudus coworkerextraservices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerextraservices get <id> --agent` | Get single coworkerextraservice |
| `nexudus coworkerextraservices create --coworker-id <value> --business-id <value> --extra-service-id <value> --total-uses <value> --charge-period <value> --agent` | Create coworkerextraservice |
| `nexudus coworkerextraservices update <id> --name "New Name" --agent` | Update coworkerextraservice |
| `nexudus coworkerextraservices delete <id> --yes --agent` | Delete coworkerextraservice (no prompt) |

#### CoworkerExtraService list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long |  |
| `--business-id` | long |  |
| `--extra-service-id` | long |  |
| `--notes` | string | Internal notes |
| `--total-uses` | int | Total credit originally allocated (time or printing). Unit depends on the ChargePeriod of the linked extra service |
| `--from-total-uses` | range | |
| `--to-total-uses` | range | |
| `--free` | bool | Whether this charge or credit is free (no cost to the customer) |
| `--price` | decimal | Price charged for this extra service |
| `--from-price` | range | |
| `--to-price` | range | |
| `--valid-from` | DateTime | Date from which this credit becomes usable |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--expire-date` | DateTime | Date when this credit expires and can no longer be used |
| `--from-expire-date` | range | |
| `--to-expire-date` | range | |
| `--due-date` | DateTime | Payment due date for the charge |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--purchase-order` | string | Purchase order |
| `--charge-period` | enum | Unit of measurement for time credit (Minutes, Days, Weeks, Months, Uses, FourWeekMonths) |
| `--invoice-this-coworker` | bool | Invoice the customer directly instead of the team or company paying member |
| `--booking-id` | int | ID of the booking that generated this charge |
| `--from-booking-id` | range | |
| `--to-booking-id` | range | |
| `--booking-from-time` | DateTime | Start time of the booking that generated this charge |
| `--from-booking-from-time` | range | |
| `--to-booking-from-time` | range | |
| `--booking-to-time` | DateTime | End time of the booking that generated this charge |
| `--from-booking-to-time` | range | |
| `--to-booking-to-time` | range | |
| `--booking-resource-name` | string | Name of the resource booked (e.g., meeting room name) |
| `--coworker-contract-unique-id` | string | Links this credit back to the customer contract that provisioned it |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerExtraService create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required |  |
| `--business-id` | long, required |  |
| `--extra-service-id` | long, required |  |
| `--notes` | string | Internal notes |
| `--total-uses` | int, required | Total credit originally allocated (time or printing). Unit depends on the ChargePeriod of the linked extra service |
| `--free` | bool | Whether this charge or credit is free (no cost to the customer) |
| `--price` | decimal | Price charged for this extra service |
| `--valid-from` | DateTime | Date from which this credit becomes usable |
| `--expire-date` | DateTime | Date when this credit expires and can no longer be used |
| `--due-date` | DateTime | Payment due date for the charge |
| `--purchase-order` | string | Purchase order |
| `--charge-period` | enum, required | Unit of measurement for time credit (Minutes, Days, Weeks, Months, Uses, FourWeekMonths) |
| `--invoice-this-coworker` | bool | Invoice the customer directly instead of the team or company paying member |
| `--booking-id` | int | ID of the booking that generated this charge |
| `--booking-from-time` | DateTime | Start time of the booking that generated this charge |
| `--booking-to-time` | DateTime | End time of the booking that generated this charge |
| `--booking-resource-name` | string | Name of the resource booked (e.g., meeting room name) |
| `--coworker-contract-unique-id` | string | Links this credit back to the customer contract that provisioned it |

#### CoworkerExtraService update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long |  |
| `--business-id` | long |  |
| `--extra-service-id` | long |  |
| `--notes` | string | Internal notes |
| `--total-uses` | int | Total credit originally allocated (time or printing). Unit depends on the ChargePeriod of the linked extra service |
| `--free` | bool | Whether this charge or credit is free (no cost to the customer) |
| `--price` | decimal | Price charged for this extra service |
| `--valid-from` | DateTime | Date from which this credit becomes usable |
| `--expire-date` | DateTime | Date when this credit expires and can no longer be used |
| `--due-date` | DateTime | Payment due date for the charge |
| `--purchase-order` | string | Purchase order |
| `--charge-period` | enum | Unit of measurement for time credit (Minutes, Days, Weeks, Months, Uses, FourWeekMonths) |
| `--invoice-this-coworker` | bool | Invoice the customer directly instead of the team or company paying member |
| `--booking-id` | int | ID of the booking that generated this charge |
| `--booking-from-time` | DateTime | Start time of the booking that generated this charge |
| `--booking-to-time` | DateTime | End time of the booking that generated this charge |
| `--booking-resource-name` | string | Name of the resource booked (e.g., meeting room name) |
| `--coworker-contract-unique-id` | string | Links this credit back to the customer contract that provisioned it |

#### CoworkerExtraService PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkerextraservices update <id> --notes "«PII:BIO:a3f2b1c9»" --agent`

### CoworkerExtraService (key fields)

`Id`, `ExtraServiceName`, `Description`, `RemainingUses`, `Price`, `Invoiced`

<!-- END:GENERATED entity=CoworkerExtraServices -->
