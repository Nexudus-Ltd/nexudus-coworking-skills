# ResourceAccessRules

<!-- BEGIN:GENERATED entity=ResourceAccessRules -->

A **ResourceAccessRule** defines additional booking policies and restrictions for one or more `Resource`(s) or for all resources in a location (`Business`), scoped by date/time, customer, team, plan, or other criteria. Rules are evaluated in `EvaluationOrder` and can optionally stop further evaluation when matched (`StopEvaluationIfRuleIsMet`).

The booking-policy fields (`BookInAdvanceLimit`, `LateBookingLimit`, `LateCancellationLimit`, `IntervalLimit`, `MaxBookingLength`, `MinBookingLength`, `NoReturnPolicy*`, cancellation-fee fields, and repeat-booking limits) mirror those on `Resource` and carry the same semantics — they override the resource-level defaults when the rule matches.

When `BusinessId` is set and `Resources` is empty, the rule applies to all resources in the business and its children (if any). When specific `Resources` are listed, the rule applies only to those resources.

### Scope: who the rule applies to

- `OnlyForMembers` / `OnlyForContacts` — quick toggles to limit the rule to members or contacts.
- `Tariffs` — pricing plans this rule applies to. When set, the rule only fires for customers on one of these plans.
- `Teams` — teams this rule applies to. When set, the rule only fires for members of one of these teams.
- `Courses` — the rule applies only to customers who have completed one of these courses.
- `EventCategories` — the rule applies only to customers who have attended (checked in to) an event in one of these categories.

### Scope: who is allowed to book when the rule fires

- `AllowedTariffs` — only customers on one of these plans are allowed to book when the rule applies to them.
- `AllowedTeams` — only members of one of these teams are allowed to book when the rule applies to them.

### List mutation helpers

For each list field (`Tariffs`, `AllowedTariffs`, `Teams`, `AllowedTeams`, `Members`, `EventCategories`, `Courses`) there are `Added*` and `Removed*` variants that append or remove entries on update without replacing the full list.

ResourceAccessRules support Search, Get, Create, Update, Delete.
ResourceAccessRules also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus resourceaccessrules list --agent` | List all resourceaccessrules |
| `nexudus resourceaccessrules list --id <id> --agent` | Filter by single ID |
| `nexudus resourceaccessrules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resourceaccessrules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resourceaccessrules list --name <value> --active <value> --agent` | Filter resourceaccessrules by properties |
| `nexudus resourceaccessrules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resourceaccessrules list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus resourceaccessrules get <id> --agent` | Get single resourceaccessrule |
| `nexudus resourceaccessrules create --business-id <value> --name <value> --applied-resources-count <value> --evaluation-order <value> --cancellation-fee-type <value> --agent` | Create resourceaccessrule |
| `nexudus resourceaccessrules update <id> --name "New Name" --agent` | Update resourceaccessrule |
| `nexudus resourceaccessrules delete <id> --yes --agent` | Delete resourceaccessrule (no prompt) |
| `nexudus resourceaccessrules run-command <key> <ids> --agent` | Run entity command |

#### ResourceAccessRule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Rule name |
| `--active` | bool | Whether this rule is currently active and evaluated during booking. |
| `--only-for-contacts` | bool | When true, this rule applies only to contacts (non-member customers). |
| `--apply-rule-from` | DateTime | Date from which this rule starts being evaluated. Null means no start-date restriction. |
| `--from-apply-rule-from` | range | |
| `--to-apply-rule-from` | range | |
| `--apply-rule-to` | DateTime | Date after which this rule stops being evaluated. Null means no end-date restriction. |
| `--from-apply-rule-to` | range | |
| `--to-apply-rule-to` | range | |
| `--book-in-advance-limit` | decimal | Maximum number of days in advance a booking can be made. Null means no limit. |
| `--from-book-in-advance-limit` | range | |
| `--to-book-in-advance-limit` | range | |
| `--late-booking-limit` | decimal | Minimum lead time (in minutes) required before a booking can start. Prevents last-minute bookings. |
| `--from-late-booking-limit` | range | |
| `--to-late-booking-limit` | range | |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee. |
| `--from-late-cancellation-limit` | range | |
| `--to-late-cancellation-limit` | range | |
| `--interval-limit` | int | Minimum interval (in minutes) between consecutive bookings on this resource, used as a buffer for setup or cleaning. |
| `--from-interval-limit` | range | |
| `--to-interval-limit` | range | |
| `--max-booking-length` | int | Maximum allowed duration for a single booking, in minutes. |
| `--from-max-booking-length` | range | |
| `--to-max-booking-length` | range | |
| `--min-booking-length` | int | Minimum allowed duration for a single booking, in minutes. |
| `--from-min-booking-length` | range | |
| `--to-min-booking-length` | range | |
| `--applied-resources-count` | int | The applied resources count value for this resource access rule |
| `--from-applied-resources-count` | range | |
| `--to-applied-resources-count` | range | |
| `--no-return-policy` | int | Cooldown in minutes: prevents the same user from booking this specific resource again within this window after their last booking ends. |
| `--from-no-return-policy` | range | |
| `--to-no-return-policy` | range | |
| `--no-return-policy-all-resources` | int | Cooldown in minutes: prevents the same user from booking any resource after booking this one, for the specified window. |
| `--from-no-return-policy-all-resources` | range | |
| `--to-no-return-policy-all-resources` | range | |
| `--no-return-policy-all-users` | int | Cooldown in minutes: prevents any user from booking this resource within the specified window after the previous booking ends. |
| `--from-no-return-policy-all-users` | range | |
| `--to-no-return-policy-all-users` | range | |
| `--reject-with-message` | string | Message shown to the user when their booking is rejected by this rule. |
| `--only-for-members` | bool | When true, this rule applies only to active members (coworkers with a plan). |
| `--evaluation-order` | int | Order in which this rule is evaluated relative to other rules on the same resource. Lower values are evaluated first. |
| `--from-evaluation-order` | range | |
| `--to-evaluation-order` | range | |
| `--stop-evaluation-if-rule-is-met` | bool | When true, no further rules are evaluated after this one matches. |
| `--cancellation-fee-product-id` | long | ID of the cancellation fee product linked to this record |
| `--charge-cancellation-fee` | bool | When true, a fee is charged for late cancellations (past the LateCancellationLimit). |
| `--cancellation-fee-type` | enum | How the cancellation fee is calculated: Absolute (fixed amount) or Percentage (of booking cost). |
| `--cancellation-fee-amount` | decimal | Fixed cancellation fee amount. Used when CancellationFeeType is Absolute. |
| `--from-cancellation-fee-amount` | range | |
| `--to-cancellation-fee-amount` | range | |
| `--cancellation-fee-percentage` | decimal | Cancellation fee as a percentage of the booking cost. Used when CancellationFeeType is Percentage. |
| `--from-cancellation-fee-percentage` | range | |
| `--to-cancellation-fee-percentage` | range | |
| `--repeat-booking-quantity-limit` | int | Maximum number of occurrences allowed when creating a recurring booking under this rule. |
| `--from-repeat-booking-quantity-limit` | range | |
| `--to-repeat-booking-quantity-limit` | range | |
| `--repeat-booking-period-limit-in-months` | int | Maximum time span (in months) over which a recurring booking series can extend under this rule. |
| `--from-repeat-booking-period-limit-in-months` | range | |
| `--to-repeat-booking-period-limit-in-months` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ResourceAccessRule sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ResourceAccessRule create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--resources` | list, repeat flag | List of resources linked to this record |
| `--added-resources` | list, repeat flag | The added resources value for this resource access rule |
| `--removed-resources` | list, repeat flag | The removed resources value for this resource access rule |
| `--name` | string, required | Rule name |
| `--active` | bool | Whether this rule is currently active and evaluated during booking. |
| `--only-for-contacts` | bool | When true, this rule applies only to contacts (non-member customers). |
| `--apply-rule-from` | DateTime | Date from which this rule starts being evaluated. Null means no start-date restriction. |
| `--apply-rule-to` | DateTime | Date after which this rule stops being evaluated. Null means no end-date restriction. |
| `--book-in-advance-limit` | decimal | Maximum number of days in advance a booking can be made. Null means no limit. |
| `--late-booking-limit` | decimal | Minimum lead time (in minutes) required before a booking can start. Prevents last-minute bookings. |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee. |
| `--interval-limit` | int | Minimum interval (in minutes) between consecutive bookings on this resource, used as a buffer for setup or cleaning. |
| `--max-booking-length` | int | Maximum allowed duration for a single booking, in minutes. |
| `--min-booking-length` | int | Minimum allowed duration for a single booking, in minutes. |
| `--applied-resources-count` | int, required | The applied resources count value for this resource access rule |
| `--no-return-policy` | int | Cooldown in minutes: prevents the same user from booking this specific resource again within this window after their last booking ends. |
| `--no-return-policy-all-resources` | int | Cooldown in minutes: prevents the same user from booking any resource after booking this one, for the specified window. |
| `--no-return-policy-all-users` | int | Cooldown in minutes: prevents any user from booking this resource within the specified window after the previous booking ends. |
| `--reject-with-message` | string | Message shown to the user when their booking is rejected by this rule. |
| `--only-for-members` | bool | When true, this rule applies only to active members (coworkers with a plan). |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this resource access rule |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this resource access rule |
| `--allowed-tariffs` | list, repeat flag | List of allowed tariffs linked to this record |
| `--added-allowed-tariffs` | list, repeat flag | The added allowed tariffs value for this resource access rule |
| `--removed-allowed-tariffs` | list, repeat flag | The removed allowed tariffs value for this resource access rule |
| `--members` | list, repeat flag | List of members linked to this record |
| `--added-members` | list, repeat flag | The added members value for this resource access rule |
| `--removed-members` | list, repeat flag | The removed members value for this resource access rule |
| `--teams` | list, repeat flag | List of teams linked to this record |
| `--added-teams` | list, repeat flag | The added teams value for this resource access rule |
| `--removed-teams` | list, repeat flag | The removed teams value for this resource access rule |
| `--allowed-teams` | list, repeat flag | List of allowed teams linked to this record |
| `--added-allowed-teams` | list, repeat flag | The added allowed teams value for this resource access rule |
| `--removed-allowed-teams` | list, repeat flag | The removed allowed teams value for this resource access rule |
| `--event-categories` | list, repeat flag | List of event categories linked to this record |
| `--added-event-categories` | list, repeat flag | The added event categories value for this resource access rule |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this resource access rule |
| `--courses` | list, repeat flag | List of courses linked to this record |
| `--added-courses` | list, repeat flag | The added courses value for this resource access rule |
| `--removed-courses` | list, repeat flag | The removed courses value for this resource access rule |
| `--evaluation-order` | int, required | Order in which this rule is evaluated relative to other rules on the same resource. Lower values are evaluated first. |
| `--stop-evaluation-if-rule-is-met` | bool | When true, no further rules are evaluated after this one matches. |
| `--cancellation-fee-product-id` | long | ID of the cancellation fee product linked to this record |
| `--charge-cancellation-fee` | bool | When true, a fee is charged for late cancellations (past the LateCancellationLimit). |
| `--cancellation-fee-type` | enum, required | How the cancellation fee is calculated: Absolute (fixed amount) or Percentage (of booking cost). |
| `--cancellation-fee-amount` | decimal | Fixed cancellation fee amount. Used when CancellationFeeType is Absolute. |
| `--cancellation-fee-percentage` | decimal | Cancellation fee as a percentage of the booking cost. Used when CancellationFeeType is Percentage. |
| `--repeat-booking-quantity-limit` | int | Maximum number of occurrences allowed when creating a recurring booking under this rule. |
| `--repeat-booking-period-limit-in-months` | int | Maximum time span (in months) over which a recurring booking series can extend under this rule. |
| `--eligible-time-slots` | JSON array or @filepath | Time slots defining when this rule applies (eligibility windows). The year, month and day component of FromTime/ToTime is always 1976-01-01. |
| `--time-slots` | JSON array or @filepath | The days and times the resources can be booked when this rule applies. The year, month and day component of FromTime/ToTime is always 1976-01-01. |

#### ResourceAccessRule update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--resources` | list, repeat flag | List of resources linked to this record |
| `--added-resources` | list, repeat flag | The added resources value for this resource access rule |
| `--removed-resources` | list, repeat flag | The removed resources value for this resource access rule |
| `--name` | string | Rule name |
| `--active` | bool | Whether this rule is currently active and evaluated during booking. |
| `--only-for-contacts` | bool | When true, this rule applies only to contacts (non-member customers). |
| `--apply-rule-from` | DateTime | Date from which this rule starts being evaluated. Null means no start-date restriction. |
| `--apply-rule-to` | DateTime | Date after which this rule stops being evaluated. Null means no end-date restriction. |
| `--book-in-advance-limit` | decimal | Maximum number of days in advance a booking can be made. Null means no limit. |
| `--late-booking-limit` | decimal | Minimum lead time (in minutes) required before a booking can start. Prevents last-minute bookings. |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee. |
| `--interval-limit` | int | Minimum interval (in minutes) between consecutive bookings on this resource, used as a buffer for setup or cleaning. |
| `--max-booking-length` | int | Maximum allowed duration for a single booking, in minutes. |
| `--min-booking-length` | int | Minimum allowed duration for a single booking, in minutes. |
| `--applied-resources-count` | int | The applied resources count value for this resource access rule |
| `--no-return-policy` | int | Cooldown in minutes: prevents the same user from booking this specific resource again within this window after their last booking ends. |
| `--no-return-policy-all-resources` | int | Cooldown in minutes: prevents the same user from booking any resource after booking this one, for the specified window. |
| `--no-return-policy-all-users` | int | Cooldown in minutes: prevents any user from booking this resource within the specified window after the previous booking ends. |
| `--reject-with-message` | string | Message shown to the user when their booking is rejected by this rule. |
| `--only-for-members` | bool | When true, this rule applies only to active members (coworkers with a plan). |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this resource access rule |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this resource access rule |
| `--allowed-tariffs` | list, repeat flag | List of allowed tariffs linked to this record |
| `--added-allowed-tariffs` | list, repeat flag | The added allowed tariffs value for this resource access rule |
| `--removed-allowed-tariffs` | list, repeat flag | The removed allowed tariffs value for this resource access rule |
| `--members` | list, repeat flag | List of members linked to this record |
| `--added-members` | list, repeat flag | The added members value for this resource access rule |
| `--removed-members` | list, repeat flag | The removed members value for this resource access rule |
| `--teams` | list, repeat flag | List of teams linked to this record |
| `--added-teams` | list, repeat flag | The added teams value for this resource access rule |
| `--removed-teams` | list, repeat flag | The removed teams value for this resource access rule |
| `--allowed-teams` | list, repeat flag | List of allowed teams linked to this record |
| `--added-allowed-teams` | list, repeat flag | The added allowed teams value for this resource access rule |
| `--removed-allowed-teams` | list, repeat flag | The removed allowed teams value for this resource access rule |
| `--event-categories` | list, repeat flag | List of event categories linked to this record |
| `--added-event-categories` | list, repeat flag | The added event categories value for this resource access rule |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this resource access rule |
| `--courses` | list, repeat flag | List of courses linked to this record |
| `--added-courses` | list, repeat flag | The added courses value for this resource access rule |
| `--removed-courses` | list, repeat flag | The removed courses value for this resource access rule |
| `--evaluation-order` | int | Order in which this rule is evaluated relative to other rules on the same resource. Lower values are evaluated first. |
| `--stop-evaluation-if-rule-is-met` | bool | When true, no further rules are evaluated after this one matches. |
| `--cancellation-fee-product-id` | long | ID of the cancellation fee product linked to this record |
| `--charge-cancellation-fee` | bool | When true, a fee is charged for late cancellations (past the LateCancellationLimit). |
| `--cancellation-fee-type` | enum | How the cancellation fee is calculated: Absolute (fixed amount) or Percentage (of booking cost). |
| `--cancellation-fee-amount` | decimal | Fixed cancellation fee amount. Used when CancellationFeeType is Absolute. |
| `--cancellation-fee-percentage` | decimal | Cancellation fee as a percentage of the booking cost. Used when CancellationFeeType is Percentage. |
| `--repeat-booking-quantity-limit` | int | Maximum number of occurrences allowed when creating a recurring booking under this rule. |
| `--repeat-booking-period-limit-in-months` | int | Maximum time span (in months) over which a recurring booking series can extend under this rule. |
| `--eligible-time-slots` | JSON array or @filepath | Time slots defining when this rule applies (eligibility windows). The year, month and day component of FromTime/ToTime is always 1976-01-01. |
| `--time-slots` | JSON array or @filepath | The days and times the resources can be booked when this rule applies. The year, month and day component of FromTime/ToTime is always 1976-01-01. |

### ResourceAccessRule (key fields)

`Id`, `Name`, `Active`

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `AllowedTariffs`, `AddedAllowedTariffs`, `RemovedAllowedTariffs`, `Members`, `AddedMembers`, `RemovedMembers`, `Teams`, `AddedTeams`, `RemovedTeams`, `AllowedTeams`, `AddedAllowedTeams`, `RemovedAllowedTeams`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `Courses`, `AddedCourses`, `RemovedCourses`

#### ResourceAccessRule inline children

ResourceAccessRule supports inline child objects on create and update. Pass a JSON array or a `@filepath` reference.

**`--eligible-time-slots`** — Time slots defining when this rule applies (eligibility windows). The year, month and day component of FromTime/ToTime is always 1976-01-01.

Writable properties: `DayOfWeek`, `FromTime`, `ToTime`

```shell
nexudus resourceaccessrules create ... --eligible-time-slots '[{"DayOfWeek": "...", "FromTime": "...", "ToTime": "..."}]' --agent
```

Or from a file:

```shell
nexudus resourceaccessrules create ... --eligible-time-slots @eligibletimeslots.json --agent
```

**`--time-slots`** — The days and times the resources can be booked when this rule applies. The year, month and day component of FromTime/ToTime is always 1976-01-01.

Writable properties: `DayOfWeek`, `FromTime`, `ToTime`

```shell
nexudus resourceaccessrules create ... --time-slots '[{"DayOfWeek": "...", "FromTime": "...", "ToTime": "..."}]' --agent
```

Or from a file:

```shell
nexudus resourceaccessrules create ... --time-slots @timeslots.json --agent
```

#### ResourceAccessRule enum values

| Option | Valid values |
| ------ | ------------ |
| `--cancellation-fee-type` | `0` None, `1` Absolute, `2` Percentage |

<!-- END:GENERATED entity=ResourceAccessRules -->
