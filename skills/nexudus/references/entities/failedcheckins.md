# FailedCheckins

<!-- BEGIN:GENERATED entity=FailedCheckins -->

A **FailedCheckin** records an unsuccessful check-in attempt by a coworker (see `Checkin` entity). Each record captures the coworker involved, the location where the attempt occurred, the reason for the failure, and contextual details such as the coworker's teams and tariff at the time.

Failed check-ins are read-only and generated automatically by the system when a check-in is rejected — for example, due to access restrictions, an inactive plan, or an unrecognised device. Use the `Description` field to inspect the specific failure reason.

The `Source` field indicates how the check-in was initiated (e.g. manual, Wi-Fi, app) and matches the `eCheckinSource` enum used by the `Checkin` entity.

FailedCheckins support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus failedcheckins list --agent` | List all failedcheckins |
| `nexudus failedcheckins list --query "search" --agent` | Search failedcheckins by name |
| `nexudus failedcheckins list --page 2 --size 10 --agent` | Paginated list |
| `nexudus failedcheckins get <id> --agent` | Get single failedcheckin |

### FailedCheckin (key fields)

`Id`, `CoworkerId`, `CoworkerFullName`, `BusinessId`, `BusinessName`

<!-- END:GENERATED entity=FailedCheckins -->
