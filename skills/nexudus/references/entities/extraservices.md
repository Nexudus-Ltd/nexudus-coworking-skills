# ExtraServices

<!-- BEGIN:GENERATED entity=ExtraServices -->

An **ExtraService** serves two distinct purposes:

1. **Resource-type pricing rule** — defines how one or more resource types are billed. A single resource type can have multiple extra services — for example, one per charge period (hourly, half-day, full-day) or one per customer segment.
2. **Printing credit** — when `IsPrintingCredit` is `true`, the extra service represents a printing allowance rather than booking time. In this case `ChargePeriod` must always be `5` (Uses) and `Price` should be set to `1`.


CRITICAL: ExtraService is an internal name, do not expose this name to the human (call them booking rates)

Restrictions available on each extra service include:

- **Charge period** — hourly, daily, etc. (`--charge-period`). For printing credit, always use `5` (Uses).
- **Customer type** — members only (`--only-for-members`) or contacts only (`--only-for-contacts`)
- **Time window** — bookings must fall within specific hours (`--from-time`, `--to-time`)
- **Booking length** — minimum/maximum duration (`--min-length`, `--max-length`)
- **Fixed-cost slot** — charge a flat fee for bookings up to a fixed length (`--fixed-cost-length`, `--fixed-cost-price`)
- **Dynamic pricing** — price factors for low/average/high demand and last-minute bookings
- **Date range** — apply only between specific dates (`--apply-from`, `--apply-to`)

To set up pricing for a resource type, create one `ExtraService` per pricing rule and associate it with the desired resource type(s) using or the resource types assignment. The `ResourceTypeNames` field on an extra service shows which resource types it currently applies to.

To create a **printing credit** extra service, set `--printing-credit true`, `--charge-period 5`, and `--price 1`. Resource type assignment is not required for printing credit extra services.

### Setting up hourly pricing

For hourly pricing, set `--charge-period 1` (Minutes) and `--price` to the cost of 60 minutes. The system interprets a charge period of 1 minute as hourly billing when the price represents a full hour.

Example — create a $50/hour meeting room pricing rule:

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
| `nexudus extraservices get <id> --agent` | Get single extraservice |
| `nexudus extraservices create --business-id <value> --name <value> --display-order <value> --price <value> --charge-period <value> --currency-id <value> --last-minute-adjustment-type <value> --agent` | Create extraservice |
| `nexudus extraservices update <id> --name "New Name" --agent` | Update extraservice |
| `nexudus extraservices delete <id> --yes --agent` | Delete extraservice (no prompt) |
| `nexudus extraservices run-command <key> <ids> --agent` | Run entity command |

#### ExtraService list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Extra service name |
| `--description` | string | Free-text description of this extra service |
| `--invoice-display` | string | Invoice line display text |
| `--visible` | bool | Whether the price is visible on the portal and app |
| `--display-order` | int | Display order |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--price` | decimal | Unit price amount |
| `--from-price` | range | |
| `--to-price` | range | |
| `--credit-price` | decimal | Credit price |
| `--from-credit-price` | range | |
| `--to-credit-price` | range | |
| `--charge-period` | enum | Charge period |
| `--maximum-price` | decimal | Maximum price cap |
| `--from-maximum-price` | range | |
| `--to-maximum-price` | range | |
| `--default-price` | bool | Use as the default price for matched resource types if more than one price applies |
| `--per-night-pricing` | bool | Use per-night pricing |
| `--currency-id` | long | ID of the currency linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--reduced-tax-rate-id` | long | ID of the reduced tax rate linked to this record |
| `--exempt-tax-rate-id` | long | ID of the exempt tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--from-time` | int | Start time restriction (minutes from midnight) |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | int | End time restriction (minutes from midnight) |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--min-length` | int | Minimum booking length (minutes) |
| `--from-min-length` | range | |
| `--to-min-length` | range | |
| `--max-length` | int | Maximum booking length (minutes) |
| `--from-max-length` | range | |
| `--to-max-length` | range | |
| `--only-within-available-times` | bool | Only apply within the resource's available times |
| `--fixed-cost-length` | int | Fixed cost booking length threshold (minutes) |
| `--from-fixed-cost-length` | range | |
| `--to-fixed-cost-length` | range | |
| `--fixed-cost-price` | decimal | Fixed cost price applied once the threshold is reached |
| `--from-fixed-cost-price` | range | |
| `--to-fixed-cost-price` | range | |
| `--only-for-contacts` | bool | Only available for contacts |
| `--only-for-members` | bool | Only available for members |
| `--booking-credit` | bool | Price uses booking credits |
| `--printing-credit` | bool | Price uses printing credits |
| `--apply-to-visitors` | bool | Apply charge to visitors |
| `--price-factor-low-demand` | decimal | Price factor for low demand periods |
| `--from-price-factor-low-demand` | range | |
| `--to-price-factor-low-demand` | range | |
| `--price-factor-average-demand` | decimal | Price factor for average demand periods |
| `--from-price-factor-average-demand` | range | |
| `--to-price-factor-average-demand` | range | |
| `--price-factor-high-demand` | decimal | Price factor for high demand periods |
| `--from-price-factor-high-demand` | range | |
| `--to-price-factor-high-demand` | range | |
| `--price-factor-last-minute` | decimal | Price factor for last-minute bookings |
| `--from-price-factor-last-minute` | range | |
| `--to-price-factor-last-minute` | range | |
| `--last-minute-period` | int | Last-minute period threshold (minutes before booking) |
| `--from-last-minute-period` | range | |
| `--to-last-minute-period` | range | |
| `--last-minute-adjustment-type` | enum | Last-minute discount type |
| `--apply-from` | DateTime | Date from which this price applies |
| `--from-apply-from` | range | |
| `--to-apply-from` | range | |
| `--apply-to` | DateTime | Date until which this price applies |
| `--from-apply-to` | range | |
| `--to-apply-to` | range | |
| `--resource-type-names` | string | Comma-separated names of associated resource types |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ExtraService create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Extra service name |
| `--description` | string | Free-text description of this extra service |
| `--invoice-display` | string | Invoice line display text |
| `--visible` | bool | Whether the price is visible on the portal and app |
| `--display-order` | int, required | Display order |
| `--resource-types` | list, repeat flag | List of resource types linked to this record |
| `--added-resource-types` | list, repeat flag | The added resource types value for this extra service |
| `--removed-resource-types` | list, repeat flag | The removed resource types value for this extra service |
| `--price` | decimal, required | Unit price amount |
| `--credit-price` | decimal | Credit price |
| `--charge-period` | enum, required | Charge period |
| `--maximum-price` | decimal | Maximum price cap |
| `--default-price` | bool | Use as the default price for matched resource types if more than one price applies |
| `--per-night-pricing` | bool | Use per-night pricing |
| `--currency-id` | long, required | ID of the currency linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--reduced-tax-rate-id` | long | ID of the reduced tax rate linked to this record |
| `--exempt-tax-rate-id` | long | ID of the exempt tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--from-time` | int | Start time restriction (minutes from midnight) |
| `--to-time` | int | End time restriction (minutes from midnight) |
| `--min-length` | int | Minimum booking length (minutes) |
| `--max-length` | int | Maximum booking length (minutes) |
| `--only-within-available-times` | bool | Only apply within the resource's available times |
| `--fixed-cost-length` | int | Fixed cost booking length threshold (minutes) |
| `--fixed-cost-price` | decimal | Fixed cost price applied once the threshold is reached |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this extra service |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this extra service |
| `--only-for-contacts` | bool | Only available for contacts |
| `--only-for-members` | bool | Only available for members |
| `--booking-credit` | bool | Price uses booking credits |
| `--printing-credit` | bool | Price uses printing credits |
| `--apply-to-visitors` | bool | Apply charge to visitors |
| `--price-factor-low-demand` | decimal | Price factor for low demand periods |
| `--price-factor-average-demand` | decimal | Price factor for average demand periods |
| `--price-factor-high-demand` | decimal | Price factor for high demand periods |
| `--price-factor-last-minute` | decimal | Price factor for last-minute bookings |
| `--last-minute-period` | int | Last-minute period threshold (minutes before booking) |
| `--last-minute-adjustment-type` | enum, required | Last-minute discount type |
| `--apply-from` | DateTime | Date from which this price applies |
| `--apply-to` | DateTime | Date until which this price applies |
| `--resource-type-names` | string | Comma-separated names of associated resource types |
| `--teams` | list, repeat flag | List of teams linked to this record |
| `--added-teams` | list, repeat flag | The added teams value for this extra service |
| `--removed-teams` | list, repeat flag | The removed teams value for this extra service |
| `--time-slots` | JSON array or @filepath | The days and times this extra service price is available for booking. The year, month and day component of FromTime/ToTime is always 1976-01-01. |

#### ExtraService update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Extra service name |
| `--description` | string | Free-text description of this extra service |
| `--invoice-display` | string | Invoice line display text |
| `--visible` | bool | Whether the price is visible on the portal and app |
| `--display-order` | int | Display order |
| `--resource-types` | list, repeat flag | List of resource types linked to this record |
| `--added-resource-types` | list, repeat flag | The added resource types value for this extra service |
| `--removed-resource-types` | list, repeat flag | The removed resource types value for this extra service |
| `--price` | decimal | Unit price amount |
| `--credit-price` | decimal | Credit price |
| `--charge-period` | enum | Charge period |
| `--maximum-price` | decimal | Maximum price cap |
| `--default-price` | bool | Use as the default price for matched resource types if more than one price applies |
| `--per-night-pricing` | bool | Use per-night pricing |
| `--currency-id` | long | ID of the currency linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--reduced-tax-rate-id` | long | ID of the reduced tax rate linked to this record |
| `--exempt-tax-rate-id` | long | ID of the exempt tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--from-time` | int | Start time restriction (minutes from midnight) |
| `--to-time` | int | End time restriction (minutes from midnight) |
| `--min-length` | int | Minimum booking length (minutes) |
| `--max-length` | int | Maximum booking length (minutes) |
| `--only-within-available-times` | bool | Only apply within the resource's available times |
| `--fixed-cost-length` | int | Fixed cost booking length threshold (minutes) |
| `--fixed-cost-price` | decimal | Fixed cost price applied once the threshold is reached |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this extra service |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this extra service |
| `--only-for-contacts` | bool | Only available for contacts |
| `--only-for-members` | bool | Only available for members |
| `--booking-credit` | bool | Price uses booking credits |
| `--printing-credit` | bool | Price uses printing credits |
| `--apply-to-visitors` | bool | Apply charge to visitors |
| `--price-factor-low-demand` | decimal | Price factor for low demand periods |
| `--price-factor-average-demand` | decimal | Price factor for average demand periods |
| `--price-factor-high-demand` | decimal | Price factor for high demand periods |
| `--price-factor-last-minute` | decimal | Price factor for last-minute bookings |
| `--last-minute-period` | int | Last-minute period threshold (minutes before booking) |
| `--last-minute-adjustment-type` | enum | Last-minute discount type |
| `--apply-from` | DateTime | Date from which this price applies |
| `--apply-to` | DateTime | Date until which this price applies |
| `--resource-type-names` | string | Comma-separated names of associated resource types |
| `--teams` | list, repeat flag | List of teams linked to this record |
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
