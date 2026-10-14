# CoworkerExtraServiceUseHistories

<!-- BEGIN:GENERATED entity=CoworkerExtraServiceUseHistories -->

A read-only ledger entry recording credit deducted from a customer's time credit or printing credit. Each entry links the credit to the booking that spent it, or has no booking when printing, an integration or a manual adjustment used it. Cancelling or changing a booking returns the credit and removes its entries. Use it to answer how much credit a customer or team used, when and on what.

CoworkerExtraServiceUseHistories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerextraserviceusehistories list --agent` | List all coworkerextraserviceusehistories |
| `nexudus coworkerextraserviceusehistories list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerextraserviceusehistories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerextraserviceusehistories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerextraserviceusehistories list --booking-from-time <value> --booking-resource-name <value> --agent` | Filter coworkerextraserviceusehistories by properties |
| `nexudus coworkerextraserviceusehistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerextraserviceusehistories list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerextraserviceusehistories get <id> --agent` | Get single coworkerextraserviceusehistory |
| `nexudus coworkerextraserviceusehistories create --coworker-extra-service-id <value> --agent` | Create coworkerextraserviceusehistory |
| `nexudus coworkerextraserviceusehistories update <id> --name "New Name" --agent` | Update coworkerextraserviceusehistory |
| `nexudus coworkerextraserviceusehistories delete <id> --yes --agent` | Delete coworkerextraserviceusehistory (no prompt) |

#### CoworkerExtraServiceUseHistory list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-extra-service-id` | long | ID of the customer time credit or printing credit this usage was deducted from |
| `--coworker-extra-service-coworker-id` | int | Display value for CoworkerExtraService.Coworker.Id. |
| `--from-coworker-extra-service-coworker-id` | range | |
| `--to-coworker-extra-service-coworker-id` | range | |
| `--coworker-extra-service-coworker-full-name` | string | Display value for CoworkerExtraService.Coworker.FullName. |
| `--coworker-extra-service-extra-service-is-printing-credit` | bool | Display value for CoworkerExtraService.ExtraService.IsPrintingCredit. |
| `--coworker-extra-service-extra-service-name` | string | Display value for CoworkerExtraService.ExtraService.Name. |
| `--coworker-extra-service-expire-date` | DateTime | Display value for CoworkerExtraService.ExpireDate. |
| `--from-coworker-extra-service-expire-date` | range | |
| `--to-coworker-extra-service-expire-date` | range | |
| `--coworker-extra-service-remaining-uses` | int | Display value for CoworkerExtraService.RemainingUses. |
| `--from-coworker-extra-service-remaining-uses` | range | |
| `--to-coworker-extra-service-remaining-uses` | range | |
| `--coworker-extra-service-total-uses` | int | Display value for CoworkerExtraService.TotalUses. |
| `--from-coworker-extra-service-total-uses` | range | |
| `--to-coworker-extra-service-total-uses` | range | |
| `--coworker-extra-service-charge-period` | string | Display value for CoworkerExtraService.ChargePeriod. |
| `--coworker-extra-service-is-from-tariff` | bool | Display value for CoworkerExtraService.IsFromTariff. |
| `--coworker-extra-service-coworker-product-unique-id` | string | Display value for CoworkerExtraService.CoworkerProductUniqueId. |
| `--booking-id` | long | ID of the booking that consumed the credit; empty when the credit was used without a booking (printing, an integration or a manual adjustment) |
| `--booking-from-time` | DateTime | Display value for Booking.FromTime. |
| `--from-booking-from-time` | range | |
| `--to-booking-from-time` | range | |
| `--booking-to-time` | DateTime | Display value for Booking.ToTime. |
| `--from-booking-to-time` | range | |
| `--to-booking-to-time` | range | |
| `--booking-resource-name` | string | Display value for Booking.Resource.Name. |
| `--booking-coworker-full-name` | string | Display value for Booking.Coworker.FullName. |
| `--credit-used` | int | Amount of credit consumed, in the credit's ChargePeriod unit (minutes, days, weeks, months or uses; cents for printing credit). Empty on legacy records |
| `--from-credit-used` | range | |
| `--to-credit-used` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerExtraServiceUseHistory sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerExtraServiceUseHistory create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-extra-service-id` | long, required | ID of the customer time credit or printing credit this usage was deducted from |
| `--booking-id` | long | ID of the booking that consumed the credit; empty when the credit was used without a booking (printing, an integration or a manual adjustment) |

#### CoworkerExtraServiceUseHistory update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-extra-service-id` | long | ID of the customer time credit or printing credit this usage was deducted from |
| `--booking-id` | long | ID of the booking that consumed the credit; empty when the credit was used without a booking (printing, an integration or a manual adjustment) |

#### CoworkerExtraServiceUseHistory PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-extra-service-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--booking-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coworkerextraserviceusehistories update <id> --coworker-extra-service-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerExtraServiceUseHistory (key fields)

`Id`, `BookingFromTime`, `BookingResourceName`, `CreditUsed`

<!-- END:GENERATED entity=CoworkerExtraServiceUseHistories -->
