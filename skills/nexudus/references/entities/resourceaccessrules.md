# ResourceAccessRules

<!-- BEGIN:GENERATED entity=ResourceAccessRules -->

A ResourceAccessRule defines overriding booking policies and restrictions for one or more resources or for all resources in a location, scoped by date/time, customer, team, plan, or other criteria. Rules are evaluated in EvaluationOrder and can optionally stop further evaluation when matched (StopEvaluationIfRuleIsMet). When a rule matches, it overrides the resource-level booking policies and restrictions for that booking. The booking-policy fields (BookInAdvanceLimit, LateBookingLimit, LateCancellationLimit, IntervalLimit, MaxBookingLength, MinBookingLength, NoReturnPolicy fields, cancellation-fee fields, and repeat-booking limits) mirror those on Resource and carry the same semantics — they override the resource-level defaults when the rule matches. SCOPE: When the rule is connected to a Business and NO Resources are selected, it applies to ALL resources within that business AND all child businesses. When the rule is connected to one or more specific Resources, it applies ONLY to those resources. Use scope fields (OnlyForMembers, OnlyForContacts, Tariffs, Teams, Members, Courses, EventCategories) to control who the rule applies to, and allowed fields (AllowedTariffs, AllowedTeams) to control who can book when the rule fires.

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
| `--business-id` | long | ID of the location linked to this rule |
| `--name` | string | Rule name |
| `--active` | bool | Whether this rule is currently active and evaluated during booking |
| `--only-for-contacts` | bool | When true, this rule applies only to contacts (non-member customers) |
| `--apply-rule-from` | DateTime | Date from which this rule starts being evaluated. Null means no start-date restriction |
| `--from-apply-rule-from` | range | |
| `--to-apply-rule-from` | range | |
| `--apply-rule-to` | DateTime | Date after which this rule stops being evaluated. Null means no end-date restriction |
| `--from-apply-rule-to` | range | |
| `--to-apply-rule-to` | range | |
| `--apply-if-within-minutes-of-start` | int | Apply this rule only if the booking is within this many minutes of its start time |
| `--from-apply-if-within-minutes-of-start` | range | |
| `--to-apply-if-within-minutes-of-start` | range | |
| `--apply-if-more-than-minutes-from-start` | int | Apply this rule only if the booking is more than this many minutes away from its start time |
| `--from-apply-if-more-than-minutes-from-start` | range | |
| `--to-apply-if-more-than-minutes-from-start` | range | |
| `--apply-if-price-min` | decimal | Apply this rule only if the booking price is at least this amount |
| `--from-apply-if-price-min` | range | |
| `--to-apply-if-price-min` | range | |
| `--apply-if-price-max` | decimal | Apply this rule only if the booking price does not exceed this amount |
| `--from-apply-if-price-max` | range | |
| `--to-apply-if-price-max` | range | |
| `--book-in-advance-limit` | decimal | Maximum number of hours in advance a booking can be made. Null means no limit |
| `--from-book-in-advance-limit` | range | |
| `--to-book-in-advance-limit` | range | |
| `--late-booking-limit` | decimal | Minimum lead time (in hours) required before a booking can start. Prevents last-minute bookings |
| `--from-late-booking-limit` | range | |
| `--to-late-booking-limit` | range | |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee |
| `--from-late-cancellation-limit` | range | |
| `--to-late-cancellation-limit` | range | |
| `--interval-limit` | int | Minimum interval (in minutes) between consecutive bookings on this resource, used as a buffer for setup or cleaning |
| `--from-interval-limit` | range | |
| `--to-interval-limit` | range | |
| `--max-booking-length` | int | Maximum allowed duration for a single booking, in minutes |
| `--from-max-booking-length` | range | |
| `--to-max-booking-length` | range | |
| `--min-booking-length` | int | Minimum allowed duration for a single booking, in minutes |
| `--from-min-booking-length` | range | |
| `--to-min-booking-length` | range | |
| `--applied-resources-count` | int | Count of resources this rule is currently applied to (read-only) |
| `--from-applied-resources-count` | range | |
| `--to-applied-resources-count` | range | |
| `--no-return-policy` | int | Cooldown in minutes: prevents the same user from booking this specific resource again within this window after their last booking ends |
| `--from-no-return-policy` | range | |
| `--to-no-return-policy` | range | |
| `--no-return-policy-all-resources` | int | Cooldown in minutes: prevents the same user from booking any resource after booking this one, for the specified window |
| `--from-no-return-policy-all-resources` | range | |
| `--to-no-return-policy-all-resources` | range | |
| `--no-return-policy-all-users` | int | Cooldown in minutes: prevents any user from booking this resource within the specified window after the previous booking ends |
| `--from-no-return-policy-all-users` | range | |
| `--to-no-return-policy-all-users` | range | |
| `--reject-with-message` | string | Message shown to the user when their booking is rejected by this rule |
| `--only-for-members` | bool | When true, this rule applies only to active members (coworkers with a plan) |
| `--evaluation-order` | int | Order in which this rule is evaluated relative to other rules on the same resource. Lower values are evaluated first |
| `--from-evaluation-order` | range | |
| `--to-evaluation-order` | range | |
| `--stop-evaluation-if-rule-is-met` | bool | When true, no further rules are evaluated after this one matches |
| `--cancellation-fee-product-id` | long | Product to charge for late cancellations when ChargeCancellationFee is true |
| `--cancellation-fee-product-name` | string | Name of the cancellation fee product (read-only, resolved from CancellationFeeProductId). |
| `--charge-cancellation-fee` | bool | When true, a fee is charged for late cancellations (past the LateCancellationLimit) |
| `--cancellation-fee-type` | enum | How the cancellation fee is calculated: Absolute (fixed amount) or Percentage (of booking cost) |
| `--cancellation-fee-amount` | decimal | Fixed cancellation fee amount. Used when CancellationFeeType is Absolute |
| `--from-cancellation-fee-amount` | range | |
| `--to-cancellation-fee-amount` | range | |
| `--cancellation-fee-percentage` | decimal | Cancellation fee as a percentage of the booking cost. Used when CancellationFeeType is Percentage |
| `--from-cancellation-fee-percentage` | range | |
| `--to-cancellation-fee-percentage` | range | |
| `--repeat-booking-quantity-limit` | int | Maximum number of occurrences allowed when creating a recurring booking under this rule |
| `--from-repeat-booking-quantity-limit` | range | |
| `--to-repeat-booking-quantity-limit` | range | |
| `--repeat-booking-period-limit-in-months` | int | Maximum time span (in months) over which a recurring booking series can extend under this rule |
| `--from-repeat-booking-period-limit-in-months` | range | |
| `--to-repeat-booking-period-limit-in-months` | range | |
| `--tariff-names` | string | Read-only, comma-separated names of the plans this rule applies to |
| `--team-names` | string | Read-only, comma-separated names of the teams this rule applies to |
| `--coworker-full-names` | string | Read-only, comma-separated full names of the customers this rule applies to |
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
| `--business-id` | long, required | ID of the location linked to this rule |
| `--resources` | list, repeat flag | List of specific resources this rule applies to. When empty and BusinessId is set, applies to all resources in that location and all child locations. When one or more resources are specified, applies only to those specific resources |
| `--added-resources` | list, repeat flag | The added resources value for this resource access rule |
| `--removed-resources` | list, repeat flag | The removed resources value for this resource access rule |
| `--name` | string, required | Rule name |
| `--active` | bool | Whether this rule is currently active and evaluated during booking |
| `--only-for-contacts` | bool | When true, this rule applies only to contacts (non-member customers) |
| `--apply-rule-from` | DateTime | Date from which this rule starts being evaluated. Null means no start-date restriction |
| `--apply-rule-to` | DateTime | Date after which this rule stops being evaluated. Null means no end-date restriction |
| `--apply-if-within-minutes-of-start` | int | Apply this rule only if the booking is within this many minutes of its start time |
| `--apply-if-more-than-minutes-from-start` | int | Apply this rule only if the booking is more than this many minutes away from its start time |
| `--apply-if-price-min` | decimal | Apply this rule only if the booking price is at least this amount |
| `--apply-if-price-max` | decimal | Apply this rule only if the booking price does not exceed this amount |
| `--book-in-advance-limit` | decimal | Maximum number of hours in advance a booking can be made. Null means no limit |
| `--late-booking-limit` | decimal | Minimum lead time (in hours) required before a booking can start. Prevents last-minute bookings |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee |
| `--interval-limit` | int | Minimum interval (in minutes) between consecutive bookings on this resource, used as a buffer for setup or cleaning |
| `--max-booking-length` | int | Maximum allowed duration for a single booking, in minutes |
| `--min-booking-length` | int | Minimum allowed duration for a single booking, in minutes |
| `--applied-resources-count` | int, required | Count of resources this rule is currently applied to (read-only) |
| `--no-return-policy` | int | Cooldown in minutes: prevents the same user from booking this specific resource again within this window after their last booking ends |
| `--no-return-policy-all-resources` | int | Cooldown in minutes: prevents the same user from booking any resource after booking this one, for the specified window |
| `--no-return-policy-all-users` | int | Cooldown in minutes: prevents any user from booking this resource within the specified window after the previous booking ends |
| `--reject-with-message` | string | Message shown to the user when their booking is rejected by this rule |
| `--only-for-members` | bool | When true, this rule applies only to active members (coworkers with a plan) |
| `--tariffs` | list, repeat flag | List of pricing plans this rule applies to. When set, the rule only fires for customers on one of these plans |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this resource access rule |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this resource access rule |
| `--allowed-tariffs` | list, repeat flag | Only customers on one of these pricing plans are allowed to book when the rule applies to them |
| `--added-allowed-tariffs` | list, repeat flag | The added allowed tariffs value for this resource access rule |
| `--removed-allowed-tariffs` | list, repeat flag | The removed allowed tariffs value for this resource access rule |
| `--members` | list, repeat flag | Specific customers this rule applies to. When set, the rule only fires for these customers |
| `--added-members` | list, repeat flag | The added members value for this resource access rule |
| `--removed-members` | list, repeat flag | The removed members value for this resource access rule |
| `--teams` | list, repeat flag | Teams this rule applies to. When set, the rule only fires for members of one of these teams |
| `--added-teams` | list, repeat flag | The added teams value for this resource access rule |
| `--removed-teams` | list, repeat flag | The removed teams value for this resource access rule |
| `--allowed-teams` | list, repeat flag | Only members of one of these teams are allowed to book when the rule applies to them |
| `--added-allowed-teams` | list, repeat flag | The added allowed teams value for this resource access rule |
| `--removed-allowed-teams` | list, repeat flag | The removed allowed teams value for this resource access rule |
| `--event-categories` | list, repeat flag | The rule applies only to customers who have attended (checked in to) an event in one of these categories |
| `--added-event-categories` | list, repeat flag | The added event categories value for this resource access rule |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this resource access rule |
| `--courses` | list, repeat flag | The rule applies only to customers who have completed one of these courses |
| `--added-courses` | list, repeat flag | The added courses value for this resource access rule |
| `--removed-courses` | list, repeat flag | The removed courses value for this resource access rule |
| `--evaluation-order` | int, required | Order in which this rule is evaluated relative to other rules on the same resource. Lower values are evaluated first |
| `--stop-evaluation-if-rule-is-met` | bool | When true, no further rules are evaluated after this one matches |
| `--cancellation-fee-product-id` | long | Product to charge for late cancellations when ChargeCancellationFee is true |
| `--charge-cancellation-fee` | bool | When true, a fee is charged for late cancellations (past the LateCancellationLimit) |
| `--cancellation-fee-type` | enum, required | How the cancellation fee is calculated: Absolute (fixed amount) or Percentage (of booking cost) |
| `--cancellation-fee-amount` | decimal | Fixed cancellation fee amount. Used when CancellationFeeType is Absolute |
| `--cancellation-fee-percentage` | decimal | Cancellation fee as a percentage of the booking cost. Used when CancellationFeeType is Percentage |
| `--repeat-booking-quantity-limit` | int | Maximum number of occurrences allowed when creating a recurring booking under this rule |
| `--repeat-booking-period-limit-in-months` | int | Maximum time span (in months) over which a recurring booking series can extend under this rule |
| `--eligible-time-slots` | JSON array or @filepath | Time slots defining when this rule applies (eligibility windows). The year, month and day component of FromTime/ToTime is always 1976-01-01. |
| `--time-slots` | JSON array or @filepath | The days and times the resources can be booked when this rule applies. The year, month and day component of FromTime/ToTime is always 1976-01-01. |

#### ResourceAccessRule update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location linked to this rule |
| `--resources` | list, repeat flag | List of specific resources this rule applies to. When empty and BusinessId is set, applies to all resources in that location and all child locations. When one or more resources are specified, applies only to those specific resources |
| `--added-resources` | list, repeat flag | The added resources value for this resource access rule |
| `--removed-resources` | list, repeat flag | The removed resources value for this resource access rule |
| `--name` | string | Rule name |
| `--active` | bool | Whether this rule is currently active and evaluated during booking |
| `--only-for-contacts` | bool | When true, this rule applies only to contacts (non-member customers) |
| `--apply-rule-from` | DateTime | Date from which this rule starts being evaluated. Null means no start-date restriction |
| `--apply-rule-to` | DateTime | Date after which this rule stops being evaluated. Null means no end-date restriction |
| `--apply-if-within-minutes-of-start` | int | Apply this rule only if the booking is within this many minutes of its start time |
| `--apply-if-more-than-minutes-from-start` | int | Apply this rule only if the booking is more than this many minutes away from its start time |
| `--apply-if-price-min` | decimal | Apply this rule only if the booking price is at least this amount |
| `--apply-if-price-max` | decimal | Apply this rule only if the booking price does not exceed this amount |
| `--book-in-advance-limit` | decimal | Maximum number of hours in advance a booking can be made. Null means no limit |
| `--late-booking-limit` | decimal | Minimum lead time (in hours) required before a booking can start. Prevents last-minute bookings |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee |
| `--interval-limit` | int | Minimum interval (in minutes) between consecutive bookings on this resource, used as a buffer for setup or cleaning |
| `--max-booking-length` | int | Maximum allowed duration for a single booking, in minutes |
| `--min-booking-length` | int | Minimum allowed duration for a single booking, in minutes |
| `--applied-resources-count` | int | Count of resources this rule is currently applied to (read-only) |
| `--no-return-policy` | int | Cooldown in minutes: prevents the same user from booking this specific resource again within this window after their last booking ends |
| `--no-return-policy-all-resources` | int | Cooldown in minutes: prevents the same user from booking any resource after booking this one, for the specified window |
| `--no-return-policy-all-users` | int | Cooldown in minutes: prevents any user from booking this resource within the specified window after the previous booking ends |
| `--reject-with-message` | string | Message shown to the user when their booking is rejected by this rule |
| `--only-for-members` | bool | When true, this rule applies only to active members (coworkers with a plan) |
| `--tariffs` | list, repeat flag | List of pricing plans this rule applies to. When set, the rule only fires for customers on one of these plans |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this resource access rule |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this resource access rule |
| `--allowed-tariffs` | list, repeat flag | Only customers on one of these pricing plans are allowed to book when the rule applies to them |
| `--added-allowed-tariffs` | list, repeat flag | The added allowed tariffs value for this resource access rule |
| `--removed-allowed-tariffs` | list, repeat flag | The removed allowed tariffs value for this resource access rule |
| `--members` | list, repeat flag | Specific customers this rule applies to. When set, the rule only fires for these customers |
| `--added-members` | list, repeat flag | The added members value for this resource access rule |
| `--removed-members` | list, repeat flag | The removed members value for this resource access rule |
| `--teams` | list, repeat flag | Teams this rule applies to. When set, the rule only fires for members of one of these teams |
| `--added-teams` | list, repeat flag | The added teams value for this resource access rule |
| `--removed-teams` | list, repeat flag | The removed teams value for this resource access rule |
| `--allowed-teams` | list, repeat flag | Only members of one of these teams are allowed to book when the rule applies to them |
| `--added-allowed-teams` | list, repeat flag | The added allowed teams value for this resource access rule |
| `--removed-allowed-teams` | list, repeat flag | The removed allowed teams value for this resource access rule |
| `--event-categories` | list, repeat flag | The rule applies only to customers who have attended (checked in to) an event in one of these categories |
| `--added-event-categories` | list, repeat flag | The added event categories value for this resource access rule |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this resource access rule |
| `--courses` | list, repeat flag | The rule applies only to customers who have completed one of these courses |
| `--added-courses` | list, repeat flag | The added courses value for this resource access rule |
| `--removed-courses` | list, repeat flag | The removed courses value for this resource access rule |
| `--evaluation-order` | int | Order in which this rule is evaluated relative to other rules on the same resource. Lower values are evaluated first |
| `--stop-evaluation-if-rule-is-met` | bool | When true, no further rules are evaluated after this one matches |
| `--cancellation-fee-product-id` | long | Product to charge for late cancellations when ChargeCancellationFee is true |
| `--charge-cancellation-fee` | bool | When true, a fee is charged for late cancellations (past the LateCancellationLimit) |
| `--cancellation-fee-type` | enum | How the cancellation fee is calculated: Absolute (fixed amount) or Percentage (of booking cost) |
| `--cancellation-fee-amount` | decimal | Fixed cancellation fee amount. Used when CancellationFeeType is Absolute |
| `--cancellation-fee-percentage` | decimal | Cancellation fee as a percentage of the booking cost. Used when CancellationFeeType is Percentage |
| `--repeat-booking-quantity-limit` | int | Maximum number of occurrences allowed when creating a recurring booking under this rule |
| `--repeat-booking-period-limit-in-months` | int | Maximum time span (in months) over which a recurring booking series can extend under this rule |
| `--eligible-time-slots` | JSON array or @filepath | Time slots defining when this rule applies (eligibility windows). The year, month and day component of FromTime/ToTime is always 1976-01-01. |
| `--time-slots` | JSON array or @filepath | The days and times the resources can be booked when this rule applies. The year, month and day component of FromTime/ToTime is always 1976-01-01. |

#### ResourceAccessRule PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-names` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus resourceaccessrules update <id> --coworker-full-names "«PII:NAME:a3f2b1c9»" --agent`

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
| `--cancellation-fee-type` | `1` Absolute, `2` Percentage |

<!-- END:GENERATED entity=ResourceAccessRules -->
