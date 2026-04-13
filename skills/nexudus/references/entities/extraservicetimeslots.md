# ExtraServiceTimeSlots

<!-- BEGIN:GENERATED entity=ExtraServiceTimeSlots -->

An **ExtraServiceTimeSlot** defines the days and times during which an `ExtraService` (resource pricing rule) is available for booking. Each time slot specifies a day of the week and a from/to time window.

The year, month, and day components of `FromTime` and `ToTime` are always `1976-01-01` — only the time-of-day portion is meaningful.

When no time slots are defined for an extra service, the price applies at all times. Adding time slots restricts the price to the specified windows only.

ExtraServiceTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus extraservicetimeslots list --agent` | List all extraservicetimeslots |
| `nexudus extraservicetimeslots list --id <id> --agent` | Filter by single ID |
| `nexudus extraservicetimeslots list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus extraservicetimeslots list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus extraservicetimeslots list --from-time <value> --to-time <value> --agent` | Filter extraservicetimeslots by properties |
| `nexudus extraservicetimeslots list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus extraservicetimeslots get <id> --agent` | Get single extraservicetimeslot |
| `nexudus extraservicetimeslots create --extra-service-id <value> --from-time <value> --to-time <value> --day-of-week <value> --agent` | Create extraservicetimeslot |
| `nexudus extraservicetimeslots update <id> --name "New Name" --agent` | Update extraservicetimeslot |
| `nexudus extraservicetimeslots delete <id> --yes --agent` | Delete extraservicetimeslot (no prompt) |

#### ExtraServiceTimeSlot list filter options

`--extra-service-id` (long), `--from-time` (DateTime), `--from-from-time` (range), `--to-from-time` (range), `--to-time` (DateTime), `--from-to-time` (range), `--to-to-time` (range), `--day-of-week` (enum), `--available` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ExtraServiceTimeSlot create options

`--extra-service-id` (long, required), `--from-time` (DateTime, required), `--to-time` (DateTime, required), `--day-of-week` (enum, required), `--available` (bool)

#### ExtraServiceTimeSlot update options

`--extra-service-id` (long), `--from-time` (DateTime), `--to-time` (DateTime), `--day-of-week` (enum), `--available` (bool)

### ExtraServiceTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=ExtraServiceTimeSlots -->
