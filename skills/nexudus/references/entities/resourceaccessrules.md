# ResourceAccessRules

<!-- BEGIN:GENERATED entity=ResourceAccessRules -->

A **ResourceAccessRule** defines additional booking policies and restrictions for a `Resource`, scoped by date/time, customer, team, plan, or other criteria. Rules are evaluated in `EvaluationOrder` and can optionally stop further evaluation when matched (`StopEvaluationIfRuleIsMet`).

The booking-policy fields (`BookInAdvanceLimit`, `LateBookingLimit`, `LateCancellationLimit`, `IntervalLimit`, `MaxBookingLength`, `MinBookingLength`, `NoReturnPolicy*`, cancellation-fee fields, and repeat-booking limits) mirror those on `Resource` and carry the same semantics — they override the resource-level defaults when the rule matches.

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
| `nexudus resourceaccessrules get <id> --agent` | Get single resourceaccessrule |
| `nexudus resourceaccessrules create --resource-id <value> --name <value> --evaluation-order <value> --agent` | Create resourceaccessrule |
| `nexudus resourceaccessrules update <id> --name "New Name" --agent` | Update resourceaccessrule |
| `nexudus resourceaccessrules delete <id> --yes --agent` | Delete resourceaccessrule (no prompt) |
| `nexudus resourceaccessrules run-command <key> <ids> --agent` | Run entity command |

#### ResourceAccessRule list filter options

`--resource-id`, `--name`, `--active`, `--only-for-contacts`, `--apply-rule-from`, `--apply-rule-to`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--max-booking-length`, `--min-booking-length`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--reject-with-message`, `--only-for-members`, `--evaluation-order`, `--stop-evaluation-if-rule-is-met`, `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`

#### ResourceAccessRule create options

`--resource-id` (required), `--name` (required), `--active`, `--only-for-contacts`, `--apply-rule-from`, `--apply-rule-to`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--max-booking-length`, `--min-booking-length`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--reject-with-message`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--allowed-tariffs` (list, repeat flag), `--added-allowed-tariffs` (list, repeat flag), `--removed-allowed-tariffs` (list, repeat flag), `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--allowed-teams` (list, repeat flag), `--added-allowed-teams` (list, repeat flag), `--removed-allowed-teams` (list, repeat flag), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--courses` (list, repeat flag), `--added-courses` (list, repeat flag), `--removed-courses` (list, repeat flag), `--evaluation-order` (required), `--stop-evaluation-if-rule-is-met`, `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`, `--eligible-time-slots` (JSON array or @filepath), `--time-slots` (JSON array or @filepath)

#### ResourceAccessRule update options

`--resource-id`, `--name`, `--active`, `--only-for-contacts`, `--apply-rule-from`, `--apply-rule-to`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--max-booking-length`, `--min-booking-length`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--reject-with-message`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--allowed-tariffs` (list, repeat flag), `--added-allowed-tariffs` (list, repeat flag), `--removed-allowed-tariffs` (list, repeat flag), `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--allowed-teams` (list, repeat flag), `--added-allowed-teams` (list, repeat flag), `--removed-allowed-teams` (list, repeat flag), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--courses` (list, repeat flag), `--added-courses` (list, repeat flag), `--removed-courses` (list, repeat flag), `--evaluation-order`, `--stop-evaluation-if-rule-is-met`, `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`, `--eligible-time-slots` (JSON array or @filepath), `--time-slots` (JSON array or @filepath)

### ResourceAccessRule (key fields)

`Id`, `Name`, `Active`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `AllowedTariffs`, `AddedAllowedTariffs`, `RemovedAllowedTariffs`, `Members`, `AddedMembers`, `RemovedMembers`, `Teams`, `AddedTeams`, `RemovedTeams`, `AllowedTeams`, `AddedAllowedTeams`, `RemovedAllowedTeams`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `Courses`, `AddedCourses`, `RemovedCourses`

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

<!-- END:GENERATED entity=ResourceAccessRules -->
