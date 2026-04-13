# Checkins

<!-- BEGIN:GENERATED entity=Checkins -->

A **Checkin** records when a customer accessed a location. To check in, a customer must hold a valid pass (`TimePass` entity) that covers the location and the time of the check-in.

If the customer does not have a valid pass but the location or network has one or more **Pay As You Go** passes configured, a pass is automatically assigned and charged to the customer at check-in time.

Check-ins can be created manually, or opened and closed automatically by **NexIO** (the front-desk Nexudus tablet app), door-access systems, or IT-network integrations. The `Source` field indicates how the check-in was created.

Checkins support Search, Get, Create, Update, Delete.
Checkins also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus checkins list --agent` | List all checkins |
| `nexudus checkins list --id <id> --agent` | Filter by single ID |
| `nexudus checkins list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus checkins list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus checkins list --from-time <value> --to-time <value> --agent` | Filter checkins by properties |
| `nexudus checkins list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus checkins get <id> --agent` | Get single checkin |
| `nexudus checkins create --business-id <value> --from-time <value> --agent` | Create checkin |
| `nexudus checkins update <id> --name "New Name" --agent` | Update checkin |
| `nexudus checkins delete <id> --yes --agent` | Delete checkin (no prompt) |
| `nexudus checkins run-command <key> <ids> --agent` | Run entity command |

#### Checkin list filter options

`--coworker-id` (long), `--business-id` (long), `--from-time` (DateTime), `--from-from-time` (range), `--to-from-time` (range), `--to-time` (DateTime), `--from-to-time` (range), `--to-to-time` (range), `--counts-towards-plan-limits` (bool), `--coworker-time-pass-guid`, `--auto-checkout` (bool), `--last-activity` (DateTime), `--from-last-activity` (range), `--to-last-activity` (range), `--mac-addresses`, `--teams-at-checkin`, `--tariff-at-checkin`, `--validate-checkin-job-id`, `--from-time-local` (DateTime), `--from-from-time-local` (range), `--to-from-time-local` (range), `--to-time-local` (DateTime), `--from-to-time-local` (range), `--to-to-time-local` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Checkin create options

`--coworker-id` (long), `--business-id` (long, required), `--from-time` (DateTime, required), `--to-time` (DateTime), `--counts-towards-plan-limits` (bool), `--coworker-time-pass-guid`, `--auto-checkout` (bool), `--last-activity` (DateTime), `--mac-addresses`, `--teams-at-checkin`, `--tariff-at-checkin`, `--validate-checkin-job-id`, `--from-time-local` (DateTime), `--to-time-local` (DateTime)

#### Checkin update options

`--coworker-id` (long), `--business-id` (long), `--from-time` (DateTime), `--to-time` (DateTime), `--counts-towards-plan-limits` (bool), `--coworker-time-pass-guid`, `--auto-checkout` (bool), `--last-activity` (DateTime), `--mac-addresses`, `--teams-at-checkin`, `--tariff-at-checkin`, `--validate-checkin-job-id`, `--from-time-local` (DateTime), `--to-time-local` (DateTime)

### Checkin (key fields)

`Id`, `CoworkerFullName`, `BusinessName`, `Source`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=Checkins -->
