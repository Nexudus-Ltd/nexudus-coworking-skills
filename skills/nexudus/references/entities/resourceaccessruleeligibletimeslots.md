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
| `nexudus resourceaccessruleeligibletimeslots create --resource-access-rule-id <value> --from-time <value> --to-time <value> --day-of-week <value> --agent` | Create resourceaccessruleeligibletimeslot |
| `nexudus resourceaccessruleeligibletimeslots update <id> --name "New Name" --agent` | Update resourceaccessruleeligibletimeslot |
| `nexudus resourceaccessruleeligibletimeslots delete <id> --yes --agent` | Delete resourceaccessruleeligibletimeslot (no prompt) |

#### ResourceAccessRuleEligibleTimeSlot list filter options

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

#### ResourceAccessRuleEligibleTimeSlot create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-access-rule-id` | long, required |  |
| `--from-time` | DateTime, required | Start time |
| `--to-time` | DateTime, required | End time |
| `--day-of-week` | enum, required |  |

#### ResourceAccessRuleEligibleTimeSlot update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-access-rule-id` | long |  |
| `--from-time` | DateTime | Start time |
| `--to-time` | DateTime | End time |
| `--day-of-week` | enum |  |

### ResourceAccessRuleEligibleTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=ResourceAccessRuleEligibleTimeSlots -->
