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
| `nexudus timepasses list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus timepasses get <id> --agent` | Get single timepass |
| `nexudus timepasses create --business-id <value> --name <value> --price <value> --currency-id <value> --agent` | Create timepass |
| `nexudus timepasses update <id> --name "New Name" --agent` | Update timepass |
| `nexudus timepasses delete <id> --yes --agent` | Delete timepass (no prompt) |
| `nexudus timepasses run-command <key> <ids> --agent` | Run entity command |

#### TimePass list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Time pass name |
| `--invoice-display` | string | Invoice line display text |
| `--price` | decimal | Unit price amount |
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
| `--currency-id` | long | ID of the currency linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--reduced-tax-rate-id` | long | ID of the reduced tax rate linked to this record |
| `--exempt-tax-rate-id` | long | ID of the exempt tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--kisi-group-id` | string | Kisi group ID |
| `--door-guard-group-id` | string | DoorGuard group ID |
| `--access-control-group-id` | string | ID of the access control group associated with this record |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--only-for-contacts` | bool | Only available for contacts |
| `--only-for-members` | bool | Only available for members |
| `--archived` | bool | Whether this time pass is archived and hidden from active lists |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TimePass sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TimePass create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Time pass name |
| `--invoice-display` | string | Invoice line display text |
| `--price` | decimal, required | Unit price amount |
| `--minutes-included` | int | Minutes included |
| `--counts-towards-plan` | bool | Counts towards plan limits |
| `--payg-members` | bool | Use as pay-as-you-go for members |
| `--payg-contacts` | bool | Use as pay-as-you-go for contacts |
| `--use-priority` | int | Use priority |
| `--currency-id` | long, required | ID of the currency linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--reduced-tax-rate-id` | long | ID of the reduced tax rate linked to this record |
| `--exempt-tax-rate-id` | long | ID of the exempt tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--businesses` | list, repeat flag | List of businesses linked to this record |
| `--added-businesses` | list, repeat flag | The added businesses value for this time pass |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this time pass |
| `--kisi-group-id` | string | Kisi group ID |
| `--door-guard-group-id` | string | DoorGuard group ID |
| `--access-control-group-id` | string | ID of the access control group associated with this record |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--only-for-contacts` | bool | Only available for contacts |
| `--only-for-members` | bool | Only available for members |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this time pass |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this time pass |
| `--archived` | bool | Whether this time pass is archived and hidden from active lists |

#### TimePass update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Time pass name |
| `--invoice-display` | string | Invoice line display text |
| `--price` | decimal | Unit price amount |
| `--minutes-included` | int | Minutes included |
| `--counts-towards-plan` | bool | Counts towards plan limits |
| `--payg-members` | bool | Use as pay-as-you-go for members |
| `--payg-contacts` | bool | Use as pay-as-you-go for contacts |
| `--use-priority` | int | Use priority |
| `--currency-id` | long | ID of the currency linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--reduced-tax-rate-id` | long | ID of the reduced tax rate linked to this record |
| `--exempt-tax-rate-id` | long | ID of the exempt tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--businesses` | list, repeat flag | List of businesses linked to this record |
| `--added-businesses` | list, repeat flag | The added businesses value for this time pass |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this time pass |
| `--kisi-group-id` | string | Kisi group ID |
| `--door-guard-group-id` | string | DoorGuard group ID |
| `--access-control-group-id` | string | ID of the access control group associated with this record |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--only-for-contacts` | bool | Only available for contacts |
| `--only-for-members` | bool | Only available for members |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this time pass |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this time pass |
| `--archived` | bool | Whether this time pass is archived and hidden from active lists |

### TimePass (key fields)

`Id`, `BusinessName`, `Name`, `Price`, `MinutesIncluded`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `Archived`

**List properties (only returned by `get`, not by `list`):** `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=TimePasses -->
