# Bookings

<!-- BEGIN:GENERATED entity=Bookings -->

A booking is a reservation of a resource, such as a meeting room or desk, for a customer at a specified time; it can be tentative, recurring, charged, and invoiced.

Bookings support Search, Get, Create, Update, Delete.
Bookings also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus bookings list --agent` | List all bookings |
| `nexudus bookings list --id <id> --agent` | Filter by single ID |
| `nexudus bookings list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus bookings list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus bookings list --resource-name <value> --coworker-full-name <value> --agent` | Filter bookings by properties |
| `nexudus bookings list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus bookings list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus bookings get <id> --agent` | Get single booking |
| `nexudus bookings create --resource-id <value> --from-time <value> --to-time <value> --repeats <value> --which-bookings-to-update <value> --agent` | Create booking |
| `nexudus bookings update <id> --name "New Name" --agent` | Update booking |
| `nexudus bookings delete <id> --yes --agent` | Delete booking (no prompt) |
| `nexudus bookings run-command <key> <ids> --agent` | Run entity command |

#### Booking list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource being reserved; it determines the booking location and availability rules. |
| `--resource-name` | string | Resource name |
| `--resource-allocation` | int | Resource allocation |
| `--from-resource-allocation` | range | |
| `--to-resource-allocation` | range | |
| `--resource-hide-in-calendar` | bool | Resource hidden in calendar |
| `--resource-no-return-policy` | int | The resource no return policy value for this booking |
| `--from-resource-no-return-policy` | range | |
| `--to-resource-no-return-policy` | range | |
| `--resource-no-return-policy-all-resources` | int | The resource no return policy all resources value for this booking |
| `--from-resource-no-return-policy-all-resources` | range | |
| `--to-resource-no-return-policy-all-resources` | range | |
| `--resource-no-return-policy-all-users` | int | The resource no return policy all users value for this booking |
| `--from-resource-no-return-policy-all-users` | range | |
| `--to-resource-no-return-policy-all-users` | range | |
| `--resource-resource-type-id` | int | Resource type ID |
| `--from-resource-resource-type-id` | range | |
| `--to-resource-resource-type-id` | range | |
| `--resource-resource-type-name` | string | Resource type name |
| `--floor-plan-desk-id` | long | Optional ID of the floor-plan unit assigned within the selected resource. The unit must be connected to this resource |
| `--floor-plan-desk-name` | string | Floor plan desk name |
| `--coworker-id` | long | Optional ID of the customer this booking is for. |
| `--coworker-coworker-type` | string | The coworker coworker type value for this booking |
| `--coworker-full-name` | string | Coworker full name |
| `--coworker-mobile-phone` | string | The coworker mobile phone value for this booking |
| `--coworker-land-line` | string | The coworker land line value for this booking |
| `--coworker-billing-name` | string | Coworker billing name |
| `--coworker-company-name` | string | Coworker company name |
| `--coworker-team-names` | string | Coworker team names |
| `--extra-service-id` | long | Optional ID of the rate used to price this booking. Set it only to a rate linked to the selected resource's ResourceType. When no rate is provided, the system calculates an applicable rate automatically. |
| `--extra-service-name` | string | Extra service name |
| `--from-time` | DateTime | Booking start date and time in UTC. |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | Booking end date and time in UTC; it must be after FromTime. |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--notes` | string | Customer-facing notes for the booking. |
| `--internal-notes` | string | Internal staff notes recorded when the booking is created. |
| `--charge-now` | bool | Whether to charge the booking immediately when it is created or updated. |
| `--invoice-now` | bool | Whether to generate an invoice for the booking immediately. |
| `--invoice-this-coworker` | bool | Whether the selected customer receives the booking charge. When false, the customer's team-paying member, if any, is the billing party. |
| `--do-not-use-booking-credit` | bool | Whether to prevent available customer booking credit from being used for this booking. |
| `--purchase-order` | string | Optional customer purchase-order reference for the booking. |
| `--discount-code` | string | Optional discount code applied when the booking price is calculated. |
| `--tentative` | bool | Whether the booking is tentative and still requires confirmation. Customer bookings for resources requiring confirmation are created as tentative; administrators can create tentative bookings for any resource. |
| `--online` | bool | Whether this is an online booking, as determined by the selected resource. |
| `--teams-at-booking` | string | System snapshot of the customer's team memberships when the booking was made. |
| `--tariff-at-booking` | string | System snapshot of the customer's plan when the booking was made. |
| `--repeat-series-unique-id` | string | System-generated identifier linking all bookings in the same recurrence series; use it to find and update all bookings in that series. |
| `--repeat-booking` | bool | Whether to create a recurring series from this booking. |
| `--repeats` | enum | Recurrence cycle: Daily, Weekly, Monthly, Yearly, FirstOfMonth, SecondOfMonth, ThirdOfMonth, FourthOfMonth, or LastOfMonth. |
| `--which-bookings-to-update` | enum | For a recurring booking update, selects whether to update this booking, future bookings, all bookings, not-charged bookings, or perform the corresponding delete or charge-reversal action. |
| `--repeat-every` | int | Optional positive recurrence interval; for example, 2 with Weekly repeats every two weeks. |
| `--from-repeat-every` | range | |
| `--to-repeat-every` | range | |
| `--repeat-until` | DateTime | Optional final UTC date and time for creating occurrences in the recurrence series. |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--repeat-on-mondays` | bool | Whether a weekly recurring booking includes Mondays. |
| `--repeat-on-tuesdays` | bool | Whether a weekly recurring booking includes Tuesdays. |
| `--repeat-on-wednesdays` | bool | Whether a weekly recurring booking includes Wednesdays. |
| `--repeat-on-thursdays` | bool | Whether a weekly recurring booking includes Thursdays. |
| `--repeat-on-fridays` | bool | Whether a weekly recurring booking includes Fridays. |
| `--repeat-on-saturdays` | bool | Whether a weekly recurring booking includes Saturdays. |
| `--repeat-on-sundays` | bool | Whether a weekly recurring booking includes Sundays. |
| `--override-price` | decimal | Optional total price override for this booking, before normal rate calculation. |
| `--from-override-price` | range | |
| `--to-override-price` | range | |
| `--invoiced` | bool | Whether the booking price has been calculated and posted to the customer's account as a CoworkerExtraService and, when applicable, CoworkerProducts. This does not indicate whether the booking has been invoiced. |
| `--invoice-date` | DateTime | UTC date and time when the booking was charged. |
| `--from-invoice-date` | range | |
| `--to-invoice-date` | range | |
| `--booking-number` | int | System-generated booking reference number. |
| `--from-booking-number` | range | |
| `--to-booking-number` | range | |
| `--coworker-invoice-id` | int | System-maintained ID of the invoice associated with this booking; manage invoices through the invoice entity. |
| `--from-coworker-invoice-id` | range | |
| `--to-coworker-invoice-id` | range | |
| `--coworker-invoice-number` | string | System-maintained invoice number associated with this booking, populated when the booking is included in an invoice. |
| `--coworker-invoice-paid` | bool | Read-only indicator that the associated invoice has been paid, populated when the booking is included in an invoice. |
| `--coworker-invoice-draft` | bool | Read-only indicator that the associated invoice is still a draft, populated when the booking is included in an invoice. |
| `--coworker-invoice-void` | bool | Read-only indicator that the associated invoice has been voided, populated when the booking is included in an invoice. |
| `--coworker-invoice-credit-note` | bool | Read-only indicator that the associated invoice is a credit note, populated when the booking is included in an invoice. |
| `--include-zoom-invite` | bool | Whether to include a Zoom meeting invitation for this booking. |
| `--checked-in-at` | DateTime | UTC date and time when the booking was checked in through the booking workflow. |
| `--from-checked-in-at` | range | |
| `--to-checked-in-at` | range | |
| `--cancel-if-not-paid` | bool | System-derived resource policy that cancels this booking when payment is not received. |
| `--cancel-if-not-checked-in` | bool | System-derived resource policy that cancels this booking when no check-in occurs. |
| `--max-occupancy` | int | Maximum occupancy detected by sensors in the selected resource during this booking. |
| `--from-max-occupancy` | range | |
| `--to-max-occupancy` | range | |
| `--last-minute-price-adjustment` | decimal | System-calculated monetary adjustment from the dynamic-pricing settings for the selected resource or location, applied for a last-minute booking. |
| `--from-last-minute-price-adjustment` | range | |
| `--to-last-minute-price-adjustment` | range | |
| `--dynamic-price-adjustment` | decimal | System-calculated monetary adjustment from the dynamic-pricing settings for the selected resource or location. |
| `--from-dynamic-price-adjustment` | range | |
| `--to-dynamic-price-adjustment` | range | |
| `--price-factor-last-minute` | decimal | System-calculated multiplier from the dynamic-pricing settings for the selected resource or location, used for the last-minute price adjustment. |
| `--from-price-factor-last-minute` | range | |
| `--to-price-factor-last-minute` | range | |
| `--price-factor-demand` | decimal | System-calculated multiplier from the dynamic-pricing settings for the selected resource or location, used for demand-based dynamic pricing. |
| `--from-price-factor-demand` | range | |
| `--to-price-factor-demand` | range | |
| `--coworker-checked-in-at` | DateTime | UTC date and time when the customer checked in for this booking. |
| `--from-coworker-checked-in-at` | range | |
| `--to-coworker-checked-in-at` | range | |
| `--coworker-checked-out-at` | DateTime | UTC date and time when the customer checked out from this booking. |
| `--from-coworker-checked-out-at` | range | |
| `--to-coworker-checked-out-at` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Booking sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `FromTime` ascending. If no `--order-by` is specified, the API returns results ordered by `FromTime` (ascending).

#### Booking create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required | ID of the resource being reserved; it determines the booking location and availability rules. |
| `--floor-plan-desk-id` | long | Optional ID of the floor-plan unit assigned within the selected resource. The unit must be connected to this resource |
| `--coworker-id` | long | Optional ID of the customer this booking is for. |
| `--extra-service-id` | long | Optional ID of the rate used to price this booking. Set it only to a rate linked to the selected resource's ResourceType. When no rate is provided, the system calculates an applicable rate automatically. |
| `--from-time` | DateTime, required | Booking start date and time in UTC. |
| `--to-time` | DateTime, required | Booking end date and time in UTC; it must be after FromTime. |
| `--notes` | string | Customer-facing notes for the booking. |
| `--internal-notes` | string | Internal staff notes recorded when the booking is created. |
| `--charge-now` | bool | Whether to charge the booking immediately when it is created or updated. |
| `--invoice-now` | bool | Whether to generate an invoice for the booking immediately. |
| `--invoice-this-coworker` | bool | Whether the selected customer receives the booking charge. When false, the customer's team-paying member, if any, is the billing party. |
| `--do-not-use-booking-credit` | bool | Whether to prevent available customer booking credit from being used for this booking. |
| `--purchase-order` | string | Optional customer purchase-order reference for the booking. |
| `--discount-code` | string | Optional discount code applied when the booking price is calculated. |
| `--tentative` | bool | Whether the booking is tentative and still requires confirmation. Customer bookings for resources requiring confirmation are created as tentative; administrators can create tentative bookings for any resource. |
| `--teams-at-booking` | string | System snapshot of the customer's team memberships when the booking was made. |
| `--tariff-at-booking` | string | System snapshot of the customer's plan when the booking was made. |
| `--repeat-series-unique-id` | string | System-generated identifier linking all bookings in the same recurrence series; use it to find and update all bookings in that series. |
| `--repeat-booking` | bool | Whether to create a recurring series from this booking. |
| `--repeats` | enum, required | Recurrence cycle: Daily, Weekly, Monthly, Yearly, FirstOfMonth, SecondOfMonth, ThirdOfMonth, FourthOfMonth, or LastOfMonth. |
| `--which-bookings-to-update` | enum, required | For a recurring booking update, selects whether to update this booking, future bookings, all bookings, not-charged bookings, or perform the corresponding delete or charge-reversal action. |
| `--repeat-every` | int | Optional positive recurrence interval; for example, 2 with Weekly repeats every two weeks. |
| `--repeat-until` | DateTime | Optional final UTC date and time for creating occurrences in the recurrence series. |
| `--repeat-on-mondays` | bool | Whether a weekly recurring booking includes Mondays. |
| `--repeat-on-tuesdays` | bool | Whether a weekly recurring booking includes Tuesdays. |
| `--repeat-on-wednesdays` | bool | Whether a weekly recurring booking includes Wednesdays. |
| `--repeat-on-thursdays` | bool | Whether a weekly recurring booking includes Thursdays. |
| `--repeat-on-fridays` | bool | Whether a weekly recurring booking includes Fridays. |
| `--repeat-on-saturdays` | bool | Whether a weekly recurring booking includes Saturdays. |
| `--repeat-on-sundays` | bool | Whether a weekly recurring booking includes Sundays. |
| `--override-price` | decimal | Optional total price override for this booking, before normal rate calculation. |
| `--include-zoom-invite` | bool | Whether to include a Zoom meeting invitation for this booking. |
| `--coworker-checked-in-at` | DateTime | UTC date and time when the customer checked in for this booking. |
| `--coworker-checked-out-at` | DateTime | UTC date and time when the customer checked out from this booking. |
| `--booking-products` | JSON array or @filepath | Products to include with this booking |
| `--booking-visitors` | JSON array or @filepath | Visitors to add to this booking |

#### Booking update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource being reserved; it determines the booking location and availability rules. |
| `--floor-plan-desk-id` | long | Optional ID of the floor-plan unit assigned within the selected resource. The unit must be connected to this resource |
| `--coworker-id` | long | Optional ID of the customer this booking is for. |
| `--extra-service-id` | long | Optional ID of the rate used to price this booking. Set it only to a rate linked to the selected resource's ResourceType. When no rate is provided, the system calculates an applicable rate automatically. |
| `--from-time` | DateTime | Booking start date and time in UTC. |
| `--to-time` | DateTime | Booking end date and time in UTC; it must be after FromTime. |
| `--notes` | string | Customer-facing notes for the booking. |
| `--charge-now` | bool | Whether to charge the booking immediately when it is created or updated. |
| `--invoice-now` | bool | Whether to generate an invoice for the booking immediately. |
| `--invoice-this-coworker` | bool | Whether the selected customer receives the booking charge. When false, the customer's team-paying member, if any, is the billing party. |
| `--do-not-use-booking-credit` | bool | Whether to prevent available customer booking credit from being used for this booking. |
| `--purchase-order` | string | Optional customer purchase-order reference for the booking. |
| `--discount-code` | string | Optional discount code applied when the booking price is calculated. |
| `--tentative` | bool | Whether the booking is tentative and still requires confirmation. Customer bookings for resources requiring confirmation are created as tentative; administrators can create tentative bookings for any resource. |
| `--teams-at-booking` | string | System snapshot of the customer's team memberships when the booking was made. |
| `--tariff-at-booking` | string | System snapshot of the customer's plan when the booking was made. |
| `--which-bookings-to-update` | enum | For a recurring booking update, selects whether to update this booking, future bookings, all bookings, not-charged bookings, or perform the corresponding delete or charge-reversal action. |
| `--override-price` | decimal | Optional total price override for this booking, before normal rate calculation. |
| `--include-zoom-invite` | bool | Whether to include a Zoom meeting invitation for this booking. |
| `--coworker-checked-in-at` | DateTime | UTC date and time when the customer checked in for this booking. |
| `--coworker-checked-out-at` | DateTime | UTC date and time when the customer checked out from this booking. |
| `--booking-products` | JSON array or @filepath | Products to include with this booking |
| `--booking-visitors` | JSON array or @filepath | Visitors to add to this booking |

#### Booking PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-mobile-phone` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--coworker-land-line` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus bookings update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### Booking (key fields)

`Id`, `ResourceName`, `CoworkerFullName`, `FromTime`, `ToTime`, `Tentative`, `Invoiced`

#### Booking inline children

Booking supports inline child objects on create and update. Pass a JSON array or a `@filepath` reference.

**`--booking-products`** — Products to include with this booking

Writable properties: `ProductId`, `Quantity`, `InvoiceInMinutes`

```shell
nexudus bookings create ... --booking-products '[{"ProductId": 123, "Quantity": 123, "InvoiceInMinutes": true}]' --agent
```

Or from a file:

```shell
nexudus bookings create ... --booking-products @bookingproducts.json --agent
```

**`--booking-visitors`** — Visitors to add to this booking

Writable properties: `VisitorFullName`, `VisitorEmail`

```shell
nexudus bookings create ... --booking-visitors '[{"VisitorFullName": "...", "VisitorEmail": "..."}]' --agent
```

Or from a file:

```shell
nexudus bookings create ... --booking-visitors @bookingvisitors.json --agent
```

#### Booking enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeats` | `1` Daily, `2` Weekly, `3` Monthly, `4` Yearly, `5` FirstOfMonth, `6` SecondOfMonth, `7` ThirdOfMonth, `8` LastOfMonth, `9` FourthOfMonth |
| `--which-bookings-to-update` | `1` UpdateThisBookingOnly, `2` UpdateFutureBookingsOnly, `3` UpdateAllBookings, `4` UpdateNotChargedBookings, `5` DeleteAllBookings, `6` DeleteBookingsAfterThis, `7` DeleteNotChargedBookings, `8` RevertAllCharges |

<!-- END:GENERATED entity=Bookings -->
