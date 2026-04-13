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
| `nexudus resources create --business-id <value> --name <value> --system-resource-type <value> --resource-type-id <value> --display-order <value> --cancellation-fee-type <value> --agent` | Create resource |
| `nexudus resources update <id> --name "New Name" --agent` | Update resource |
| `nexudus resources delete <id> --yes --agent` | Delete resource (no prompt) |
| `nexudus resources run-command <key> <ids> --agent` | Run entity command |

#### Resource list filter options

`--business-id` (long), `--name`, `--system-resource-type` (enum), `--resource-type-id` (long), `--description`, `--new-picture-url`, `--clear-picture-file` (bool), `--email-confirmation-content`, `--visible` (bool), `--requires-confirmation` (bool), `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--group-name`, `--projector` (bool), `--internet` (bool), `--conference-phone` (bool), `--standard-phone` (bool), `--white-board` (bool), `--large-display` (bool), `--catering` (bool), `--tea-and-coffee` (bool), `--drinks` (bool), `--security-lock` (bool), `--cctv` (bool), `--voice-recorder` (bool), `--air-conditioning` (bool), `--heating` (bool), `--natural-light` (bool), `--standing-desk` (bool), `--quiet-zone` (bool), `--wireless-charger` (bool), `--privacy-screen` (bool), `--soundproof` (bool), `--video-conferencing` (bool), `--dual-display-screen` (bool), `--display-screen` (bool), `--wireless-presentation` (bool), `--pa-system` (bool), `--desktop-monitor` (bool), `--flip-chart` (bool), `--secure-storage` (bool), `--allow-multiple-bookings` (bool), `--allocation` (int), `--from-allocation` (range), `--to-allocation` (range), `--limit-visitors-to-allocation` (bool), `--book-in-advance-limit` (decimal), `--from-book-in-advance-limit` (range), `--to-book-in-advance-limit` (range), `--late-booking-limit` (decimal), `--from-late-booking-limit` (range), `--to-late-booking-limit` (range), `--late-cancellation-limit` (int), `--from-late-cancellation-limit` (range), `--to-late-cancellation-limit` (range), `--interval-limit` (int), `--from-interval-limit` (range), `--to-interval-limit` (range), `--no-return-policy` (int), `--from-no-return-policy` (range), `--to-no-return-policy` (range), `--no-return-policy-all-resources` (int), `--from-no-return-policy-all-resources` (range), `--to-no-return-policy-all-resources` (range), `--no-return-policy-all-users` (int), `--from-no-return-policy-all-users` (range), `--to-no-return-policy-all-users` (range), `--max-booking-length` (int), `--from-max-booking-length` (range), `--to-max-booking-length` (range), `--min-booking-length` (int), `--from-min-booking-length` (range), `--to-min-booking-length` (range), `--shifts`, `--google-calendar-id`, `--kisi-group-id`, `--access-control-group-id`, `--longitude` (decimal), `--from-longitude` (range), `--to-longitude` (range), `--latitude` (decimal), `--from-latitude` (range), `--to-latitude` (range), `--hide-in-calendar` (bool), `--archived` (bool), `--use-shared-zoom-account` (bool), `--zoom-access-token`, `--zoom-refresh-token`, `--zoom-user-id`, `--last-cleaned-at` (DateTime), `--from-last-cleaned-at` (range), `--to-last-cleaned-at` (range), `--office365-calendar-id`, `--linked-resource-ids`, `--only-for-contacts` (bool), `--only-for-members` (bool), `--only-for-invoicing-business` (bool), `--cancellation-fee-product-id` (long), `--charge-cancellation-fee` (bool), `--cancellation-fee-type` (enum), `--cancellation-fee-amount` (decimal), `--from-cancellation-fee-amount` (range), `--to-cancellation-fee-amount` (range), `--cancellation-fee-percentage` (decimal), `--from-cancellation-fee-percentage` (range), `--to-cancellation-fee-percentage` (range), `--repeat-booking-quantity-limit` (int), `--from-repeat-booking-quantity-limit` (range), `--to-repeat-booking-quantity-limit` (range), `--repeat-booking-period-limit-in-months` (int), `--from-repeat-booking-period-limit-in-months` (range), `--to-repeat-booking-period-limit-in-months` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Resource create options

`--business-id` (long, required), `--name` (required), `--system-resource-type` (enum, required), `--resource-type-id` (long, required), `--description`, `--new-picture-url`, `--clear-picture-file` (bool), `--email-confirmation-content`, `--visible` (bool), `--requires-confirmation` (bool), `--display-order` (int, required), `--group-name`, `--projector` (bool), `--internet` (bool), `--conference-phone` (bool), `--standard-phone` (bool), `--white-board` (bool), `--large-display` (bool), `--catering` (bool), `--tea-and-coffee` (bool), `--drinks` (bool), `--security-lock` (bool), `--cctv` (bool), `--voice-recorder` (bool), `--air-conditioning` (bool), `--heating` (bool), `--natural-light` (bool), `--standing-desk` (bool), `--quiet-zone` (bool), `--wireless-charger` (bool), `--privacy-screen` (bool), `--soundproof` (bool), `--video-conferencing` (bool), `--dual-display-screen` (bool), `--display-screen` (bool), `--wireless-presentation` (bool), `--pa-system` (bool), `--desktop-monitor` (bool), `--flip-chart` (bool), `--secure-storage` (bool), `--allow-multiple-bookings` (bool), `--allocation` (int), `--limit-visitors-to-allocation` (bool), `--book-in-advance-limit` (decimal), `--late-booking-limit` (decimal), `--late-cancellation-limit` (int), `--interval-limit` (int), `--no-return-policy` (int), `--no-return-policy-all-resources` (int), `--no-return-policy-all-users` (int), `--max-booking-length` (int), `--min-booking-length` (int), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--shifts`, `--linked-resources` (list, repeat flag), `--added-linked-resources` (list, repeat flag), `--removed-linked-resources` (list, repeat flag), `--google-calendar-id`, `--kisi-group-id`, `--access-control-group-id`, `--longitude` (decimal), `--latitude` (decimal), `--hide-in-calendar` (bool), `--archived` (bool), `--use-shared-zoom-account` (bool), `--zoom-access-token`, `--zoom-refresh-token`, `--zoom-user-id`, `--last-cleaned-at` (DateTime), `--office365-calendar-id`, `--linked-resource-ids`, `--only-for-contacts` (bool), `--only-for-members` (bool), `--only-for-invoicing-business` (bool), `--booking-availability-exceptions` (list, repeat flag), `--added-booking-availability-exceptions` (list, repeat flag), `--removed-booking-availability-exceptions` (list, repeat flag), `--cancellation-fee-product-id` (long), `--charge-cancellation-fee` (bool), `--cancellation-fee-type` (enum, required), `--cancellation-fee-amount` (decimal), `--cancellation-fee-percentage` (decimal), `--repeat-booking-quantity-limit` (int), `--repeat-booking-period-limit-in-months` (int), `--time-slots` (JSON array or @filepath)

#### Resource update options

`--business-id` (long), `--name`, `--system-resource-type` (enum), `--resource-type-id` (long), `--description`, `--new-picture-url`, `--clear-picture-file` (bool), `--email-confirmation-content`, `--visible` (bool), `--requires-confirmation` (bool), `--display-order` (int), `--group-name`, `--projector` (bool), `--internet` (bool), `--conference-phone` (bool), `--standard-phone` (bool), `--white-board` (bool), `--large-display` (bool), `--catering` (bool), `--tea-and-coffee` (bool), `--drinks` (bool), `--security-lock` (bool), `--cctv` (bool), `--voice-recorder` (bool), `--air-conditioning` (bool), `--heating` (bool), `--natural-light` (bool), `--standing-desk` (bool), `--quiet-zone` (bool), `--wireless-charger` (bool), `--privacy-screen` (bool), `--soundproof` (bool), `--video-conferencing` (bool), `--dual-display-screen` (bool), `--display-screen` (bool), `--wireless-presentation` (bool), `--pa-system` (bool), `--desktop-monitor` (bool), `--flip-chart` (bool), `--secure-storage` (bool), `--allow-multiple-bookings` (bool), `--allocation` (int), `--limit-visitors-to-allocation` (bool), `--book-in-advance-limit` (decimal), `--late-booking-limit` (decimal), `--late-cancellation-limit` (int), `--interval-limit` (int), `--no-return-policy` (int), `--no-return-policy-all-resources` (int), `--no-return-policy-all-users` (int), `--max-booking-length` (int), `--min-booking-length` (int), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--shifts`, `--linked-resources` (list, repeat flag), `--added-linked-resources` (list, repeat flag), `--removed-linked-resources` (list, repeat flag), `--google-calendar-id`, `--kisi-group-id`, `--access-control-group-id`, `--longitude` (decimal), `--latitude` (decimal), `--hide-in-calendar` (bool), `--archived` (bool), `--use-shared-zoom-account` (bool), `--zoom-access-token`, `--zoom-refresh-token`, `--zoom-user-id`, `--last-cleaned-at` (DateTime), `--office365-calendar-id`, `--linked-resource-ids`, `--only-for-contacts` (bool), `--only-for-members` (bool), `--only-for-invoicing-business` (bool), `--booking-availability-exceptions` (list, repeat flag), `--added-booking-availability-exceptions` (list, repeat flag), `--removed-booking-availability-exceptions` (list, repeat flag), `--cancellation-fee-product-id` (long), `--charge-cancellation-fee` (bool), `--cancellation-fee-type` (enum), `--cancellation-fee-amount` (decimal), `--cancellation-fee-percentage` (decimal), `--repeat-booking-quantity-limit` (int), `--repeat-booking-period-limit-in-months` (int), `--time-slots` (JSON array or @filepath)

### Resource (key fields)

`Id`, `BusinessName`, `Name`, `ResourceTypeName`, `Visible`, `GroupName`, `Allocation`, `Archived`, `OnlyForContacts`, `OnlyForMembers`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Teams`, `AddedTeams`, `RemovedTeams`, `LinkedResources`, `AddedLinkedResources`, `RemovedLinkedResources`, `BookingAvailabilityExceptions`, `AddedBookingAvailabilityExceptions`, `RemovedBookingAvailabilityExceptions`

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
