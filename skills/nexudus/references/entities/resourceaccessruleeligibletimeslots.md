# ResourceAccessRuleEligibleTimeSlots

<!-- BEGIN:GENERATED entity=ResourceAccessRuleEligibleTimeSlots -->

ResourceAccessRuleEligibleTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourceaccessruleeligibletimeslots list --agent` | List all resourceaccessruleeligibletimeslots |
| `nexudus resourceaccessruleeligibletimeslots list --id <id> --agent` | Filter by single ID |
| `nexudus resourceaccessruleeligibletimeslots list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resourceaccessruleeligibletimeslots list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resourceaccessruleeligibletimeslots list --from-time <value> --to-time <value> --agent` | Filter resourceaccessruleeligibletimeslots by properties |
| `nexudus resourceaccessruleeligibletimeslots list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resourceaccessruleeligibletimeslots get <id> --agent` | Get single resourceaccessruleeligibletimeslot |
| `nexudus resourceaccessruleeligibletimeslots create --resource-access-rule-id <value> --from-time <value> --to-time <value> --agent` | Create resourceaccessruleeligibletimeslot |
| `nexudus resourceaccessruleeligibletimeslots update <id> --name "New Name" --agent` | Update resourceaccessruleeligibletimeslot |
| `nexudus resourceaccessruleeligibletimeslots delete <id> --yes --agent` | Delete resourceaccessruleeligibletimeslot (no prompt) |

#### ResourceAccessRuleEligibleTimeSlot list filter options

`--resource-access-rule-id`, `--from-time`, `--to-time`, `--day-of-week`

#### ResourceAccessRuleEligibleTimeSlot create options

`--resource-access-rule-id` (required), `--from-time` (required), `--to-time` (required), `--day-of-week`

#### ResourceAccessRuleEligibleTimeSlot update options

`--resource-access-rule-id`, `--from-time`, `--to-time`, `--day-of-week`

### ResourceAccessRuleEligibleTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=ResourceAccessRuleEligibleTimeSlots -->
