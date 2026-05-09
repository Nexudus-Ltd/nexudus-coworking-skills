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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Time pass name |
| `--invoice-display` | string | Invoice line display text |
| `--price` | decimal | Price |
| `--from-price` | range | |
| `--to-price` | range | |
| `--minutes-included` | int | Minutes included |
| `--from-minutes-included` | range | |
| `--to-minutes-included` | range | |
| `--counts-towards-plan` | bool | Counts towards plan limits |
| `--payg-members` | bool | Use as pay-as-you-go for members |
| `--payg-contacts` | bool | Use as pay-as-you-go for contacts |
| `--use-priority` | int | Use priority |
| `--from-use-priority` | range | |
| `--to-use-priority` | range | |
| `--currency-id` | long |  |
| `--tax-rate-id` | long |  |
| `--reduced-tax-rate-id` | long |  |
| `--exempt-tax-rate-id` | long |  |
| `--financial-account-id` | long |  |
| `--kisi-group-id` | string | Kisi group ID |
| `--door-guard-group-id` | string | DoorGuard group ID |
| `--access-control-group-id` | string |  |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--only-for-contacts` | bool | Only available for contacts |
| `--only-for-members` | bool | Only available for members |
| `--archived` | bool | Archived |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TimePass create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required | Time pass name |
| `--invoice-display` | string | Invoice line display text |
| `--price` | decimal, required | Price |
| `--minutes-included` | int | Minutes included |
| `--counts-towards-plan` | bool | Counts towards plan limits |
| `--payg-members` | bool | Use as pay-as-you-go for members |
| `--payg-contacts` | bool | Use as pay-as-you-go for contacts |
| `--use-priority` | int | Use priority |
| `--currency-id` | long, required |  |
| `--tax-rate-id` | long |  |
| `--reduced-tax-rate-id` | long |  |
| `--exempt-tax-rate-id` | long |  |
| `--financial-account-id` | long |  |
| `--businesses` | list, repeat flag |  |
| `--added-businesses` | list, repeat flag |  |
| `--removed-businesses` | list, repeat flag |  |
| `--kisi-group-id` | string | Kisi group ID |
| `--door-guard-group-id` | string | DoorGuard group ID |
| `--access-control-group-id` | string |  |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--only-for-contacts` | bool | Only available for contacts |
| `--only-for-members` | bool | Only available for members |
| `--tariffs` | list, repeat flag |  |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--archived` | bool | Archived |

#### TimePass update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Time pass name |
| `--invoice-display` | string | Invoice line display text |
| `--price` | decimal | Price |
| `--minutes-included` | int | Minutes included |
| `--counts-towards-plan` | bool | Counts towards plan limits |
| `--payg-members` | bool | Use as pay-as-you-go for members |
| `--payg-contacts` | bool | Use as pay-as-you-go for contacts |
| `--use-priority` | int | Use priority |
| `--currency-id` | long |  |
| `--tax-rate-id` | long |  |
| `--reduced-tax-rate-id` | long |  |
| `--exempt-tax-rate-id` | long |  |
| `--financial-account-id` | long |  |
| `--businesses` | list, repeat flag |  |
| `--added-businesses` | list, repeat flag |  |
| `--removed-businesses` | list, repeat flag |  |
| `--kisi-group-id` | string | Kisi group ID |
| `--door-guard-group-id` | string | DoorGuard group ID |
| `--access-control-group-id` | string |  |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--only-for-contacts` | bool | Only available for contacts |
| `--only-for-members` | bool | Only available for members |
| `--tariffs` | list, repeat flag |  |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--archived` | bool | Archived |

### TimePass (key fields)

`Id`, `BusinessName`, `Name`, `Price`, `MinutesIncluded`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `Archived`

**List properties (only returned by `get`, not by `list`):** `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=TimePasses -->
