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
| `nexudus extraservices create --business-id <value> --name <value> --display-order <value> --price <value> --currency-id <value> --agent` | Create extraservice |
| `nexudus extraservices update <id> --name "New Name" --agent` | Update extraservice |
| `nexudus extraservices delete <id> --yes --agent` | Delete extraservice (no prompt) |
| `nexudus extraservices run-command <key> <ids> --agent` | Run entity command |

#### ExtraService list filter options

`--business-id`, `--name`, `--description`, `--invoice-display`, `--visible`, `--display-order`, `--price`, `--credit-price`, `--charge-period`, `--maximum-price`, `--default-price`, `--per-night-pricing`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--from-time`, `--to-time`, `--min-length`, `--max-length`, `--only-within-available-times`, `--fixed-cost-length`, `--fixed-cost-price`, `--only-for-contacts`, `--only-for-members`, `--booking-credit`, `--printing-credit`, `--apply-to-visitors`, `--price-factor-low-demand`, `--price-factor-average-demand`, `--price-factor-high-demand`, `--price-factor-last-minute`, `--last-minute-period`, `--last-minute-adjustment-type`, `--apply-from`, `--apply-to`, `--resource-type-names`

#### ExtraService create options

`--business-id` (required), `--name` (required), `--description`, `--invoice-display`, `--visible`, `--display-order` (required), `--resource-types` (list, repeat flag), `--added-resource-types` (list, repeat flag), `--removed-resource-types` (list, repeat flag), `--price` (required), `--credit-price`, `--charge-period`, `--maximum-price`, `--default-price`, `--per-night-pricing`, `--currency-id` (required), `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--extra-service-prices` (list, repeat flag), `--added-extra-service-prices` (list, repeat flag), `--removed-extra-service-prices` (list, repeat flag), `--from-time`, `--to-time`, `--min-length`, `--max-length`, `--only-within-available-times`, `--fixed-cost-length`, `--fixed-cost-price`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--only-for-contacts`, `--only-for-members`, `--booking-credit`, `--printing-credit`, `--apply-to-visitors`, `--price-factor-low-demand`, `--price-factor-average-demand`, `--price-factor-high-demand`, `--price-factor-last-minute`, `--last-minute-period`, `--last-minute-adjustment-type`, `--apply-from`, `--apply-to`, `--resource-type-names`, `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--time-slots` (JSON array or @filepath)

#### ExtraService update options

`--business-id`, `--name`, `--description`, `--invoice-display`, `--visible`, `--display-order`, `--resource-types` (list, repeat flag), `--added-resource-types` (list, repeat flag), `--removed-resource-types` (list, repeat flag), `--price`, `--credit-price`, `--charge-period`, `--maximum-price`, `--default-price`, `--per-night-pricing`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--extra-service-prices` (list, repeat flag), `--added-extra-service-prices` (list, repeat flag), `--removed-extra-service-prices` (list, repeat flag), `--from-time`, `--to-time`, `--min-length`, `--max-length`, `--only-within-available-times`, `--fixed-cost-length`, `--fixed-cost-price`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--only-for-contacts`, `--only-for-members`, `--booking-credit`, `--printing-credit`, `--apply-to-visitors`, `--price-factor-low-demand`, `--price-factor-average-demand`, `--price-factor-high-demand`, `--price-factor-last-minute`, `--last-minute-period`, `--last-minute-adjustment-type`, `--apply-from`, `--apply-to`, `--resource-type-names`, `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--time-slots` (JSON array or @filepath)

### ExtraService (key fields)

`Id`, `Name`, `Visible`, `Price`, `ChargePeriod`, `IsDefaultPrice`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `ResourceTypeNames`

**List properties (only returned by `get`, not by `list`):** `ResourceTypes`, `AddedResourceTypes`, `RemovedResourceTypes`, `ExtraServicePrices`, `AddedExtraServicePrices`, `RemovedExtraServicePrices`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Teams`, `AddedTeams`, `RemovedTeams`

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
