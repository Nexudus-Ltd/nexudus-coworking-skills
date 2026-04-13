# ResourceTimeSlots

<!-- BEGIN:GENERATED entity=ResourceTimeSlots -->

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

`--resource-id` (long), `--from-time` (DateTime), `--from-from-time` (range), `--to-from-time` (range), `--to-time` (DateTime), `--from-to-time` (range), `--to-to-time` (range), `--day-of-week` (enum), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ResourceTimeSlot create options

`--resource-id` (long, required), `--from-time` (DateTime, required), `--to-time` (DateTime, required), `--day-of-week` (enum, required)

#### ResourceTimeSlot update options

`--resource-id` (long), `--from-time` (DateTime), `--to-time` (DateTime), `--day-of-week` (enum)

### ResourceTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=ResourceTimeSlots -->
