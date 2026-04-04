# Resources

<!-- BEGIN:GENERATED entity=Resources -->

A **Resource** represents any bookable item in a coworking or flex-space location — meeting rooms, event spaces, phone booths, hot desks, private offices, storage units, labs, kitchens, and more. Each resource belongs to exactly one `ResourceType` (via `ResourceTypeId`), which is a category such as "Meeting Room" or "Phone Booth".

> **Resource → ResourceType → ExtraService (booking rates):** Pricing is not set directly on a resource or its type. Instead, one or more `ExtraService` (Booking rate) records are linked to a `ResourceType` to define pricing rules — each covering a specific charge period (hourly, daily, etc.) and optional restrictions (customer segment, time window, booking length). A resource inherits the pricing rules of its resource type automatically. This means that resources needing a different set of rates, it also needs a different type. You must know the `ResourceTypeId` before creating a resource.

CRITICAL: ExtraService is an internal name, do not expose this name to the human (call them booking rates)

### Booking policies and restrictions

Each resource can define its own booking policies that override or extend location-level defaults:

- **Advance / late booking** — `BookInAdvanceLimit` caps how far ahead a booking can be made; `LateBookingLimit` sets the minimum lead time before a booking can start.
- **Booking length** — `MinBookingLength` and `MaxBookingLength` constrain the duration of a single booking (in minutes).
- **Cancellation** — `LateCancellationLimit` sets the cut-off (in minutes before start) after which a booking counts as a late cancellation. When `ChargeCancellationFee` is enabled, a fee is charged — either a fixed amount (`CancellationFeeType = Absolute`, `CancellationFeeAmount`) or a percentage of the booking cost (`CancellationFeeType = Percentage`, `CancellationFeePercentage`).
- **No-return policy** — `NoReturnPolicy` prevents the same user from booking this specific resource again within a given number of minutes after their last booking ends. `NoReturnPolicyAllResources` extends this cooldown across all resources, and `NoReturnPolicyAllUsers` prevents any user from booking this resource within the specified window.
- **Repeat bookings** — `RepeatBookingQuantityLimit` and `RepeatBookingPeriodLimitInMonths` cap the number and time span of recurring bookings.
- **Capacity** — `Allocation` sets the maximum number of attendees. When `AllowMultipleBookings` is true, overlapping bookings are permitted up to this capacity. `LimitVisitorsToAllocation` enforces the capacity cap for visitor additions.
- **Confirmation** — `RequiresConfirmation` means bookings are held as pending until an admin approves them.
- **Visibility** — `Visible` controls whether the resource appears to end users. `Archived` hides the resource from all views.

### Access restrictions

- `OnlyForMembers` — only active members (coworkers with a plan) can book this resource.
- `OnlyForContacts` — only contacts (non-member customers) can book this resource.
- `Tariffs` — restrict bookings to coworkers on specific pricing plans.
- `Teams` — restrict bookings to members of specific teams.

### Amenity flags

Boolean flags such as `Projector`, `WhiteBoard`, `VideoConferencing`, `Soundproof`, etc. describe the physical amenities available in the resource. These are used for filtering and display purposes.

Resources support Search, Get, Create, Update, Delete.
Resources also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus resources list --agent` | List all resources |
| `nexudus resources list --id <id> --agent` | Filter by single ID |
| `nexudus resources list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resources list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resources list --name <value> --visible <value> --agent` | Filter resources by properties |
| `nexudus resources list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resources get <id> --agent` | Get single resource |
| `nexudus resources create --business-id <value> --name <value> --resource-type-id <value> --display-order <value> --agent` | Create resource |
| `nexudus resources update <id> --name "New Name" --agent` | Update resource |
| `nexudus resources delete <id> --yes --agent` | Delete resource (no prompt) |
| `nexudus resources run-command <key> <ids> --agent` | Run entity command |

#### Resource list filter options

`--business-id`, `--name`, `--system-resource-type`, `--resource-type-id`, `--description`, `--new-picture-url`, `--clear-picture`, `--email-confirmation-content`, `--visible`, `--requires-confirmation`, `--display-order`, `--group-name`, `--projector`, `--internet`, `--conference-phone`, `--standard-phone`, `--white-board`, `--large-display`, `--catering`, `--tea-and-coffee`, `--drinks`, `--security-lock`, `--cctv`, `--voice-recorder`, `--air-conditioning`, `--heating`, `--natural-light`, `--standing-desk`, `--quiet-zone`, `--wireless-charger`, `--privacy-screen`, `--soundproof`, `--video-conferencing`, `--dual-display-screen`, `--display-screen`, `--wireless-presentation`, `--pa-system`, `--desktop-monitor`, `--flip-chart`, `--secure-storage`, `--allow-multiple-bookings`, `--allocation`, `--limit-visitors-to-allocation`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--max-booking-length`, `--min-booking-length`, `--shifts`, `--google-calendar-id`, `--kisi-group-id`, `--access-control-group-id`, `--longitude`, `--latitude`, `--hide-in-calendar`, `--archived`, `--use-shared-zoom-account`, `--zoom-access-token`, `--zoom-refresh-token`, `--zoom-user-id`, `--last-cleaned-at`, `--office365-calendar-id`, `--linked-resource-ids`, `--only-for-contacts`, `--only-for-members`, `--only-for-invoicing-business`, `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`

#### Resource create options

`--business-id` (required), `--name` (required), `--system-resource-type`, `--resource-type-id` (required), `--description`, `--new-picture-url`, `--clear-picture`, `--email-confirmation-content`, `--visible`, `--requires-confirmation`, `--display-order` (required), `--group-name`, `--projector`, `--internet`, `--conference-phone`, `--standard-phone`, `--white-board`, `--large-display`, `--catering`, `--tea-and-coffee`, `--drinks`, `--security-lock`, `--cctv`, `--voice-recorder`, `--air-conditioning`, `--heating`, `--natural-light`, `--standing-desk`, `--quiet-zone`, `--wireless-charger`, `--privacy-screen`, `--soundproof`, `--video-conferencing`, `--dual-display-screen`, `--display-screen`, `--wireless-presentation`, `--pa-system`, `--desktop-monitor`, `--flip-chart`, `--secure-storage`, `--allow-multiple-bookings`, `--allocation`, `--limit-visitors-to-allocation`, `--bookings` (list, repeat flag), `--added-bookings` (list, repeat flag), `--removed-bookings` (list, repeat flag), `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--max-booking-length`, `--min-booking-length`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--shifts`, `--resource-products` (list, repeat flag), `--added-resource-products` (list, repeat flag), `--removed-resource-products` (list, repeat flag), `--floor-plan-desks` (list, repeat flag), `--added-floor-plan-desks` (list, repeat flag), `--removed-floor-plan-desks` (list, repeat flag), `--resource-access-rules` (list, repeat flag), `--added-resource-access-rules` (list, repeat flag), `--removed-resource-access-rules` (list, repeat flag), `--linked-resources` (list, repeat flag), `--added-linked-resources` (list, repeat flag), `--removed-linked-resources` (list, repeat flag), `--google-calendar-id`, `--kisi-group-id`, `--access-control-group-id`, `--longitude`, `--latitude`, `--hide-in-calendar`, `--archived`, `--use-shared-zoom-account`, `--zoom-access-token`, `--zoom-refresh-token`, `--zoom-user-id`, `--last-cleaned-at`, `--office365-calendar-id`, `--linked-resource-ids`, `--only-for-contacts`, `--only-for-members`, `--only-for-invoicing-business`, `--booking-availability-exceptions` (list, repeat flag), `--added-booking-availability-exceptions` (list, repeat flag), `--removed-booking-availability-exceptions` (list, repeat flag), `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--cancelled-bookings` (list, repeat flag), `--added-cancelled-bookings` (list, repeat flag), `--removed-cancelled-bookings` (list, repeat flag), `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`, `--time-slots` (JSON array or @filepath)

#### Resource update options

`--business-id`, `--name`, `--system-resource-type`, `--resource-type-id`, `--description`, `--new-picture-url`, `--clear-picture`, `--email-confirmation-content`, `--visible`, `--requires-confirmation`, `--display-order`, `--group-name`, `--projector`, `--internet`, `--conference-phone`, `--standard-phone`, `--white-board`, `--large-display`, `--catering`, `--tea-and-coffee`, `--drinks`, `--security-lock`, `--cctv`, `--voice-recorder`, `--air-conditioning`, `--heating`, `--natural-light`, `--standing-desk`, `--quiet-zone`, `--wireless-charger`, `--privacy-screen`, `--soundproof`, `--video-conferencing`, `--dual-display-screen`, `--display-screen`, `--wireless-presentation`, `--pa-system`, `--desktop-monitor`, `--flip-chart`, `--secure-storage`, `--allow-multiple-bookings`, `--allocation`, `--limit-visitors-to-allocation`, `--bookings` (list, repeat flag), `--added-bookings` (list, repeat flag), `--removed-bookings` (list, repeat flag), `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--max-booking-length`, `--min-booking-length`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--shifts`, `--resource-products` (list, repeat flag), `--added-resource-products` (list, repeat flag), `--removed-resource-products` (list, repeat flag), `--floor-plan-desks` (list, repeat flag), `--added-floor-plan-desks` (list, repeat flag), `--removed-floor-plan-desks` (list, repeat flag), `--resource-access-rules` (list, repeat flag), `--added-resource-access-rules` (list, repeat flag), `--removed-resource-access-rules` (list, repeat flag), `--linked-resources` (list, repeat flag), `--added-linked-resources` (list, repeat flag), `--removed-linked-resources` (list, repeat flag), `--google-calendar-id`, `--kisi-group-id`, `--access-control-group-id`, `--longitude`, `--latitude`, `--hide-in-calendar`, `--archived`, `--use-shared-zoom-account`, `--zoom-access-token`, `--zoom-refresh-token`, `--zoom-user-id`, `--last-cleaned-at`, `--office365-calendar-id`, `--linked-resource-ids`, `--only-for-contacts`, `--only-for-members`, `--only-for-invoicing-business`, `--booking-availability-exceptions` (list, repeat flag), `--added-booking-availability-exceptions` (list, repeat flag), `--removed-booking-availability-exceptions` (list, repeat flag), `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--cancelled-bookings` (list, repeat flag), `--added-cancelled-bookings` (list, repeat flag), `--removed-cancelled-bookings` (list, repeat flag), `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`, `--time-slots` (JSON array or @filepath)

### Resource (key fields)

`Id`, `BusinessName`, `Name`, `ResourceTypeName`, `Visible`, `GroupName`, `Allocation`, `Archived`, `OnlyForContacts`, `OnlyForMembers`

**List properties (only returned by `get`, not by `list`):** `Bookings`, `AddedBookings`, `RemovedBookings`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Teams`, `AddedTeams`, `RemovedTeams`, `ResourceProducts`, `AddedResourceProducts`, `RemovedResourceProducts`, `FloorPlanDesks`, `AddedFloorPlanDesks`, `RemovedFloorPlanDesks`, `ResourceAccessRules`, `AddedResourceAccessRules`, `RemovedResourceAccessRules`, `LinkedResources`, `AddedLinkedResources`, `RemovedLinkedResources`, `BookingAvailabilityExceptions`, `AddedBookingAvailabilityExceptions`, `RemovedBookingAvailabilityExceptions`, `CancelledBookings`, `AddedCancelledBookings`, `RemovedCancelledBookings`

#### Resource inline children

Resource supports inline child objects on create and update. Pass a JSON array or a `@filepath` reference.

**`--time-slots`** — The days and times this resource is available for booking. The year, month and day component of FromTime/ToTime is always 1976-01-01.

Writable properties: `DayOfWeek`, `FromTime`, `ToTime`

```shell
nexudus resources create ... --time-slots '[{"DayOfWeek": "...", "FromTime": "...", "ToTime": "..."}]' --agent
```

Or from a file:

```shell
nexudus resources create ... --time-slots @timeslots.json --agent
```

#### Resource enum values

| Option | Valid values |
| ------ | ------------ |
| `--system-resource-type` | `0` None, `1` MeetingRoom, `2` HotDesk, `3` PrivateOffice, `4` EventSpace, `5` Lab, `6` Kitchen, `7` TreatmentRoom, `9` StorageUnit, `10` Machine, `11` DayPass, `12` PhoneBooth, `99` Other |
| `--cancellation-fee-type` | `0` None, `1` Absolute, `2` Percentage |

<!-- END:GENERATED entity=Resources -->
