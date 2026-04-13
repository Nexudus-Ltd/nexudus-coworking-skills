# TimePasses

<!-- BEGIN:GENERATED entity=TimePasses -->

Passes allow customers to check in to a coworking space. There are two kinds:

- **Day Pass** — valid for a single calendar day. Created with `--minutes-included` omitted (null). The customer can check in any number of times during that day.
- **Time Pass** — valid across multiple days up to a fixed amount of time. Created with `--minutes-included <minutes>` set. The customer can check in until the included minutes are exhausted.

TimePasses support Search, Get, Create, Update, Delete.
TimePasses also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus timepasses list --agent` | List all timepasses |
| `nexudus timepasses list --id <id> --agent` | Filter by single ID |
| `nexudus timepasses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus timepasses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus timepasses list --name <value> --price <value> --agent` | Filter timepasses by properties |
| `nexudus timepasses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus timepasses get <id> --agent` | Get single timepass |
| `nexudus timepasses create --business-id <value> --name <value> --price <value> --currency-id <value> --agent` | Create timepass |
| `nexudus timepasses update <id> --name "New Name" --agent` | Update timepass |
| `nexudus timepasses delete <id> --yes --agent` | Delete timepass (no prompt) |
| `nexudus timepasses run-command <key> <ids> --agent` | Run entity command |

#### TimePass list filter options

`--business-id` (long), `--name`, `--invoice-display`, `--price` (decimal), `--from-price` (range), `--to-price` (range), `--minutes-included` (int), `--from-minutes-included` (range), `--to-minutes-included` (range), `--counts-towards-plan` (bool), `--payg-members` (bool), `--payg-contacts` (bool), `--use-priority` (int), `--from-use-priority` (range), `--to-use-priority` (range), `--currency-id` (long), `--tax-rate-id` (long), `--reduced-tax-rate-id` (long), `--exempt-tax-rate-id` (long), `--financial-account-id` (long), `--kisi-group-id`, `--door-guard-group-id`, `--access-control-group-id`, `--allow-network-checkin` (bool), `--only-for-contacts` (bool), `--only-for-members` (bool), `--archived` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### TimePass create options

`--business-id` (long, required), `--name` (required), `--invoice-display`, `--price` (decimal, required), `--minutes-included` (int), `--counts-towards-plan` (bool), `--payg-members` (bool), `--payg-contacts` (bool), `--use-priority` (int), `--currency-id` (long, required), `--tax-rate-id` (long), `--reduced-tax-rate-id` (long), `--exempt-tax-rate-id` (long), `--financial-account-id` (long), `--businesses` (list, repeat flag), `--added-businesses` (list, repeat flag), `--removed-businesses` (list, repeat flag), `--kisi-group-id`, `--door-guard-group-id`, `--access-control-group-id`, `--allow-network-checkin` (bool), `--only-for-contacts` (bool), `--only-for-members` (bool), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--archived` (bool)

#### TimePass update options

`--business-id` (long), `--name`, `--invoice-display`, `--price` (decimal), `--minutes-included` (int), `--counts-towards-plan` (bool), `--payg-members` (bool), `--payg-contacts` (bool), `--use-priority` (int), `--currency-id` (long), `--tax-rate-id` (long), `--reduced-tax-rate-id` (long), `--exempt-tax-rate-id` (long), `--financial-account-id` (long), `--businesses` (list, repeat flag), `--added-businesses` (list, repeat flag), `--removed-businesses` (list, repeat flag), `--kisi-group-id`, `--door-guard-group-id`, `--access-control-group-id`, `--allow-network-checkin` (bool), `--only-for-contacts` (bool), `--only-for-members` (bool), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--archived` (bool)

### TimePass (key fields)

`Id`, `BusinessName`, `Name`, `Price`, `MinutesIncluded`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `Archived`

**List properties (only returned by `get`, not by `list`):** `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=TimePasses -->
