# ResourceAccessRuleEligibleTimeSlots

<!-- BEGIN:GENERATED entity=ResourceAccessRuleEligibleTimeSlots -->

ResourceAccessRuleEligibleTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourceaccessruleeligibletimeslots list --agent` | List all resourceaccessruleeligibletimeslots |
| `nexudus resourceaccessruleeligibletimeslots list --query "search" --agent` | Search resourceaccessruleeligibletimeslots by name |
| `nexudus resourceaccessruleeligibletimeslots list --page 2 --size 10 --agent` | Paginated list |
| `nexudus resourceaccessruleeligibletimeslots get <id> --agent` | Get single resourceaccessruleeligibletimeslot |
| `nexudus resourceaccessruleeligibletimeslots create --resource-access-rule-id <value> --from-time <value> --to-time <value> --agent` | Create resourceaccessruleeligibletimeslot |
| `nexudus resourceaccessruleeligibletimeslots update <id> --name "New Name" --agent` | Update resourceaccessruleeligibletimeslot |
| `nexudus resourceaccessruleeligibletimeslots delete <id> --yes --agent` | Delete resourceaccessruleeligibletimeslot (no prompt) |

#### ResourceAccessRuleEligibleTimeSlot create options

`--resource-access-rule-id` (required), `--from-time` (required), `--to-time` (required), `--day-of-week`

#### ResourceAccessRuleEligibleTimeSlot update options

`--resource-access-rule-id`, `--from-time`, `--to-time`, `--day-of-week`

### ResourceAccessRuleEligibleTimeSlot (key fields)

`Id`, `ResourceAccessRuleId`, `FromTime`, `ToTime`, `DayOfWeek`

<!-- END:GENERATED entity=ResourceAccessRuleEligibleTimeSlots -->
