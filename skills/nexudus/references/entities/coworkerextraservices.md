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
| `nexudus coworkerextraservices create --coworker-id <value> --business-id <value> --extra-service-id <value> --total-uses <value> --agent` | Create coworkerextraservice |
| `nexudus coworkerextraservices update <id> --name "New Name" --agent` | Update coworkerextraservice |
| `nexudus coworkerextraservices delete <id> --yes --agent` | Delete coworkerextraservice (no prompt) |

#### CoworkerExtraService list filter options

`--coworker-id`, `--business-id`, `--extra-service-id`, `--notes`, `--total-uses`, `--from-total-uses` (range), `--to-total-uses` (range), `--free`, `--price`, `--from-price` (range), `--to-price` (range), `--valid-from`, `--from-valid-from` (range), `--to-valid-from` (range), `--expire-date`, `--from-expire-date` (range), `--to-expire-date` (range), `--due-date`, `--from-due-date` (range), `--to-due-date` (range), `--purchase-order`, `--charge-period`, `--invoice-this-coworker`, `--booking-id`, `--from-booking-id` (range), `--to-booking-id` (range), `--booking-from-time`, `--from-booking-from-time` (range), `--to-booking-from-time` (range), `--booking-to-time`, `--from-booking-to-time` (range), `--to-booking-to-time` (range), `--booking-resource-name`, `--coworker-contract-unique-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerExtraService create options

`--coworker-id` (required), `--business-id` (required), `--extra-service-id` (required), `--notes`, `--total-uses` (required), `--free`, `--price`, `--valid-from`, `--expire-date`, `--due-date`, `--purchase-order`, `--charge-period`, `--invoice-this-coworker`, `--booking-id`, `--booking-from-time`, `--booking-to-time`, `--booking-resource-name`, `--coworker-contract-unique-id`

#### CoworkerExtraService update options

`--coworker-id`, `--business-id`, `--extra-service-id`, `--notes`, `--total-uses`, `--free`, `--price`, `--valid-from`, `--expire-date`, `--due-date`, `--purchase-order`, `--charge-period`, `--invoice-this-coworker`, `--booking-id`, `--booking-from-time`, `--booking-to-time`, `--booking-resource-name`, `--coworker-contract-unique-id`

### CoworkerExtraService (key fields)

`Id`, `ExtraServiceName`, `Description`, `RemainingUses`, `Price`, `Invoiced`

<!-- END:GENERATED entity=CoworkerExtraServices -->
