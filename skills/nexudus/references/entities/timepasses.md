# TimePasses

<!-- BEGIN:GENERATED entity=TimePasses -->

A Pass (internally TimePass) is a prepaid check-in allowance for a location, configured as either a day pass or a time-limited pass with availability, customer, pricing, and access-control rules.

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
| `--business-id` | long | ID of the location that owns this pass and supplies its default location scope and local check-in schedule. |
| `--name` | string | Required pass name, up to 254 characters; this is the customer-facing name used to identify the pass. |
| `--invoice-display` | string | Optional custom text shown on invoice lines instead of the pass name. |
| `--price` | decimal | Base amount charged in the selected currency; the lowest matching plan-specific special price overrides this amount for eligible members. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--minutes-included` | int | Non-negative total check-in allowance in minutes; leave null for a day pass that can be used repeatedly during one calendar day. |
| `--from-minutes-included` | range | |
| `--to-minutes-included` | range | |
| `--counts-towards-plan` | bool | Whether check-ins made with this pass count against the customer's plan check-in and time limits. |
| `--payg-members` | bool | Whether this pass can be automatically sold to members who check in without a valid pass when pay-as-you-go check-in is enabled. |
| `--payg-contacts` | bool | Whether this pass can be automatically sold to contacts without an active contract who check in without a valid pass when pay-as-you-go check-in is enabled. |
| `--use-priority` | int | Optional pass-selection priority when a customer has multiple valid passes; higher values are used first and null is treated as normal priority (0). |
| `--from-use-priority` | range | |
| `--to-use-priority` | range | |
| `--currency-id` | long | ID of the ISO 4217 currency used for the pass price and plan-specific special prices. |
| `--tax-rate-id` | long | Optional ID of the standard tax rate applied when this pass is invoiced. |
| `--reduced-tax-rate-id` | long | Optional ID of the reduced tax rate applied when the customer qualifies for reduced taxation. |
| `--exempt-tax-rate-id` | long | Optional ID of the tax rate applied when the customer is tax exempt. |
| `--financial-account-id` | long | Optional ID of the financial account used to record pass revenue. |
| `--kisi-group-id` | string | Optional external Kisi access-control group ID assigned to customers using this pass. |
| `--door-guard-group-id` | string | Optional external DoorGuard access-control group ID assigned to customers using this pass. |
| `--access-control-group-id` | string | Legacy single access-control group ID; do not use this field because provider-specific access groups are managed through the current access-control integration. |
| `--allow-network-checkin` | bool | Whether a customer holding this pass can check in to the location's connected IT network. |
| `--only-for-contacts` | bool | Whether this pass is restricted to contacts without an active contract; do not combine with OnlyForMembers. |
| `--only-for-members` | bool | Whether this pass is restricted to members with an active contract; when Tariffs is non-empty, the member must have an active contract on one of those plans, and this must not be combined with OnlyForContacts. |
| `--archived` | bool | Whether this pass is archived and should no longer appear in active pass lists. |
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
| `--business-id` | long, required | ID of the location that owns this pass and supplies its default location scope and local check-in schedule. |
| `--name` | string, required | Required pass name, up to 254 characters; this is the customer-facing name used to identify the pass. |
| `--invoice-display` | string | Optional custom text shown on invoice lines instead of the pass name. |
| `--price` | decimal, required | Base amount charged in the selected currency; the lowest matching plan-specific special price overrides this amount for eligible members. |
| `--minutes-included` | int | Non-negative total check-in allowance in minutes; leave null for a day pass that can be used repeatedly during one calendar day. |
| `--counts-towards-plan` | bool | Whether check-ins made with this pass count against the customer's plan check-in and time limits. |
| `--payg-members` | bool | Whether this pass can be automatically sold to members who check in without a valid pass when pay-as-you-go check-in is enabled. |
| `--payg-contacts` | bool | Whether this pass can be automatically sold to contacts without an active contract who check in without a valid pass when pay-as-you-go check-in is enabled. |
| `--use-priority` | int | Optional pass-selection priority when a customer has multiple valid passes; higher values are used first and null is treated as normal priority (0). |
| `--currency-id` | long, required | ID of the ISO 4217 currency used for the pass price and plan-specific special prices. |
| `--tax-rate-id` | long | Optional ID of the standard tax rate applied when this pass is invoiced. |
| `--reduced-tax-rate-id` | long | Optional ID of the reduced tax rate applied when the customer qualifies for reduced taxation. |
| `--exempt-tax-rate-id` | long | Optional ID of the tax rate applied when the customer is tax exempt. |
| `--financial-account-id` | long | Optional ID of the financial account used to record pass revenue. |
| `--businesses` | list, repeat flag | List of locations where this pass can be used; when empty, it is valid at the owning location and its child locations, while a non-empty list restricts use to those locations. |
| `--added-businesses` | list, repeat flag | The added businesses value for this time pass |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this time pass |
| `--kisi-group-id` | string | Optional external Kisi access-control group ID assigned to customers using this pass. |
| `--door-guard-group-id` | string | Optional external DoorGuard access-control group ID assigned to customers using this pass. |
| `--access-control-group-id` | string | Legacy single access-control group ID; do not use this field because provider-specific access groups are managed through the current access-control integration. |
| `--allow-network-checkin` | bool | Whether a customer holding this pass can check in to the location's connected IT network. |
| `--only-for-contacts` | bool | Whether this pass is restricted to contacts without an active contract; do not combine with OnlyForMembers. |
| `--only-for-members` | bool | Whether this pass is restricted to members with an active contract; when Tariffs is non-empty, the member must have an active contract on one of those plans, and this must not be combined with OnlyForContacts. |
| `--tariffs` | list, repeat flag | List of plans whose active members can use this pass when OnlyForMembers is true; an empty list allows members on any plan. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this time pass |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this time pass |
| `--archived` | bool | Whether this pass is archived and should no longer appear in active pass lists. |

#### TimePass update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this pass and supplies its default location scope and local check-in schedule. |
| `--name` | string | Required pass name, up to 254 characters; this is the customer-facing name used to identify the pass. |
| `--invoice-display` | string | Optional custom text shown on invoice lines instead of the pass name. |
| `--price` | decimal | Base amount charged in the selected currency; the lowest matching plan-specific special price overrides this amount for eligible members. |
| `--minutes-included` | int | Non-negative total check-in allowance in minutes; leave null for a day pass that can be used repeatedly during one calendar day. |
| `--counts-towards-plan` | bool | Whether check-ins made with this pass count against the customer's plan check-in and time limits. |
| `--payg-members` | bool | Whether this pass can be automatically sold to members who check in without a valid pass when pay-as-you-go check-in is enabled. |
| `--payg-contacts` | bool | Whether this pass can be automatically sold to contacts without an active contract who check in without a valid pass when pay-as-you-go check-in is enabled. |
| `--use-priority` | int | Optional pass-selection priority when a customer has multiple valid passes; higher values are used first and null is treated as normal priority (0). |
| `--currency-id` | long | ID of the ISO 4217 currency used for the pass price and plan-specific special prices. |
| `--tax-rate-id` | long | Optional ID of the standard tax rate applied when this pass is invoiced. |
| `--reduced-tax-rate-id` | long | Optional ID of the reduced tax rate applied when the customer qualifies for reduced taxation. |
| `--exempt-tax-rate-id` | long | Optional ID of the tax rate applied when the customer is tax exempt. |
| `--financial-account-id` | long | Optional ID of the financial account used to record pass revenue. |
| `--businesses` | list, repeat flag | List of locations where this pass can be used; when empty, it is valid at the owning location and its child locations, while a non-empty list restricts use to those locations. |
| `--added-businesses` | list, repeat flag | The added businesses value for this time pass |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this time pass |
| `--kisi-group-id` | string | Optional external Kisi access-control group ID assigned to customers using this pass. |
| `--door-guard-group-id` | string | Optional external DoorGuard access-control group ID assigned to customers using this pass. |
| `--access-control-group-id` | string | Legacy single access-control group ID; do not use this field because provider-specific access groups are managed through the current access-control integration. |
| `--allow-network-checkin` | bool | Whether a customer holding this pass can check in to the location's connected IT network. |
| `--only-for-contacts` | bool | Whether this pass is restricted to contacts without an active contract; do not combine with OnlyForMembers. |
| `--only-for-members` | bool | Whether this pass is restricted to members with an active contract; when Tariffs is non-empty, the member must have an active contract on one of those plans, and this must not be combined with OnlyForContacts. |
| `--tariffs` | list, repeat flag | List of plans whose active members can use this pass when OnlyForMembers is true; an empty list allows members on any plan. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this time pass |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this time pass |
| `--archived` | bool | Whether this pass is archived and should no longer appear in active pass lists. |

### TimePass (key fields)

`Id`, `BusinessName`, `Name`, `Price`, `MinutesIncluded`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `Archived`

**List properties (only returned by `get`, not by `list`):** `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=TimePasses -->
