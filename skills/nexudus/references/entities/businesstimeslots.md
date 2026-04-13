# BusinessTimeSlots

<!-- BEGIN:GENERATED entity=BusinessTimeSlots -->

A **BusinessTimeSlot** defines the days and times during which a location is open. Each time slot specifies a day of the week and a from/to time window.

The year, month, and day components of `FromTime` and `ToTime` are always `1976-01-01` — only the time-of-day portion is meaningful.

When no time slots are defined for a location, the location is considered open at all times. Adding time slots restricts opening hours to the specified windows only.

BusinessTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus businesstimeslots list --agent` | List all businesstimeslots |
| `nexudus businesstimeslots list --id <id> --agent` | Filter by single ID |
| `nexudus businesstimeslots list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus businesstimeslots list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus businesstimeslots list --from-time <value> --to-time <value> --agent` | Filter businesstimeslots by properties |
| `nexudus businesstimeslots list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus businesstimeslots get <id> --agent` | Get single businesstimeslot |
| `nexudus businesstimeslots create --business-id <value> --from-time <value> --to-time <value> --day-of-week <value> --agent` | Create businesstimeslot |
| `nexudus businesstimeslots update <id> --name "New Name" --agent` | Update businesstimeslot |
| `nexudus businesstimeslots delete <id> --yes --agent` | Delete businesstimeslot (no prompt) |

#### BusinessTimeSlot list filter options

`--business-id` (long), `--from-time` (DateTime), `--from-from-time` (range), `--to-from-time` (range), `--to-time` (DateTime), `--from-to-time` (range), `--to-to-time` (range), `--day-of-week` (enum), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BusinessTimeSlot create options

`--business-id` (long, required), `--from-time` (DateTime, required), `--to-time` (DateTime, required), `--day-of-week` (enum, required)

#### BusinessTimeSlot update options

`--business-id` (long), `--from-time` (DateTime), `--to-time` (DateTime), `--day-of-week` (enum)

### BusinessTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=BusinessTimeSlots -->
