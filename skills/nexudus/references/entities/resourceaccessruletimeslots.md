# ResourceAccessRuleTimeSlots

<!-- BEGIN:GENERATED entity=ResourceAccessRuleTimeSlots -->

ResourceAccessRuleTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourceaccessruletimeslots list --agent` | List all resourceaccessruletimeslots |
| `nexudus resourceaccessruletimeslots list --query "search" --agent` | Search resourceaccessruletimeslots by name |
| `nexudus resourceaccessruletimeslots list --page 2 --size 10 --agent` | Paginated list |
| `nexudus resourceaccessruletimeslots get <id> --agent` | Get single resourceaccessruletimeslot |
| `nexudus resourceaccessruletimeslots create --resource-access-rule-id <value> --from-time <value> --to-time <value> --agent` | Create resourceaccessruletimeslot |
| `nexudus resourceaccessruletimeslots update <id> --name "New Name" --agent` | Update resourceaccessruletimeslot |
| `nexudus resourceaccessruletimeslots delete <id> --yes --agent` | Delete resourceaccessruletimeslot (no prompt) |

#### ResourceAccessRuleTimeSlot create options

`--resource-access-rule-id` (required), `--from-time` (required), `--to-time` (required), `--day-of-week`

#### ResourceAccessRuleTimeSlot update options

`--resource-access-rule-id`, `--from-time`, `--to-time`, `--day-of-week`

### ResourceAccessRuleTimeSlot (key fields)

`Id`, `ResourceAccessRuleId`, `FromTime`, `ToTime`, `DayOfWeek`

<!-- END:GENERATED entity=ResourceAccessRuleTimeSlots -->
