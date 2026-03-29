# ResourceTimeSlots

<!-- BEGIN:GENERATED entity=ResourceTimeSlots -->

ResourceTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourcetimeslots list --agent` | List all resourcetimeslots |
| `nexudus resourcetimeslots list --query "search" --agent` | Search resourcetimeslots by name |
| `nexudus resourcetimeslots list --page 2 --size 10 --agent` | Paginated list |
| `nexudus resourcetimeslots get <id> --agent` | Get single resourcetimeslot |
| `nexudus resourcetimeslots create --resource-id <value> --from-time <value> --to-time <value> --agent` | Create resourcetimeslot |
| `nexudus resourcetimeslots update <id> --name "New Name" --agent` | Update resourcetimeslot |
| `nexudus resourcetimeslots delete <id> --yes --agent` | Delete resourcetimeslot (no prompt) |

#### ResourceTimeSlot create options

`--resource-id` (required), `--from-time` (required), `--to-time` (required), `--day-of-week`

#### ResourceTimeSlot update options

`--resource-id`, `--from-time`, `--to-time`, `--day-of-week`

### ResourceTimeSlot (key fields)

`Id`, `ResourceId`, `FromTime`, `ToTime`, `DayOfWeek`

#### ResourceTimeSlot enum values

| Option | Valid values |
| ------ | ------------ |
| `--day-of-week` | `0` Sunday, `1` Monday, `2` Tuesday, `3` Wednesday, `4` Thursday, `5` Friday, `6` Saturday |

<!-- END:GENERATED entity=ResourceTimeSlots -->
