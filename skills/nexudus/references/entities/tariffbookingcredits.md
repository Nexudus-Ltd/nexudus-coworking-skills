# TariffBookingCredits

<!-- BEGIN:GENERATED entity=TariffBookingCredits -->

Plan booking credit (internally TariffBookingCredit) represents an amount of monetary credit linked to a plan (internally Tariff). The `Credit` value specifies how much credit is included. The renewal time controls how often the credit expires and the allowance resets.

TariffBookingCredits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffbookingcredits list --agent` | List all tariffbookingcredits |
| `nexudus tariffbookingcredits list --id <id> --agent` | Filter by single ID |
| `nexudus tariffbookingcredits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffbookingcredits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffbookingcredits list --name <value> --tariff-name <value> --agent` | Filter tariffbookingcredits by properties |
| `nexudus tariffbookingcredits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffbookingcredits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus tariffbookingcredits get <id> --agent` | Get single tariffbookingcredit |
| `nexudus tariffbookingcredits create --name <value> --tariff-id <value> --credit <value> --service-renewal-time <value> --agent` | Create tariffbookingcredit |
| `nexudus tariffbookingcredits update <id> --name "New Name" --agent` | Update tariffbookingcredit |
| `nexudus tariffbookingcredits delete <id> --yes --agent` | Delete tariffbookingcredit (no prompt) |

#### TariffBookingCredit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Credit name |
| `--tariff-id` | long | ID of the plan linked to this record |
| `--tariff-name` | string | Tariff name |
| `--tariff-business-currency-code` | string | Tariff business currency code |
| `--credit` | decimal | Credit amount |
| `--from-credit` | range | |
| `--to-credit` | range | |
| `--can-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types using elegible-resource-types |
| `--can-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with ElegibleResourceTypes |
| `--service-renewal-time` | enum | How often will this credit amount will expire and be issued again. Most common option is TariffMonth, which follows the plan renewal cycle. |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with ElegibleProducts, ElegiblePasses and AppliesToCharges; if all are empty the credit applies to all products, passes and charges |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TariffBookingCredit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TariffBookingCredit create options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string, required | Credit name |
| `--tariff-id` | long, required | ID of the plan linked to this record |
| `--elegible-resource-types` | list, repeat flag | List of the IDs of the resource types this booking credit can be used for |
| `--added-elegible-resource-types` | list, repeat flag | The added elegible resource types value for this tariff booking credit |
| `--removed-elegible-resource-types` | list, repeat flag | The removed elegible resource types value for this tariff booking credit |
| `--elegible-products` | list, repeat flag | List of the IDs of the products this booking credit can be used for. Applies only when IsUniversalCredit is true. |
| `--added-elegible-products` | list, repeat flag | The added elegible products value for this tariff booking credit |
| `--removed-elegible-products` | list, repeat flag | The removed elegible products value for this tariff booking credit |
| `--elegible-tariffs` | list, repeat flag | List of the IDs of the plans this booking credit can be used for. Applies only when IsUniversalCredit is true. |
| `--added-elegible-tariffs` | list, repeat flag | The added elegible tariffs value for this tariff booking credit |
| `--removed-elegible-tariffs` | list, repeat flag | The removed elegible tariffs value for this tariff booking credit |
| `--credit` | decimal, required | Credit amount |
| `--can-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types using elegible-resource-types |
| `--can-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with ElegibleResourceTypes |
| `--event-categories` | list, repeat flag | List of the IDs of the event categories this booking credit can be used for. Applies only when IsUniversalCredit is true. |
| `--added-event-categories` | list, repeat flag | The added event categories value for this tariff booking credit |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this tariff booking credit |
| `--service-renewal-time` | enum, required | How often will this credit amount will expire and be issued again. Most common option is TariffMonth, which follows the plan renewal cycle. |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with ElegibleProducts, ElegiblePasses and AppliesToCharges; if all are empty the credit applies to all products, passes and charges |
| `--elegible-passes` | list, repeat flag | List of the IDs of the passes this booking credit can be used for. Applies only when IsUniversalCredit is true. |
| `--added-elegible-passes` | list, repeat flag | The added elegible passes value for this tariff booking credit |
| `--removed-elegible-passes` | list, repeat flag | The removed elegible passes value for this tariff booking credit |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges |

#### TariffBookingCredit update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Credit name |
| `--tariff-id` | long | ID of the plan linked to this record |
| `--elegible-resource-types` | list, repeat flag | List of the IDs of the resource types this booking credit can be used for |
| `--added-elegible-resource-types` | list, repeat flag | The added elegible resource types value for this tariff booking credit |
| `--removed-elegible-resource-types` | list, repeat flag | The removed elegible resource types value for this tariff booking credit |
| `--elegible-products` | list, repeat flag | List of the IDs of the products this booking credit can be used for. Applies only when IsUniversalCredit is true. |
| `--added-elegible-products` | list, repeat flag | The added elegible products value for this tariff booking credit |
| `--removed-elegible-products` | list, repeat flag | The removed elegible products value for this tariff booking credit |
| `--elegible-tariffs` | list, repeat flag | List of the IDs of the plans this booking credit can be used for. Applies only when IsUniversalCredit is true. |
| `--added-elegible-tariffs` | list, repeat flag | The added elegible tariffs value for this tariff booking credit |
| `--removed-elegible-tariffs` | list, repeat flag | The removed elegible tariffs value for this tariff booking credit |
| `--credit` | decimal | Credit amount |
| `--can-be-used-for-bookings` | bool | Whether this credit can be used to pay for bookings. Restrict to specific resource types using elegible-resource-types |
| `--can-be-used-for-events` | bool | Whether this credit can be used to pay for event sign-ups. Restrict to specific categories with ElegibleResourceTypes |
| `--event-categories` | list, repeat flag | List of the IDs of the event categories this booking credit can be used for. Applies only when IsUniversalCredit is true. |
| `--added-event-categories` | list, repeat flag | The added event categories value for this tariff booking credit |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this tariff booking credit |
| `--service-renewal-time` | enum | How often will this credit amount will expire and be issued again. Most common option is TariffMonth, which follows the plan renewal cycle. |
| `--is-universal-credit` | bool | Whether this is a universal credit applicable to products, time passes and other charges. Restrict with ElegibleProducts, ElegiblePasses and AppliesToCharges; if all are empty the credit applies to all products, passes and charges |
| `--elegible-passes` | list, repeat flag | List of the IDs of the passes this booking credit can be used for. Applies only when IsUniversalCredit is true. |
| `--added-elegible-passes` | list, repeat flag | The added elegible passes value for this tariff booking credit |
| `--removed-elegible-passes` | list, repeat flag | The removed elegible passes value for this tariff booking credit |
| `--applies-to-charges` | bool | Whether this universal credit applies to other charges |

### TariffBookingCredit (key fields)

`Id`, `Name`, `TariffName`, `Credit`, `ServiceRenewalTime`

**List properties (only returned by `get`, not by `list`):** `ElegibleResourceTypes`, `AddedElegibleResourceTypes`, `RemovedElegibleResourceTypes`, `ElegibleProducts`, `AddedElegibleProducts`, `RemovedElegibleProducts`, `ElegibleTariffs`, `AddedElegibleTariffs`, `RemovedElegibleTariffs`, `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `ElegiblePasses`, `AddedElegiblePasses`, `RemovedElegiblePasses`

#### TariffBookingCredit enum values

| Option | Valid values |
| ------ | ------------ |
| `--service-renewal-time` | `1` Week, `2` CalendarMonth, `3` TariffMonth, `4` Year, `5` Day |

<!-- END:GENERATED entity=TariffBookingCredits -->
