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
| `nexudus timepasstimeslots create --time-pass-id <value> --from-time <value> --to-time <value> --agent` | Create timepasstimeslot |
| `nexudus timepasstimeslots update <id> --name "New Name" --agent` | Update timepasstimeslot |
| `nexudus timepasstimeslots delete <id> --yes --agent` | Delete timepasstimeslot (no prompt) |

#### TimePassTimeSlot list filter options

`--time-pass-id`, `--from-time`, `--to-time`, `--day-of-week`

#### TimePassTimeSlot create options

`--time-pass-id` (required), `--from-time` (required), `--to-time` (required), `--day-of-week`

#### TimePassTimeSlot update options

`--time-pass-id`, `--from-time`, `--to-time`, `--day-of-week`

### TimePassTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=TimePassTimeSlots -->
