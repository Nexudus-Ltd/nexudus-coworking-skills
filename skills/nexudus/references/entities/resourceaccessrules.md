# ResourceAccessRules

<!-- BEGIN:GENERATED entity=ResourceAccessRules -->

ResourceAccessRules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourceaccessrules list --agent` | List all resourceaccessrules |
| `nexudus resourceaccessrules list --query "search" --agent` | Search resourceaccessrules by name |
| `nexudus resourceaccessrules list --page 2 --size 10 --agent` | Paginated list |
| `nexudus resourceaccessrules get <id> --agent` | Get single resourceaccessrule |
| `nexudus resourceaccessrules create --resource-id <value> --name <value> --agent` | Create resourceaccessrule |
| `nexudus resourceaccessrules update <id> --name "New Name" --agent` | Update resourceaccessrule |
| `nexudus resourceaccessrules delete <id> --yes --agent` | Delete resourceaccessrule (no prompt) |

#### ResourceAccessRule create options

`--resource-id` (required), `--name` (required), `--active`, `--only-for-contacts`, `--apply-rule-from`, `--apply-rule-to`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--max-booking-length`, `--min-booking-length`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--reject-with-message`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--allowed-tariffs` (list, repeat flag), `--added-allowed-tariffs` (list, repeat flag), `--removed-allowed-tariffs` (list, repeat flag), `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--allowed-teams` (list, repeat flag), `--added-allowed-teams` (list, repeat flag), `--removed-allowed-teams` (list, repeat flag), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--courses` (list, repeat flag), `--added-courses` (list, repeat flag), `--removed-courses` (list, repeat flag), `--evaluation-order`, `--stop-evaluation-if-rule-is-met`, `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`

#### ResourceAccessRule update options

`--resource-id`, `--name`, `--active`, `--only-for-contacts`, `--apply-rule-from`, `--apply-rule-to`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--max-booking-length`, `--min-booking-length`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--reject-with-message`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--allowed-tariffs` (list, repeat flag), `--added-allowed-tariffs` (list, repeat flag), `--removed-allowed-tariffs` (list, repeat flag), `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--allowed-teams` (list, repeat flag), `--added-allowed-teams` (list, repeat flag), `--removed-allowed-teams` (list, repeat flag), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--courses` (list, repeat flag), `--added-courses` (list, repeat flag), `--removed-courses` (list, repeat flag), `--evaluation-order`, `--stop-evaluation-if-rule-is-met`, `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`

### ResourceAccessRule (key fields)

`Id`, `ResourceId`, `Name`, `Active`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `AllowedTariffs`, `AddedAllowedTariffs`, `RemovedAllowedTariffs`, `Members`, `AddedMembers`, `RemovedMembers`, `Teams`, `AddedTeams`, `RemovedTeams`, `AllowedTeams`, `AddedAllowedTeams`, `RemovedAllowedTeams`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `Courses`, `AddedCourses`, `RemovedCourses`

<!-- END:GENERATED entity=ResourceAccessRules -->
