# TimePassTimeSlots

<!-- BEGIN:GENERATED entity=TimePassTimeSlots -->

TimePassTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus timepasstimeslots list --agent` | List all timepasstimeslots |
| `nexudus timepasstimeslots list --id <id> --agent` | Filter by single ID |
| `nexudus timepasstimeslots list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus timepasstimeslots list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus timepasstimeslots list --from-time <value> --to-time <value> --agent` | Filter timepasstimeslots by properties |
| `nexudus timepasstimeslots list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus timepasstimeslots get <id> --agent` | Get single timepasstimeslot |
| `nexudus timepasstimeslots create --time-pass-id <value> --from-time <value> --to-time <value> --day-of-week <value> --agent` | Create timepasstimeslot |
| `nexudus timepasstimeslots update <id> --name "New Name" --agent` | Update timepasstimeslot |
| `nexudus timepasstimeslots delete <id> --yes --agent` | Delete timepasstimeslot (no prompt) |

#### TimePassTimeSlot list filter options

`--time-pass-id` (long), `--from-time` (DateTime), `--from-from-time` (range), `--to-from-time` (range), `--to-time` (DateTime), `--from-to-time` (range), `--to-to-time` (range), `--day-of-week` (enum), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### TimePassTimeSlot create options

`--time-pass-id` (long, required), `--from-time` (DateTime, required), `--to-time` (DateTime, required), `--day-of-week` (enum, required)

#### TimePassTimeSlot update options

`--time-pass-id` (long), `--from-time` (DateTime), `--to-time` (DateTime), `--day-of-week` (enum)

### TimePassTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=TimePassTimeSlots -->
