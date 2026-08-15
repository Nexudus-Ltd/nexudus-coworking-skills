# ExtraServiceTimeSlots

<!-- BEGIN:GENERATED entity=ExtraServiceTimeSlots -->

Time slots define the specific days and time windows when a resource pricing rule is available for booking

ExtraServiceTimeSlots support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus extraservicetimeslots list --agent` | List all extraservicetimeslots |
| `nexudus extraservicetimeslots list --id <id> --agent` | Filter by single ID |
| `nexudus extraservicetimeslots list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus extraservicetimeslots list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus extraservicetimeslots list --from-time <value> --to-time <value> --agent` | Filter extraservicetimeslots by properties |
| `nexudus extraservicetimeslots list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus extraservicetimeslots list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus extraservicetimeslots get <id> --agent` | Get single extraservicetimeslot |
| `nexudus extraservicetimeslots create --extra-service-id <value> --from-time <value> --to-time <value> --day-of-week <value> --agent` | Create extraservicetimeslot |
| `nexudus extraservicetimeslots update <id> --name "New Name" --agent` | Update extraservicetimeslot |
| `nexudus extraservicetimeslots delete <id> --yes --agent` | Delete extraservicetimeslot (no prompt) |

#### ExtraServiceTimeSlot list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--extra-service-id` | long | ID of the extra service linked to this record |
| `--from-time` | DateTime | Start time of the availability window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | End time of the availability window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--day-of-week` | enum | The day of week value for this extra service time slot |
| `--available` | bool | Whether the extra service is available for booking during this time slot. When false, the slot acts as an explicit block. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ExtraServiceTimeSlot sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ExtraServiceTimeSlot create options

| Option | Type | Description |
| --- | --- | --- |
| `--extra-service-id` | long, required | ID of the extra service linked to this record |
| `--from-time` | DateTime, required | Start time of the availability window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--to-time` | DateTime, required | End time of the availability window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--day-of-week` | enum, required | The day of week value for this extra service time slot |
| `--available` | bool | Whether the extra service is available for booking during this time slot. When false, the slot acts as an explicit block. |

#### ExtraServiceTimeSlot update options

| Option | Type | Description |
| --- | --- | --- |
| `--extra-service-id` | long | ID of the extra service linked to this record |
| `--from-time` | DateTime | Start time of the availability window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--to-time` | DateTime | End time of the availability window. Only the time-of-day component is used; the date component is always 1976-01-01. |
| `--day-of-week` | enum | The day of week value for this extra service time slot |
| `--available` | bool | Whether the extra service is available for booking during this time slot. When false, the slot acts as an explicit block. |

### ExtraServiceTimeSlot (key fields)

`Id`, `FromTime`, `ToTime`

#### ExtraServiceTimeSlot enum values

| Option | Valid values |
| ------ | ------------ |
| `--day-of-week` | `0` Sunday, `1` Monday, `2` Tuesday, `3` Wednesday, `4` Thursday, `5` Friday, `6` Saturday |

<!-- END:GENERATED entity=ExtraServiceTimeSlots -->
