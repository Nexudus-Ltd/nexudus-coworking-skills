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

`--business-id` (long), `--name`, `--description`, `--invoice-display`, `--visible` (bool), `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--price` (decimal), `--from-price` (range), `--to-price` (range), `--credit-price` (decimal), `--from-credit-price` (range), `--to-credit-price` (range), `--charge-period` (enum), `--maximum-price` (decimal), `--from-maximum-price` (range), `--to-maximum-price` (range), `--default-price` (bool), `--per-night-pricing` (bool), `--currency-id` (long), `--tax-rate-id` (long), `--reduced-tax-rate-id` (long), `--exempt-tax-rate-id` (long), `--financial-account-id` (long), `--from-time` (int), `--from-from-time` (range), `--to-from-time` (range), `--to-time` (int), `--from-to-time` (range), `--to-to-time` (range), `--min-length` (int), `--from-min-length` (range), `--to-min-length` (range), `--max-length` (int), `--from-max-length` (range), `--to-max-length` (range), `--only-within-available-times` (bool), `--fixed-cost-length` (int), `--from-fixed-cost-length` (range), `--to-fixed-cost-length` (range), `--fixed-cost-price` (decimal), `--from-fixed-cost-price` (range), `--to-fixed-cost-price` (range), `--only-for-contacts` (bool), `--only-for-members` (bool), `--booking-credit` (bool), `--printing-credit` (bool), `--apply-to-visitors` (bool), `--price-factor-low-demand` (decimal), `--from-price-factor-low-demand` (range), `--to-price-factor-low-demand` (range), `--price-factor-average-demand` (decimal), `--from-price-factor-average-demand` (range), `--to-price-factor-average-demand` (range), `--price-factor-high-demand` (decimal), `--from-price-factor-high-demand` (range), `--to-price-factor-high-demand` (range), `--price-factor-last-minute` (decimal), `--from-price-factor-last-minute` (range), `--to-price-factor-last-minute` (range), `--last-minute-period` (int), `--from-last-minute-period` (range), `--to-last-minute-period` (range), `--last-minute-adjustment-type` (enum), `--apply-from` (DateTime), `--from-apply-from` (range), `--to-apply-from` (range), `--apply-to` (DateTime), `--from-apply-to` (range), `--to-apply-to` (range), `--resource-type-names`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ExtraService create options

`--business-id` (long, required), `--name` (required), `--description`, `--invoice-display`, `--visible` (bool), `--display-order` (int, required), `--resource-types` (list, repeat flag), `--added-resource-types` (list, repeat flag), `--removed-resource-types` (list, repeat flag), `--price` (decimal, required), `--credit-price` (decimal), `--charge-period` (enum, required), `--maximum-price` (decimal), `--default-price` (bool), `--per-night-pricing` (bool), `--currency-id` (long, required), `--tax-rate-id` (long), `--reduced-tax-rate-id` (long), `--exempt-tax-rate-id` (long), `--financial-account-id` (long), `--from-time` (int), `--to-time` (int), `--min-length` (int), `--max-length` (int), `--only-within-available-times` (bool), `--fixed-cost-length` (int), `--fixed-cost-price` (decimal), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--only-for-contacts` (bool), `--only-for-members` (bool), `--booking-credit` (bool), `--printing-credit` (bool), `--apply-to-visitors` (bool), `--price-factor-low-demand` (decimal), `--price-factor-average-demand` (decimal), `--price-factor-high-demand` (decimal), `--price-factor-last-minute` (decimal), `--last-minute-period` (int), `--last-minute-adjustment-type` (enum, required), `--apply-from` (DateTime), `--apply-to` (DateTime), `--resource-type-names`, `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--time-slots` (JSON array or @filepath)

#### ExtraService update options

`--business-id` (long), `--name`, `--description`, `--invoice-display`, `--visible` (bool), `--display-order` (int), `--resource-types` (list, repeat flag), `--added-resource-types` (list, repeat flag), `--removed-resource-types` (list, repeat flag), `--price` (decimal), `--credit-price` (decimal), `--charge-period` (enum), `--maximum-price` (decimal), `--default-price` (bool), `--per-night-pricing` (bool), `--currency-id` (long), `--tax-rate-id` (long), `--reduced-tax-rate-id` (long), `--exempt-tax-rate-id` (long), `--financial-account-id` (long), `--from-time` (int), `--to-time` (int), `--min-length` (int), `--max-length` (int), `--only-within-available-times` (bool), `--fixed-cost-length` (int), `--fixed-cost-price` (decimal), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--only-for-contacts` (bool), `--only-for-members` (bool), `--booking-credit` (bool), `--printing-credit` (bool), `--apply-to-visitors` (bool), `--price-factor-low-demand` (decimal), `--price-factor-average-demand` (decimal), `--price-factor-high-demand` (decimal), `--price-factor-last-minute` (decimal), `--last-minute-period` (int), `--last-minute-adjustment-type` (enum), `--apply-from` (DateTime), `--apply-to` (DateTime), `--resource-type-names`, `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--time-slots` (JSON array or @filepath)

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
