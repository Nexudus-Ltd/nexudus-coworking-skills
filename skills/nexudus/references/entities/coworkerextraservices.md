# CoworkerExtraServices

<!-- BEGIN:GENERATED entity=CoworkerExtraServices -->

A Customer Time Credit (CoworkerExtraService) records a customer's booking time or printing allowance, or a charge generated for a booking; manual credits are used only for matching booking rates while plan, product, and booking records are managed by their source workflow.

CoworkerExtraServices support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerextraservices list --agent` | List all coworkerextraservices |
| `nexudus coworkerextraservices list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerextraservices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerextraservices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerextraservices list --extra-service-name <value> --description <value> --agent` | Filter coworkerextraservices by properties |
| `nexudus coworkerextraservices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerextraservices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerextraservices get <id> --agent` | Get single coworkerextraservice |
| `nexudus coworkerextraservices create --coworker-id <value> --business-id <value> --extra-service-id <value> --total-uses <value> --charge-period <value> --agent` | Create coworkerextraservice |
| `nexudus coworkerextraservices update <id> --name "New Name" --agent` | Update coworkerextraservice |
| `nexudus coworkerextraservices delete <id> --yes --agent` | Delete coworkerextraservice (no prompt) |

#### CoworkerExtraService list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer who owns this time credit or booking charge. |
| `--business-id` | long | ID of the location that issued this record; it is required and cannot be changed after creation. |
| `--extra-service-id` | long | ID of the booking rate that defines this record's eligible resource types, currency, and credit type. |
| `--extra-service-name` | string | Name of the linked extra service |
| `--extra-service-currency-code` | string | Currency code of the linked extra service (e.g., USD, EUR) |
| `--extra-service-is-printing-credit` | bool | True if the linked extra service is a printing credit (PaperCut/Ezeep). False for booking time credit |
| `--description` | string | Read-only description generated for the assigned booking rate or credit. |
| `--notes` | string | Optional internal notes about this time credit or booking charge. |
| `--remaining-uses` | int | Read-only unused credit remaining, in the unit selected by ChargePeriod; it is reduced when the credit is used. |
| `--from-remaining-uses` | range | |
| `--to-remaining-uses` | range | |
| `--total-uses` | int | Total credit granted, in the ChargePeriod unit; it must be at least RemainingUses and is set only when creating a manual credit. |
| `--from-total-uses` | range | |
| `--to-total-uses` | range | |
| `--free` | bool | Whether the record has no charge to the customer; when true, calculated price is zero. |
| `--price` | decimal | Optional monetary amount charged in the booking rate's currency; when omitted, the server calculates it from the rate and TotalUses. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--last-minute-price-adjustment` | decimal | Read-only monetary adjustment calculated for a last-minute booking. |
| `--from-last-minute-price-adjustment` | range | |
| `--to-last-minute-price-adjustment` | range | |
| `--dynamic-price-adjustment` | decimal | Read-only monetary adjustment calculated by demand-based pricing. |
| `--from-dynamic-price-adjustment` | range | |
| `--to-dynamic-price-adjustment` | range | |
| `--price-factor-last-minute` | decimal | Read-only price multiplier calculated for a last-minute booking. |
| `--from-price-factor-last-minute` | range | |
| `--to-price-factor-last-minute` | range | |
| `--price-factor-demand` | decimal | Read-only price multiplier calculated by demand-based pricing. |
| `--from-price-factor-demand` | range | |
| `--to-price-factor-demand` | range | |
| `--valid-from` | DateTime | Optional UTC date and time when credit becomes usable; blank means it can be used immediately. |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--expire-date` | DateTime | Optional UTC expiry date and time; blank means no expiry, and when set it must be after ValidFrom and credit is valid only before it. |
| `--from-expire-date` | range | |
| `--to-expire-date` | range | |
| `--due-date` | DateTime | Optional UTC due date for invoicing this booking charge; blank means it is included on the next invoice. |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--purchase-order` | string | Optional customer purchase-order reference for invoicing. |
| `--charge-period` | enum | Unit used for TotalUses and RemainingUses: Minutes, Days, Weeks, Months, Uses, or FourWeekMonths. |
| `--invoiced` | bool | Whether this booking charge has been added to an invoice; invoiced records have billing update restrictions. |
| `--invoice-date` | DateTime | Read-only UTC date and time when this charge was invoiced. |
| `--from-invoice-date` | range | |
| `--to-invoice-date` | range | |
| `--is-from-tariff` | bool | Whether this credit was automatically provisioned from the customer's plan; plan-provisioned credits cannot be deleted directly. |
| `--booking-unique-id` | string | Internal booking identifier that links a generated booking charge to its source booking; reverse or change the booking instead. |
| `--automatically-added` | bool | Whether the record was created automatically for a booking rather than as a manually assigned credit; automatic records are not eligible credit. |
| `--invoice-this-coworker` | bool | Whether to invoice this customer directly rather than their team or company paying customer. |
| `--discount-code` | string | Read-only discount-code text applied to this charge. |
| `--discount-amount` | decimal | Read-only monetary amount discounted from Price in the booking rate's currency. |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--booking-id` | int | Read-only internal numeric ID of the booking that generated this charge; use the Booking entity instead. |
| `--from-booking-id` | range | |
| `--to-booking-id` | range | |
| `--booking-from-time` | DateTime | Read-only UTC start time copied from the source booking; update the booking instead. |
| `--from-booking-from-time` | range | |
| `--to-booking-from-time` | range | |
| `--booking-to-time` | DateTime | Read-only UTC end time copied from the source booking; update the booking instead. |
| `--from-booking-to-time` | range | |
| `--to-booking-to-time` | range | |
| `--booking-resource-name` | string | Read-only resource name copied from the source booking; update the booking instead. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerExtraService sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerExtraService create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer who owns this time credit or booking charge. |
| `--business-id` | long, required | ID of the location that issued this record; it is required and cannot be changed after creation. |
| `--extra-service-id` | long, required | ID of the booking rate that defines this record's eligible resource types, currency, and credit type. |
| `--notes` | string | Optional internal notes about this time credit or booking charge. |
| `--total-uses` | int, required | Total credit granted, in the ChargePeriod unit; it must be at least RemainingUses and is set only when creating a manual credit. |
| `--free` | bool | Whether the record has no charge to the customer; when true, calculated price is zero. |
| `--price` | decimal | Optional monetary amount charged in the booking rate's currency; when omitted, the server calculates it from the rate and TotalUses. |
| `--valid-from` | DateTime | Optional UTC date and time when credit becomes usable; blank means it can be used immediately. |
| `--expire-date` | DateTime | Optional UTC expiry date and time; blank means no expiry, and when set it must be after ValidFrom and credit is valid only before it. |
| `--due-date` | DateTime | Optional UTC due date for invoicing this booking charge; blank means it is included on the next invoice. |
| `--purchase-order` | string | Optional customer purchase-order reference for invoicing. |
| `--charge-period` | enum, required | Unit used for TotalUses and RemainingUses: Minutes, Days, Weeks, Months, Uses, or FourWeekMonths. |
| `--invoice-this-coworker` | bool | Whether to invoice this customer directly rather than their team or company paying customer. |

#### CoworkerExtraService update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer who owns this time credit or booking charge. |
| `--business-id` | long | ID of the location that issued this record; it is required and cannot be changed after creation. |
| `--extra-service-id` | long | ID of the booking rate that defines this record's eligible resource types, currency, and credit type. |
| `--notes` | string | Optional internal notes about this time credit or booking charge. |
| `--total-uses` | int | Total credit granted, in the ChargePeriod unit; it must be at least RemainingUses and is set only when creating a manual credit. |
| `--free` | bool | Whether the record has no charge to the customer; when true, calculated price is zero. |
| `--price` | decimal | Optional monetary amount charged in the booking rate's currency; when omitted, the server calculates it from the rate and TotalUses. |
| `--valid-from` | DateTime | Optional UTC date and time when credit becomes usable; blank means it can be used immediately. |
| `--expire-date` | DateTime | Optional UTC expiry date and time; blank means no expiry, and when set it must be after ValidFrom and credit is valid only before it. |
| `--due-date` | DateTime | Optional UTC due date for invoicing this booking charge; blank means it is included on the next invoice. |
| `--purchase-order` | string | Optional customer purchase-order reference for invoicing. |
| `--charge-period` | enum | Unit used for TotalUses and RemainingUses: Minutes, Days, Weeks, Months, Uses, or FourWeekMonths. |
| `--invoice-this-coworker` | bool | Whether to invoice this customer directly rather than their team or company paying customer. |

#### CoworkerExtraService PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkerextraservices update <id> --notes "«PII:BIO:a3f2b1c9»" --agent`

### CoworkerExtraService (key fields)

`Id`, `ExtraServiceName`, `Description`, `RemainingUses`, `Price`, `Invoiced`

#### CoworkerExtraService enum values

| Option | Valid values |
| ------ | ------------ |
| `--charge-period` | `1` Minutes, `2` Days, `3` Weeks, `4` Months, `5` Uses, `6` FourWeekMonths |

<!-- END:GENERATED entity=CoworkerExtraServices -->
