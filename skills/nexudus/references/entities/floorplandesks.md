# FloorPlanDesks

<!-- BEGIN:GENERATED entity=FloorPlanDesks -->

A FloorPlanDesk, called a floor plan unit by operators, represents an office, desk, room, or other area on a location's floor plan that can be assigned through contracts, connected to a bookable resource, and included in occupancy reporting.

FloorPlanDesks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplandesks list --agent` | List all floorplandesks |
| `nexudus floorplandesks list --id <id> --agent` | Filter by single ID |
| `nexudus floorplandesks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplandesks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplandesks list --floor-plan-name <value> --coworker-full-name <value> --agent` | Filter floorplandesks by properties |
| `nexudus floorplandesks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplandesks list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus floorplandesks get <id> --agent` | Get single floorplandesk |
| `nexudus floorplandesks create --floor-plan-id <value> --name <value> --item-type <value> --size <value> --capacity <value> --price <value> --agent` | Create floorplandesk |
| `nexudus floorplandesks update <id> --name "New Name" --agent` | Update floorplandesk |
| `nexudus floorplandesks delete <id> --yes --agent` | Delete floorplandesk (no prompt) |

#### FloorPlanDesk list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-id` | long | ID of the required floor plan that owns this unit and determines its location |
| `--floor-plan-name` | string | Floor plan name |
| `--floor-plan-business-id` | int | ID of the location that owns the floor plan |
| `--from-floor-plan-business-id` | range | |
| `--to-floor-plan-business-id` | range | |
| `--floor-plan-business-currency-code` | string | Currency code of the location |
| `--floor-plan-business-name` | string | Location name |
| `--floor-plan-capacity` | int | Maximum capacity of the floor plan |
| `--from-floor-plan-capacity` | range | |
| `--to-floor-plan-capacity` | range | |
| `--coworker-id` | long | ID of the optional customer occupying this unit; normally assign occupancy through a contract, and the customer cannot be changed while contracts are linked |
| `--coworker-full-name` | string | Full name of the assigned customer |
| `--coworker-company-name` | string | Company name of the assigned customer |
| `--coworker-coworker-type` | enum | Record type of the assigned customer (Individual or Company) |
| `--coworker-email` | string | Email address of the assigned customer |
| `--coworker-team-names` | string | Names of the teams the assigned customer belongs to |
| `--sensor-id` | long | ID of the optional IoT sensor whose latest reading and occupancy action are reported for this unit |
| `--sensor-name` | string | Sensor name |
| `--sensor-unit` | string | Unit of measurement reported by the sensor (e.g. °C, ppm) |
| `--sensor-sensor-type` | enum | Type of the linked sensor (e.g. PresenceDetection, PeopleCounter, Temperature) |
| `--sensor-last-received-value` | string | Most recent raw value reported by the sensor |
| `--sensor-last-value-triggered-action` | bool | Whether the last sensor reading triggered a configured automation action |
| `--name` | string | Required, non-empty display name of the floor plan unit, such as 'Office 3' or 'Hot Desk 12' |
| `--item-type` | enum | Type of unit: Office, DedicatedDesk, HotDesk, Other, or Room; AI private-office recommendations include only Office units |
| `--resource-id` | long | ID of the optional bookable resource connected to this unit so customers can book it through a floor plan view |
| `--resource-name` | string | Linked resource name |
| `--resource-resource-type-name` | string | Resource type name of the linked resource |
| `--resource-allocation` | int | Maximum simultaneous bookings allowed for the linked resource |
| `--from-resource-allocation` | range | |
| `--to-resource-allocation` | range | |
| `--resource-projector` | bool | Whether the linked resource has a projector |
| `--resource-internet` | bool | Whether the linked resource provides internet access |
| `--resource-conference-phone` | bool | Whether the linked resource has a conference phone |
| `--resource-standard-phone` | bool | Whether the linked resource has a standard phone |
| `--resource-white-board` | bool | Whether the linked resource has a whiteboard |
| `--resource-large-display` | bool | Whether the linked resource has a large display or TV screen |
| `--resource-catering` | bool | Whether the linked resource offers catering services |
| `--resource-tea-and-coffee` | bool | Whether the linked resource provides tea and coffee |
| `--resource-drinks` | bool | Whether the linked resource provides drinks |
| `--resource-security-lock` | bool | Whether the linked resource has a security lock |
| `--resource-c-c-t-v` | bool | Whether the linked resource is covered by CCTV |
| `--resource-voice-recorder` | bool | Whether the linked resource has a voice recorder |
| `--resource-air-conditioning` | bool | Whether the linked resource has air conditioning |
| `--resource-heating` | bool | Whether the linked resource has heating |
| `--resource-natural-light` | bool | Whether the linked resource has natural light |
| `--resource-standing-desk` | bool | Whether the linked resource has a standing desk |
| `--resource-quiet-zone` | bool | Whether the linked resource is in a quiet zone |
| `--resource-wireless-charger` | bool | Whether the linked resource has a wireless charger |
| `--resource-privacy-screen` | bool | Whether the linked resource has a privacy screen |
| `--resource-soundproof` | bool | Whether the linked resource is soundproofed |
| `--resource-shifts` | string | Shift schedule defined on the linked resource |
| `--size` | decimal | Floor area stored in square metres; the Admin UI may display and convert it to square feet, and a linked layout area can overwrite it when SizeIsLinkedToArea is true |
| `--from-size` | range | |
| `--to-size` | range | |
| `--size-is-linked-to-area` | bool | Whether Size is synchronized from the Floor Plan Editor area identified by FloorPlanLayoutAssetUniqueId when that linked area exists |
| `--capacity` | decimal | Target number of seats for this unit, used for occupancy reporting and as a minimum-capacity filter in AI private-office recommendations |
| `--from-capacity` | range | |
| `--to-capacity` | range | |
| `--price` | decimal | Target price in the floor plan location's currency for revenue occupancy reporting; it is not a billing price and is the AI price fallback when PriceForAi is null |
| `--from-price` | range | |
| `--to-price` | range | |
| `--area` | string | Optional reporting group for floor plan units, such as a floor, zone, or wing |
| `--sensor-last-value` | string | Read-only string containing the latest value received from the linked sensor; sensor processing updates and clears it |
| `--is-sensor-occupied` | bool | Whether the linked sensor's occupancy action currently marks this unit as occupied; sensor processing controls this read-only value |
| `--notes` | string | Optional internal notes about this unit, limited to 255 characters and not visible to customers |
| `--available` | bool | Whether this unit is in service and can be assigned to contracts or bookings; current availability also requires the UTC availability window to include now |
| `--available-to-ai` | bool | Whether AI channels may include this unit in private-office recommendations; the unit must also be an available Office |
| `--notes-for-ai` | string | Optional notes for AI recommendations, limited to 1,024 characters, such as accessibility, furnishing, natural light, or noise information |
| `--show-price-for-ai` | bool | Whether AI recommendations may show a price for this unit; this does not stop PriceForAi or Price from being used to match a customer's budget |
| `--price-for-ai` | decimal | Optional price override in the location's currency used for AI display and budget matching; null falls back to Price |
| `--from-price-for-ai` | range | |
| `--to-price-for-ai` | range | |
| `--coworker-contract-ids` | string | Read-only comma-separated IDs of contracts linked to this unit; update the contracts rather than this projection |
| `--coworker-contract-full-names` | string | Read-only comma-separated customer names from contracts linked to this unit; update the contracts rather than this projection |
| `--coworker-contract-start-dates` | string | Read-only comma-separated start dates from contracts linked to this unit; update the contracts rather than this projection |
| `--available-from-time` | DateTime | Inclusive UTC start of the reporting availability window; when omitted on create it defaults to the start of the current day at the location, and it must precede AvailableToTime when both are set |
| `--from-available-from-time` | range | |
| `--to-available-from-time` | range | |
| `--available-to-time` | DateTime | Optional inclusive UTC end of the reporting availability window; null means no end, and it must follow AvailableFromTime when both are set |
| `--from-available-to-time` | range | |
| `--to-available-to-time` | range | |
| `--floor-plan-layout-asset-unique-id` | string | Floor Plan Editor-managed area GUID that links this unit to a layout asset and drives linked Size synchronization |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanDesk sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FloorPlanDesk create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-id` | long, required | ID of the required floor plan that owns this unit and determines its location |
| `--coworker-id` | long | ID of the optional customer occupying this unit; normally assign occupancy through a contract, and the customer cannot be changed while contracts are linked |
| `--sensor-id` | long | ID of the optional IoT sensor whose latest reading and occupancy action are reported for this unit |
| `--name` | string, required | Required, non-empty display name of the floor plan unit, such as 'Office 3' or 'Hot Desk 12' |
| `--item-type` | enum, required | Type of unit: Office, DedicatedDesk, HotDesk, Other, or Room; AI private-office recommendations include only Office units |
| `--resource-id` | long | ID of the optional bookable resource connected to this unit so customers can book it through a floor plan view |
| `--size` | decimal, required | Floor area stored in square metres; the Admin UI may display and convert it to square feet, and a linked layout area can overwrite it when SizeIsLinkedToArea is true |
| `--size-is-linked-to-area` | bool | Whether Size is synchronized from the Floor Plan Editor area identified by FloorPlanLayoutAssetUniqueId when that linked area exists |
| `--capacity` | decimal, required | Target number of seats for this unit, used for occupancy reporting and as a minimum-capacity filter in AI private-office recommendations |
| `--price` | decimal, required | Target price in the floor plan location's currency for revenue occupancy reporting; it is not a billing price and is the AI price fallback when PriceForAi is null |
| `--area` | string | Optional reporting group for floor plan units, such as a floor, zone, or wing |
| `--notes` | string | Optional internal notes about this unit, limited to 255 characters and not visible to customers |
| `--available` | bool | Whether this unit is in service and can be assigned to contracts or bookings; current availability also requires the UTC availability window to include now |
| `--available-to-ai` | bool | Whether AI channels may include this unit in private-office recommendations; the unit must also be an available Office |
| `--notes-for-ai` | string | Optional notes for AI recommendations, limited to 1,024 characters, such as accessibility, furnishing, natural light, or noise information |
| `--show-price-for-ai` | bool | Whether AI recommendations may show a price for this unit; this does not stop PriceForAi or Price from being used to match a customer's budget |
| `--price-for-ai` | decimal | Optional price override in the location's currency used for AI display and budget matching; null falls back to Price |
| `--available-from-time` | DateTime | Inclusive UTC start of the reporting availability window; when omitted on create it defaults to the start of the current day at the location, and it must precede AvailableToTime when both are set |
| `--available-to-time` | DateTime | Optional inclusive UTC end of the reporting availability window; null means no end, and it must follow AvailableFromTime when both are set |
| `--floor-plan-layout-asset-unique-id` | string | Floor Plan Editor-managed area GUID that links this unit to a layout asset and drives linked Size synchronization |

#### FloorPlanDesk update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-id` | long | ID of the required floor plan that owns this unit and determines its location |
| `--coworker-id` | long | ID of the optional customer occupying this unit; normally assign occupancy through a contract, and the customer cannot be changed while contracts are linked |
| `--sensor-id` | long | ID of the optional IoT sensor whose latest reading and occupancy action are reported for this unit |
| `--name` | string | Required, non-empty display name of the floor plan unit, such as 'Office 3' or 'Hot Desk 12' |
| `--item-type` | enum | Type of unit: Office, DedicatedDesk, HotDesk, Other, or Room; AI private-office recommendations include only Office units |
| `--resource-id` | long | ID of the optional bookable resource connected to this unit so customers can book it through a floor plan view |
| `--size` | decimal | Floor area stored in square metres; the Admin UI may display and convert it to square feet, and a linked layout area can overwrite it when SizeIsLinkedToArea is true |
| `--size-is-linked-to-area` | bool | Whether Size is synchronized from the Floor Plan Editor area identified by FloorPlanLayoutAssetUniqueId when that linked area exists |
| `--capacity` | decimal | Target number of seats for this unit, used for occupancy reporting and as a minimum-capacity filter in AI private-office recommendations |
| `--price` | decimal | Target price in the floor plan location's currency for revenue occupancy reporting; it is not a billing price and is the AI price fallback when PriceForAi is null |
| `--area` | string | Optional reporting group for floor plan units, such as a floor, zone, or wing |
| `--notes` | string | Optional internal notes about this unit, limited to 255 characters and not visible to customers |
| `--available` | bool | Whether this unit is in service and can be assigned to contracts or bookings; current availability also requires the UTC availability window to include now |
| `--available-to-ai` | bool | Whether AI channels may include this unit in private-office recommendations; the unit must also be an available Office |
| `--notes-for-ai` | string | Optional notes for AI recommendations, limited to 1,024 characters, such as accessibility, furnishing, natural light, or noise information |
| `--show-price-for-ai` | bool | Whether AI recommendations may show a price for this unit; this does not stop PriceForAi or Price from being used to match a customer's budget |
| `--price-for-ai` | decimal | Optional price override in the location's currency used for AI display and budget matching; null falls back to Price |
| `--available-from-time` | DateTime | Inclusive UTC start of the reporting availability window; when omitted on create it defaults to the start of the current day at the location, and it must precede AvailableToTime when both are set |
| `--available-to-time` | DateTime | Optional inclusive UTC end of the reporting availability window; null means no end, and it must follow AvailableFromTime when both are set |
| `--floor-plan-layout-asset-unique-id` | string | Floor Plan Editor-managed area GUID that links this unit to a layout asset and drives linked Size synchronization |

#### FloorPlanDesk PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |
| `--coworker-contract-full-names` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus floorplandesks update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### FloorPlanDesk (key fields)

`Id`, `FloorPlanName`, `CoworkerFullName`, `SensorName`, `Name`, `ResourceName`

#### FloorPlanDesk enum values

| Option | Valid values |
| ------ | ------------ |
| `--item-type` | `1` Office, `2` DedicatedDesk, `3` HotDesk, `4` Other, `5` Room |

<!-- END:GENERATED entity=FloorPlanDesks -->
