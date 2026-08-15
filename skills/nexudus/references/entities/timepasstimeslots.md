# TimePassTimeSlots

<!-- BEGIN:GENERATED entity=TimePassTimeSlots -->

A TimePassTimeSlot defines the days and times during which a time pass can be used. Each time slot specifies a day of the week and a from/to time window that restricts when the pass is valid. Time values are stored in UTC. The base date is 1976-01-01 but the actual stored date depends on the time zone offset (e.g., 1975-12-31 for time zones ahead of UTC). Always convert local times to UTC before creating time slots.

TimePassTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus timepasstimeslots list --agent` | List all timepasstimeslots |
| `nexudus timepasstimeslots list --id <id> --agent` | Filter by single ID |
| `nexudus timepasstimeslots list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus timepasstimeslots list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus timepasstimeslots list --from-time <value> --to-time <value> --agent` | Filter timepasstimeslots by properties |
| `nexudus timepasstimeslots list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus timepasstimeslots list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus timepasstimeslots get <id> --agent` | Get single timepasstimeslot |
| `nexudus timepasstimeslots create --time-pass-id <value> --from-time <value> --to-time <value> --day-of-week <value> --agent` | Create timepasstimeslot |
| `nexudus timepasstimeslots update <id> --name "New Name" --agent` | Update timepasstimeslot |
| `nexudus timepasstimeslots delete <id> --yes --agent` | Delete timepasstimeslot (no prompt) |

#### TimePassTimeSlot list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--time-pass-id` | long | ID of the time pass linked to this record |
| `--from-time` | DateTime | Start time, stored in UTC. The base date is 1976-01-01 but the actual date depends on the time zone offset. |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | End time, stored in UTC. The base date is 1976-01-01 but the actual date depends on the time zone offset. |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--day-of-week` | enum | The day of week value for this time pass time slot |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TimePassTimeSlot sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TimePassTimeSlot create options

| Option | Type | Description |
| --- | --- | --- |
| `--time-pass-id` | long, required | ID of the time pass linked to this record |
| `--from-time` | DateTime, required | Start time, stored in UTC. The base date is 1976-01-01 but the actual date depends on the time zone offset. |
| `--to-time` | DateTime, required | End time, stored in UTC. The base date is 1976-01-01 but the actual date depends on the time zone offset. |
| `--day-of-week` | enum, required | The day of week value for this time pass time slot |

#### TimePassTimeSlot update options

| Option | Type | Description |
| --- | --- | --- |
| `--time-pass-id` | long | ID of the time pass linked to this record |
| `--from-time` | DateTime | Start time, stored in UTC. The base date is 1976-01-01 but the actual date depends on the time zone offset. |
| `--to-time` | DateTime | End time, stored in UTC. The base date is 1976-01-01 but the actual date depends on the time zone offset. |
| `--day-of-week` | enum | The day of week value for this time pass time slot |

### TimePassTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

#### TimePassTimeSlot enum values

| Option | Valid values |
| ------ | ------------ |
| `--day-of-week` | `0` Sunday, `1` Monday, `2` Tuesday, `3` Wednesday, `4` Thursday, `5` Friday, `6` Saturday |

<!-- END:GENERATED entity=TimePassTimeSlots -->
