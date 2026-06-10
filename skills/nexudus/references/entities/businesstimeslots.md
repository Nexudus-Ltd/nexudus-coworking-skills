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
| `nexudus businesstimeslots list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus businesstimeslots get <id> --agent` | Get single businesstimeslot |
| `nexudus businesstimeslots create --business-id <value> --from-time <value> --to-time <value> --day-of-week <value> --agent` | Create businesstimeslot |
| `nexudus businesstimeslots update <id> --name "New Name" --agent` | Update businesstimeslot |
| `nexudus businesstimeslots delete <id> --yes --agent` | Delete businesstimeslot (no prompt) |

#### BusinessTimeSlot list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--from-time` | DateTime | Start time of the opening window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | End time of the opening window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--day-of-week` | enum | The day of week value for this business time slot |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BusinessTimeSlot sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### BusinessTimeSlot create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--from-time` | DateTime, required | Start time of the opening window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--to-time` | DateTime, required | End time of the opening window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--day-of-week` | enum, required | The day of week value for this business time slot |

#### BusinessTimeSlot update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--from-time` | DateTime | Start time of the opening window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--to-time` | DateTime | End time of the opening window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--day-of-week` | enum | The day of week value for this business time slot |

### BusinessTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

#### BusinessTimeSlot enum values

| Option | Valid values |
| ------ | ------------ |
| `--day-of-week` | `0` Sunday, `1` Monday, `2` Tuesday, `3` Wednesday, `4` Thursday, `5` Friday, `6` Saturday |

<!-- END:GENERATED entity=BusinessTimeSlots -->
