# ResourceAccessRuleTimeSlots

<!-- BEGIN:GENERATED entity=ResourceAccessRuleTimeSlots -->

ResourceAccessRuleTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourceaccessruletimeslots list --agent` | List all resourceaccessruletimeslots |
| `nexudus resourceaccessruletimeslots list --id <id> --agent` | Filter by single ID |
| `nexudus resourceaccessruletimeslots list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resourceaccessruletimeslots list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resourceaccessruletimeslots list --from-time <value> --to-time <value> --agent` | Filter resourceaccessruletimeslots by properties |
| `nexudus resourceaccessruletimeslots list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resourceaccessruletimeslots get <id> --agent` | Get single resourceaccessruletimeslot |
| `nexudus resourceaccessruletimeslots create --resource-access-rule-id <value> --from-time <value> --to-time <value> --day-of-week <value> --agent` | Create resourceaccessruletimeslot |
| `nexudus resourceaccessruletimeslots update <id> --name "New Name" --agent` | Update resourceaccessruletimeslot |
| `nexudus resourceaccessruletimeslots delete <id> --yes --agent` | Delete resourceaccessruletimeslot (no prompt) |

#### ResourceAccessRuleTimeSlot list filter options

`--resource-access-rule-id`, `--from-time`, `--from-from-time` (range), `--to-from-time` (range), `--to-time`, `--from-to-time` (range), `--to-to-time` (range), `--day-of-week`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ResourceAccessRuleTimeSlot create options

`--resource-access-rule-id` (required), `--from-time` (required), `--to-time` (required), `--day-of-week` (required)

#### ResourceAccessRuleTimeSlot update options

`--resource-access-rule-id`, `--from-time`, `--to-time`, `--day-of-week`

### ResourceAccessRuleTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=ResourceAccessRuleTimeSlots -->
