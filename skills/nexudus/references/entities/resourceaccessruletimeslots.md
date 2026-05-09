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

| Option | Type | Description |
| --- | --- | --- |
| `--resource-access-rule-id` | long |  |
| `--from-time` | DateTime | Start time |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | End time |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--day-of-week` | enum |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ResourceAccessRuleTimeSlot create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-access-rule-id` | long, required |  |
| `--from-time` | DateTime, required | Start time |
| `--to-time` | DateTime, required | End time |
| `--day-of-week` | enum, required |  |

#### ResourceAccessRuleTimeSlot update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-access-rule-id` | long |  |
| `--from-time` | DateTime | Start time |
| `--to-time` | DateTime | End time |
| `--day-of-week` | enum |  |

### ResourceAccessRuleTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=ResourceAccessRuleTimeSlots -->
