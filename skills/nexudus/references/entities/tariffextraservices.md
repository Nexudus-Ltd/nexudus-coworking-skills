# TariffExtraServices

<!-- BEGIN:GENERATED entity=TariffExtraServices -->

Plan time credit (internally TariffExtraService) links an time credit type (internally ExtraService) to a plan (internally Tariff), defining an included allowance of booking time or printing credits for customers on that plan. The `UsesIncluded` value specifies how much is included. The renewal time controls how often the credit expires and the allowance resets.

TariffExtraServices support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffextraservices list --agent` | List all tariffextraservices |
| `nexudus tariffextraservices list --id <id> --agent` | Filter by single ID |
| `nexudus tariffextraservices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffextraservices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffextraservices list --tariff-name <value> --extra-service-name <value> --agent` | Filter tariffextraservices by properties |
| `nexudus tariffextraservices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffextraservices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus tariffextraservices get <id> --agent` | Get single tariffextraservice |
| `nexudus tariffextraservices create --tariff-id <value> --extra-service-id <value> --uses-included <value> --service-renewal-time <value> --agent` | Create tariffextraservice |
| `nexudus tariffextraservices update <id> --name "New Name" --agent` | Update tariffextraservice |
| `nexudus tariffextraservices delete <id> --yes --agent` | Delete tariffextraservice (no prompt) |

#### TariffExtraService list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long | ID of the plan linked to this record |
| `--tariff-name` | string | Tariff name |
| `--extra-service-id` | long | ID of the time credit type linked to this record. An ExtraService with IsBookingCredit = true associated with the type of resources this time credit is valid for.  |
| `--extra-service-name` | string | Extra service name |
| `--extra-service-charge-period` | string | Extra service charge period |
| `--extra-service-is-booking-credit` | bool | Whether extra service is booking credit |
| `--extra-service-is-printing-credit` | bool | Whether extra service is printing credit |
| `--uses-included` | int | Number of uses included in the unit associated with the selected time credit type (ExtraService.ChargePeriod). ExtraServiceChargePeriod in this entity. Minutes = 1, Days = 2, Weeks = 3, Months = 4, Uses = 5, FourWeekMonths = 6 |
| `--from-uses-included` | range | |
| `--to-uses-included` | range | |
| `--service-renewal-time` | enum | How often will this credit amount will expire and be issued again. Most common option is TariffMonth, which follows the plan renewal cycle. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TariffExtraService sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TariffExtraService create options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long, required | ID of the plan linked to this record |
| `--extra-service-id` | long, required | ID of the time credit type linked to this record. An ExtraService with IsBookingCredit = true associated with the type of resources this time credit is valid for.  |
| `--uses-included` | int, required | Number of uses included in the unit associated with the selected time credit type (ExtraService.ChargePeriod). ExtraServiceChargePeriod in this entity. Minutes = 1, Days = 2, Weeks = 3, Months = 4, Uses = 5, FourWeekMonths = 6 |
| `--service-renewal-time` | enum, required | How often will this credit amount will expire and be issued again. Most common option is TariffMonth, which follows the plan renewal cycle. |

#### TariffExtraService update options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long | ID of the plan linked to this record |
| `--extra-service-id` | long | ID of the time credit type linked to this record. An ExtraService with IsBookingCredit = true associated with the type of resources this time credit is valid for.  |
| `--uses-included` | int | Number of uses included in the unit associated with the selected time credit type (ExtraService.ChargePeriod). ExtraServiceChargePeriod in this entity. Minutes = 1, Days = 2, Weeks = 3, Months = 4, Uses = 5, FourWeekMonths = 6 |
| `--service-renewal-time` | enum | How often will this credit amount will expire and be issued again. Most common option is TariffMonth, which follows the plan renewal cycle. |

### TariffExtraService (key fields)

`Id`, `TariffName`, `ExtraServiceName`, `UsesIncluded`

#### TariffExtraService enum values

| Option | Valid values |
| ------ | ------------ |
| `--service-renewal-time` | `1` Week, `2` CalendarMonth, `3` TariffMonth, `4` Year, `5` Day |

<!-- END:GENERATED entity=TariffExtraServices -->
