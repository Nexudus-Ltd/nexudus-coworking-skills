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

`--coworker-id` (long), `--business-id` (long), `--extra-service-id` (long), `--notes`, `--total-uses` (int), `--from-total-uses` (range), `--to-total-uses` (range), `--free` (bool), `--price` (decimal), `--from-price` (range), `--to-price` (range), `--valid-from` (DateTime), `--from-valid-from` (range), `--to-valid-from` (range), `--expire-date` (DateTime), `--from-expire-date` (range), `--to-expire-date` (range), `--due-date` (DateTime), `--from-due-date` (range), `--to-due-date` (range), `--purchase-order`, `--charge-period` (enum), `--invoice-this-coworker` (bool), `--booking-id` (int), `--from-booking-id` (range), `--to-booking-id` (range), `--booking-from-time` (DateTime), `--from-booking-from-time` (range), `--to-booking-from-time` (range), `--booking-to-time` (DateTime), `--from-booking-to-time` (range), `--to-booking-to-time` (range), `--booking-resource-name`, `--coworker-contract-unique-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerExtraService create options

`--coworker-id` (long, required), `--business-id` (long, required), `--extra-service-id` (long, required), `--notes`, `--total-uses` (int, required), `--free` (bool), `--price` (decimal), `--valid-from` (DateTime), `--expire-date` (DateTime), `--due-date` (DateTime), `--purchase-order`, `--charge-period` (enum, required), `--invoice-this-coworker` (bool), `--booking-id` (int), `--booking-from-time` (DateTime), `--booking-to-time` (DateTime), `--booking-resource-name`, `--coworker-contract-unique-id`

#### CoworkerExtraService update options

`--coworker-id` (long), `--business-id` (long), `--extra-service-id` (long), `--notes`, `--total-uses` (int), `--free` (bool), `--price` (decimal), `--valid-from` (DateTime), `--expire-date` (DateTime), `--due-date` (DateTime), `--purchase-order`, `--charge-period` (enum), `--invoice-this-coworker` (bool), `--booking-id` (int), `--booking-from-time` (DateTime), `--booking-to-time` (DateTime), `--booking-resource-name`, `--coworker-contract-unique-id`

### CoworkerExtraService (key fields)

`Id`, `ExtraServiceName`, `Description`, `RemainingUses`, `Price`, `Invoiced`

<!-- END:GENERATED entity=CoworkerExtraServices -->
