# TimePasses

<!-- BEGIN:GENERATED entity=TimePasses -->

Passes allow customers to check in to a coworking space. There are two kinds:

- **Day Pass** — valid for a single calendar day. Created with `--minutes-included` omitted (null). The customer can check in any number of times during that day.
- **Time Pass** — valid across multiple days up to a fixed amount of time. Created with `--minutes-included <minutes>` set. The customer can check in until the included minutes are exhausted.

TimePasses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus timepasses list --agent` | List all timepasses |
| `nexudus timepasses list --query "search" --agent` | Search timepasses by name |
| `nexudus timepasses list --page 2 --size 10 --agent` | Paginated list |
| `nexudus timepasses get <id> --agent` | Get single timepass |
| `nexudus timepasses create --business <value> --name <value> --agent` | Create timepass |
| `nexudus timepasses update <id> --name "New Name" --agent` | Update timepass |
| `nexudus timepasses delete <id> --yes --agent` | Delete timepass (no prompt) |

#### TimePass create options

`--business` (required), `--name` (required), `--invoice-display`, `--price`, `--minutes-included`, `--counts-towards-plan`, `--payg-members`, `--payg-contacts`, `--use-priority`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--kisi-group-id`, `--door-guard-group-id`, `--allow-network-checkin`, `--only-for-contacts`, `--only-for-members`, `--archived`

#### TimePass update options

`--name`, `--invoice-display`, `--price`, `--minutes-included`, `--counts-towards-plan`, `--payg-members`, `--payg-contacts`, `--use-priority`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--kisi-group-id`, `--door-guard-group-id`, `--allow-network-checkin`, `--only-for-contacts`, `--only-for-members`, `--archived`

### TimePass (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`, `Price`, `MinutesIncluded`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `Archived`

<!-- END:GENERATED entity=TimePasses -->
