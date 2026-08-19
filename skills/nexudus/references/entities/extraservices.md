# ExtraServices

<!-- BEGIN:GENERATED entity=ExtraServices -->

Resource Rates (internally Extra services) are pricing rules for resource types (like meeting rooms) that define how resources are billed, including charge periods, dynamic pricing, and customer restrictions

ExtraServices support Search, Get, Create, Update, Delete.
ExtraServices also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus extraservices list --agent` | List all extraservices |
| `nexudus extraservices list --id <id> --agent` | Filter by single ID |
| `nexudus extraservices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus extraservices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus extraservices list --name <value> --visible <value> --agent` | Filter extraservices by properties |
| `nexudus extraservices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus extraservices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus extraservices get <id> --agent` | Get single extraservice |
| `nexudus extraservices create --business-id <value> --name <value> --display-order <value> --price <value> --charge-period <value> --currency-id <value> --last-minute-adjustment-type <value> --agent` | Create extraservice |
| `nexudus extraservices update <id> --name "New Name" --agent` | Update extraservice |
| `nexudus extraservices delete <id> --yes --agent` | Delete extraservice (no prompt) |
| `nexudus extraservices run-command <key> <ids> --agent` | Run entity command |

#### ExtraService list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this resource rate belongs to |
| `--name` | string | Resource rate name |
| `--description` | string | Optional description of this resource rate |
| `--invoice-display` | string | Custom text shown on invoice lines instead of the resource rate name |
| `--visible` | bool | Whether this resource rate is active and available for resource pricing. Not currently used. |
| `--display-order` | int | Sort position of this resource rate; lower values appear first |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--price` | decimal | Base price in the selected currency per charge period; minute-based rates are prorated as an hourly price |
| `--from-price` | range | |
| `--to-price` | range | |
| `--credit-price` | decimal | Optional alternative price used when the customer pays using time credit; null uses the base price |
| `--from-credit-price` | range | |
| `--to-credit-price` | range | |
| `--charge-period` | enum | Unit used to calculate the booking cost: Minutes, Days, Weeks, Months, Uses, or FourWeekMonths |
| `--maximum-price` | decimal | Optional maximum amount this rate can charge for a booking after length-based calculation |
| `--from-maximum-price` | range | |
| `--to-maximum-price` | range | |
| `--default-price` | bool | Whether this rate is preferred when multiple valid rates match the same resource and charge period |
| `--per-night-pricing` | bool | Whether day-based booking length is calculated by nights rather than elapsed 24-hour periods |
| `--currency-id` | long | ID of the currency used for prices charged by this resource rate |
| `--currency-code` | string | Currency code |
| `--tax-rate-id` | long | ID of the standard tax rate applied to charges; may be required by location settings for rates that are not booking credits |
| `--reduced-tax-rate-id` | long | ID of the reduced tax rate applied when the customer qualifies for reduced taxation |
| `--exempt-tax-rate-id` | long | ID of the tax rate applied when the customer is tax exempt |
| `--financial-account-id` | long | ID of the financial account used to record revenue; may be required by location settings for rates that are not booking credits |
| `--min-length` | int | Optional minimum booking length expressed in the selected charge period |
| `--from-min-length` | range | |
| `--to-min-length` | range | |
| `--max-length` | int | Optional maximum booking length expressed in the selected charge period |
| `--from-max-length` | range | |
| `--to-max-length` | range | |
| `--fixed-cost-length` | int | Optional initial booking duration in minutes charged at FixedCostPrice; requires FixedCostPrice |
| `--from-fixed-cost-length` | range | |
| `--to-fixed-cost-length` | range | |
| `--fixed-cost-price` | decimal | Fixed amount charged for the initial FixedCostLength minutes; requires FixedCostLength |
| `--from-fixed-cost-price` | range | |
| `--to-fixed-cost-price` | range | |
| `--only-for-contacts` | bool | Whether this rate is restricted to contacts without an active contract; cannot be true together with OnlyForMembers |
| `--only-for-members` | bool | Whether this rate is restricted to customers with an active contract; cannot be true together with OnlyForContacts |
| `--booking-credit` | bool | Whether this record defines a time credit type rather than a chargeable resource rate |
| `--printing-credit` | bool | Whether this record defines a printing credit type used by printing integrations |
| `--apply-to-visitors` | bool | Whether the booking charge is multiplied by the number of visitors linked to the booking |
| `--price-factor-low-demand` | decimal | Optional signed percentage adjustment for low demand; for example 10 increases the price by 10% and -10 discounts it by 10%. Overrides the location-wide factor |
| `--from-price-factor-low-demand` | range | |
| `--to-price-factor-low-demand` | range | |
| `--price-factor-average-demand` | decimal | Optional signed percentage adjustment for average demand; for example 10 increases the price by 10% and -10 discounts it by 10%. Overrides the location-wide factor |
| `--from-price-factor-average-demand` | range | |
| `--to-price-factor-average-demand` | range | |
| `--price-factor-high-demand` | decimal | Optional signed percentage adjustment for high demand; for example 10 increases the price by 10% and -10 discounts it by 10%. Overrides the location-wide factor |
| `--from-price-factor-high-demand` | range | |
| `--to-price-factor-high-demand` | range | |
| `--price-factor-last-minute` | decimal | Optional signed percentage adjustment for bookings made within LastMinutePeriodMinutes; negative values discount and positive values increase the price |
| `--from-price-factor-last-minute` | range | |
| `--to-price-factor-last-minute` | range | |
| `--last-minute-period` | int | Number of minutes before a booking starts during which PriceFactorLastMinute applies |
| `--from-last-minute-period` | range | |
| `--to-last-minute-period` | range | |
| `--last-minute-adjustment-type` | enum | How the last-minute adjustment is applied: Fixed applies the full factor throughout the period; Gradual increases it from zero at the period boundary to the full factor near the start time; Disabled turns it off |
| `--apply-from` | DateTime | Optional date and time from which this rate is valid, inclusive |
| `--from-apply-from` | range | |
| `--to-apply-from` | range | |
| `--apply-to` | DateTime | Optional date and time until which this rate is valid, exclusive |
| `--from-apply-to` | range | |
| `--to-apply-to` | range | |
| `--resource-type-names` | string | Read-only resource type names generated from ResourceTypes |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ExtraService sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` ascending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (ascending).

#### ExtraService create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this resource rate belongs to |
| `--name` | string, required | Resource rate name |
| `--description` | string | Optional description of this resource rate |
| `--invoice-display` | string | Custom text shown on invoice lines instead of the resource rate name |
| `--visible` | bool | Whether this resource rate is active and available for resource pricing. Not currently used. |
| `--display-order` | int, required | Sort position of this resource rate; lower values appear first |
| `--resource-types` | list, repeat flag | List of resource types priced by this rate. At least one resource type is required |
| `--added-resource-types` | list, repeat flag | The added resource types value for this extra service |
| `--removed-resource-types` | list, repeat flag | The removed resource types value for this extra service |
| `--price` | decimal, required | Base price in the selected currency per charge period; minute-based rates are prorated as an hourly price |
| `--credit-price` | decimal | Optional alternative price used when the customer pays using time credit; null uses the base price |
| `--charge-period` | enum, required | Unit used to calculate the booking cost: Minutes, Days, Weeks, Months, Uses, or FourWeekMonths |
| `--maximum-price` | decimal | Optional maximum amount this rate can charge for a booking after length-based calculation |
| `--default-price` | bool | Whether this rate is preferred when multiple valid rates match the same resource and charge period |
| `--per-night-pricing` | bool | Whether day-based booking length is calculated by nights rather than elapsed 24-hour periods |
| `--currency-id` | long, required | ID of the currency used for prices charged by this resource rate |
| `--tax-rate-id` | long | ID of the standard tax rate applied to charges; may be required by location settings for rates that are not booking credits |
| `--reduced-tax-rate-id` | long | ID of the reduced tax rate applied when the customer qualifies for reduced taxation |
| `--exempt-tax-rate-id` | long | ID of the tax rate applied when the customer is tax exempt |
| `--financial-account-id` | long | ID of the financial account used to record revenue; may be required by location settings for rates that are not booking credits |
| `--min-length` | int | Optional minimum booking length expressed in the selected charge period |
| `--max-length` | int | Optional maximum booking length expressed in the selected charge period |
| `--fixed-cost-length` | int | Optional initial booking duration in minutes charged at FixedCostPrice; requires FixedCostPrice |
| `--fixed-cost-price` | decimal | Fixed amount charged for the initial FixedCostLength minutes; requires FixedCostLength |
| `--tariffs` | list, repeat flag | List of plans whose active members can use this rate; empty means no plan restriction |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this extra service |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this extra service |
| `--only-for-contacts` | bool | Whether this rate is restricted to contacts without an active contract; cannot be true together with OnlyForMembers |
| `--only-for-members` | bool | Whether this rate is restricted to customers with an active contract; cannot be true together with OnlyForContacts |
| `--booking-credit` | bool | Whether this record defines a time credit type rather than a chargeable resource rate |
| `--printing-credit` | bool | Whether this record defines a printing credit type used by printing integrations |
| `--apply-to-visitors` | bool | Whether the booking charge is multiplied by the number of visitors linked to the booking |
| `--price-factor-low-demand` | decimal | Optional signed percentage adjustment for low demand; for example 10 increases the price by 10% and -10 discounts it by 10%. Overrides the location-wide factor |
| `--price-factor-average-demand` | decimal | Optional signed percentage adjustment for average demand; for example 10 increases the price by 10% and -10 discounts it by 10%. Overrides the location-wide factor |
| `--price-factor-high-demand` | decimal | Optional signed percentage adjustment for high demand; for example 10 increases the price by 10% and -10 discounts it by 10%. Overrides the location-wide factor |
| `--price-factor-last-minute` | decimal | Optional signed percentage adjustment for bookings made within LastMinutePeriodMinutes; negative values discount and positive values increase the price |
| `--last-minute-period` | int | Number of minutes before a booking starts during which PriceFactorLastMinute applies |
| `--last-minute-adjustment-type` | enum, required | How the last-minute adjustment is applied: Fixed applies the full factor throughout the period; Gradual increases it from zero at the period boundary to the full factor near the start time; Disabled turns it off |
| `--apply-from` | DateTime | Optional date and time from which this rate is valid, inclusive |
| `--apply-to` | DateTime | Optional date and time until which this rate is valid, exclusive |
| `--teams` | list, repeat flag | List of teams whose customers can use this rate; empty means no team restriction |
| `--added-teams` | list, repeat flag | The added teams value for this extra service |
| `--removed-teams` | list, repeat flag | The removed teams value for this extra service |
| `--time-slots` | JSON array or @filepath | The days and times this extra service price is available for booking. The year, month and day component of FromTime/ToTime is always 1976-01-01. |

#### ExtraService update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this resource rate belongs to |
| `--name` | string | Resource rate name |
| `--description` | string | Optional description of this resource rate |
| `--invoice-display` | string | Custom text shown on invoice lines instead of the resource rate name |
| `--visible` | bool | Whether this resource rate is active and available for resource pricing. Not currently used. |
| `--display-order` | int | Sort position of this resource rate; lower values appear first |
| `--resource-types` | list, repeat flag | List of resource types priced by this rate. At least one resource type is required |
| `--added-resource-types` | list, repeat flag | The added resource types value for this extra service |
| `--removed-resource-types` | list, repeat flag | The removed resource types value for this extra service |
| `--price` | decimal | Base price in the selected currency per charge period; minute-based rates are prorated as an hourly price |
| `--credit-price` | decimal | Optional alternative price used when the customer pays using time credit; null uses the base price |
| `--charge-period` | enum | Unit used to calculate the booking cost: Minutes, Days, Weeks, Months, Uses, or FourWeekMonths |
| `--maximum-price` | decimal | Optional maximum amount this rate can charge for a booking after length-based calculation |
| `--default-price` | bool | Whether this rate is preferred when multiple valid rates match the same resource and charge period |
| `--per-night-pricing` | bool | Whether day-based booking length is calculated by nights rather than elapsed 24-hour periods |
| `--currency-id` | long | ID of the currency used for prices charged by this resource rate |
| `--tax-rate-id` | long | ID of the standard tax rate applied to charges; may be required by location settings for rates that are not booking credits |
| `--reduced-tax-rate-id` | long | ID of the reduced tax rate applied when the customer qualifies for reduced taxation |
| `--exempt-tax-rate-id` | long | ID of the tax rate applied when the customer is tax exempt |
| `--financial-account-id` | long | ID of the financial account used to record revenue; may be required by location settings for rates that are not booking credits |
| `--min-length` | int | Optional minimum booking length expressed in the selected charge period |
| `--max-length` | int | Optional maximum booking length expressed in the selected charge period |
| `--fixed-cost-length` | int | Optional initial booking duration in minutes charged at FixedCostPrice; requires FixedCostPrice |
| `--fixed-cost-price` | decimal | Fixed amount charged for the initial FixedCostLength minutes; requires FixedCostLength |
| `--tariffs` | list, repeat flag | List of plans whose active members can use this rate; empty means no plan restriction |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this extra service |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this extra service |
| `--only-for-contacts` | bool | Whether this rate is restricted to contacts without an active contract; cannot be true together with OnlyForMembers |
| `--only-for-members` | bool | Whether this rate is restricted to customers with an active contract; cannot be true together with OnlyForContacts |
| `--booking-credit` | bool | Whether this record defines a time credit type rather than a chargeable resource rate |
| `--printing-credit` | bool | Whether this record defines a printing credit type used by printing integrations |
| `--apply-to-visitors` | bool | Whether the booking charge is multiplied by the number of visitors linked to the booking |
| `--price-factor-low-demand` | decimal | Optional signed percentage adjustment for low demand; for example 10 increases the price by 10% and -10 discounts it by 10%. Overrides the location-wide factor |
| `--price-factor-average-demand` | decimal | Optional signed percentage adjustment for average demand; for example 10 increases the price by 10% and -10 discounts it by 10%. Overrides the location-wide factor |
| `--price-factor-high-demand` | decimal | Optional signed percentage adjustment for high demand; for example 10 increases the price by 10% and -10 discounts it by 10%. Overrides the location-wide factor |
| `--price-factor-last-minute` | decimal | Optional signed percentage adjustment for bookings made within LastMinutePeriodMinutes; negative values discount and positive values increase the price |
| `--last-minute-period` | int | Number of minutes before a booking starts during which PriceFactorLastMinute applies |
| `--last-minute-adjustment-type` | enum | How the last-minute adjustment is applied: Fixed applies the full factor throughout the period; Gradual increases it from zero at the period boundary to the full factor near the start time; Disabled turns it off |
| `--apply-from` | DateTime | Optional date and time from which this rate is valid, inclusive |
| `--apply-to` | DateTime | Optional date and time until which this rate is valid, exclusive |
| `--teams` | list, repeat flag | List of teams whose customers can use this rate; empty means no team restriction |
| `--added-teams` | list, repeat flag | The added teams value for this extra service |
| `--removed-teams` | list, repeat flag | The removed teams value for this extra service |
| `--time-slots` | JSON array or @filepath | The days and times this extra service price is available for booking. The year, month and day component of FromTime/ToTime is always 1976-01-01. |

### ExtraService (key fields)

`Id`, `Name`, `Visible`, `Price`, `ChargePeriod`, `IsDefaultPrice`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `ResourceTypeNames`

**List properties (only returned by `get`, not by `list`):** `ResourceTypes`, `AddedResourceTypes`, `RemovedResourceTypes`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Teams`, `AddedTeams`, `RemovedTeams`

#### ExtraService inline children

ExtraService supports inline child objects on create and update. Pass a JSON array or a `@filepath` reference.

**`--time-slots`** — The days and times this extra service price is available for booking. The year, month and day component of FromTime/ToTime is always 1976-01-01.

Writable properties: `DayOfWeek`, `FromTime`, `ToTime`, `Available`

```shell
nexudus extraservices create ... --time-slots '[{"DayOfWeek": "...", "FromTime": "...", "ToTime": "...", "Available": true}]' --agent
```

Or from a file:

```shell
nexudus extraservices create ... --time-slots @timeslots.json --agent
```

#### ExtraService enum values

| Option | Valid values |
| ------ | ------------ |
| `--charge-period` | `1` Minutes, `2` Days, `3` Weeks, `4` Months, `5` Uses, `6` FourWeekMonths |
| `--last-minute-adjustment-type` | `1` Disabled, `2` Fixed, `3` Gradual |

<!-- END:GENERATED entity=ExtraServices -->
