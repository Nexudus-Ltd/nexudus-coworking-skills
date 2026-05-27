# ResourceTimeSlots

<!-- BEGIN:GENERATED entity=ResourceTimeSlots -->

A **ResourceTimeSlot** defines the days and times during which a specific resource is available for booking. Each time slot specifies a day of the week and a from/to time window.

ResourceTimeSlots support Search, Get, Create, Update, Delete.
ResourceTimeSlots also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus resourcetimeslots list --agent` | List all resourcetimeslots |
| `nexudus resourcetimeslots list --id <id> --agent` | Filter by single ID |
| `nexudus resourcetimeslots list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resourcetimeslots list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resourcetimeslots list --from-time <value> --to-time <value> --agent` | Filter resourcetimeslots by properties |
| `nexudus resourcetimeslots list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resourcetimeslots get <id> --agent` | Get single resourcetimeslot |
| `nexudus resourcetimeslots create --resource-id <value> --from-time <value> --to-time <value> --day-of-week <value> --agent` | Create resourcetimeslot |
| `nexudus resourcetimeslots update <id> --name "New Name" --agent` | Update resourcetimeslot |
| `nexudus resourcetimeslots delete <id> --yes --agent` | Delete resourcetimeslot (no prompt) |
| `nexudus resourcetimeslots run-command <key> <ids> --agent` | Run entity command |

#### ResourceTimeSlot list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource linked to this record |
| `--from-time` | DateTime | Start time |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | End time |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--day-of-week` | enum | The day of week value for this resource time slot |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ResourceTimeSlot create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required | ID of the resource linked to this record |
| `--from-time` | DateTime, required | Start time |
| `--to-time` | DateTime, required | End time |
| `--day-of-week` | enum, required | The day of week value for this resource time slot |

#### ResourceTimeSlot update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource linked to this record |
| `--from-time` | DateTime | Start time |
| `--to-time` | DateTime | End time |
| `--day-of-week` | enum | The day of week value for this resource time slot |

### ResourceTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

#### ResourceTimeSlot enum values

| Option | Valid values |
| ------ | ------------ |
| `--day-of-week` | `0` Sunday, `1` Monday, `2` Tuesday, `3` Wednesday, `4` Thursday, `5` Friday, `6` Saturday |

<!-- END:GENERATED entity=ResourceTimeSlots -->
