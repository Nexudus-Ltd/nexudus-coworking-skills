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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Display name of the resource (e.g., 'Board Room A', 'Phone Booth 3'). |
| `--system-resource-type` | enum | Built-in resource category used for system behaviour (e.g., MeetingRoom, HotDesk, PhoneBooth). Distinct from the custom ResourceType. |
| `--resource-type-id` | long | ID of the resource type linked to this record |
| `--description` | string | Free-text description shown to users when viewing the resource details. |
| `--new-picture-url` | string | URL of a new file to upload as the picture |
| `--clear-picture-file` | bool | Set to true to remove the current picture file |
| `--email-confirmation-content` | string | Custom HTML or text included in booking confirmation emails for this resource. |
| `--visible` | bool | Whether the resource is visible and bookable by end users. Hidden resources can still be booked by admins. |
| `--requires-confirmation` | bool | When true, bookings for this resource are held as pending until an admin approves them. |
| `--display-order` | int | Sort position when listing resources. Lower values appear first. |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--group-name` | string | Optional grouping label used to cluster related resources together in the UI (e.g., 'Floor 2'). |
| `--projector` | bool | Amenity flag: resource has a projector. |
| `--internet` | bool | Amenity flag: resource has internet access. |
| `--conference-phone` | bool | Amenity flag: resource has a conference phone. |
| `--standard-phone` | bool | Amenity flag: resource has a standard phone. |
| `--white-board` | bool | Amenity flag: resource has a whiteboard. |
| `--large-display` | bool | Amenity flag: resource has a large display. |
| `--catering` | bool | Amenity flag: catering is available for this resource. |
| `--tea-and-coffee` | bool | Amenity flag: tea and coffee are available. |
| `--drinks` | bool | Amenity flag: drinks are available. |
| `--security-lock` | bool | Amenity flag: resource has a security lock. |
| `--cctv` | bool | Amenity flag: resource has CCTV coverage. |
| `--voice-recorder` | bool | Amenity flag: resource has a voice recorder. |
| `--air-conditioning` | bool | Amenity flag: resource has air conditioning. |
| `--heating` | bool | Amenity flag: resource has heating. |
| `--natural-light` | bool | Amenity flag: resource has natural light. |
| `--standing-desk` | bool | Amenity flag: resource has a standing desk. |
| `--quiet-zone` | bool | Amenity flag: resource is located in a quiet zone. |
| `--wireless-charger` | bool | Amenity flag: resource has a wireless charger. |
| `--privacy-screen` | bool | Amenity flag: resource has a privacy screen. |
| `--soundproof` | bool | Amenity flag: resource is soundproof. |
| `--video-conferencing` | bool | Amenity flag: resource has video conferencing equipment. |
| `--dual-display-screen` | bool | Amenity flag: resource has a dual display screen. |
| `--display-screen` | bool | Amenity flag: resource has a display screen. |
| `--wireless-presentation` | bool | Amenity flag: resource has wireless presentation capabilities. |
| `--pa-system` | bool | Amenity flag: resource has a PA system. |
| `--desktop-monitor` | bool | Amenity flag: resource has a desktop monitor. |
| `--flip-chart` | bool | Amenity flag: resource has a flip chart. |
| `--secure-storage` | bool | Amenity flag: resource has secure storage. |
| `--allow-multiple-bookings` | bool | When true, overlapping bookings are permitted up to the Allocation capacity. |
| `--allocation` | int | Maximum number of attendees or concurrent bookings allowed. Used with AllowMultipleBookings to control capacity. |
| `--from-allocation` | range | |
| `--to-allocation` | range | |
| `--limit-visitors-to-allocation` | bool | When true, the total number of visitors added to a booking cannot exceed the Allocation capacity. |
| `--book-in-advance-limit` | decimal | Maximum number of days in advance a booking can be made for this resource. Null means no limit. |
| `--from-book-in-advance-limit` | range | |
| `--to-book-in-advance-limit` | range | |
| `--late-booking-limit` | decimal | Minimum lead time (in minutes) required before a booking can start. Prevents last-minute bookings. |
| `--from-late-booking-limit` | range | |
| `--to-late-booking-limit` | range | |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee. |
| `--from-late-cancellation-limit` | range | |
| `--to-late-cancellation-limit` | range | |
| `--interval-limit` | int | Minimum interval (in minutes) between consecutive bookings on this resource, used as a buffer for setup or cleaning. |
| `--from-interval-limit` | range | |
| `--to-interval-limit` | range | |
| `--no-return-policy` | int | Cooldown in minutes: prevents the same user from booking this specific resource again within this window after their last booking ends. |
| `--from-no-return-policy` | range | |
| `--to-no-return-policy` | range | |
| `--no-return-policy-all-resources` | int | Cooldown in minutes: prevents the same user from booking any resource after booking this one, for the specified window. |
| `--from-no-return-policy-all-resources` | range | |
| `--to-no-return-policy-all-resources` | range | |
| `--no-return-policy-all-users` | int | Cooldown in minutes: prevents any user from booking this resource within the specified window after the previous booking ends. |
| `--from-no-return-policy-all-users` | range | |
| `--to-no-return-policy-all-users` | range | |
| `--max-booking-length` | int | Maximum allowed duration for a single booking on this resource, in minutes. |
| `--from-max-booking-length` | range | |
| `--to-max-booking-length` | range | |
| `--min-booking-length` | int | Minimum allowed duration for a single booking on this resource, in minutes. |
| `--from-min-booking-length` | range | |
| `--to-min-booking-length` | range | |
| `--shifts` | string | JSON-encoded shifts configuration defining the resource's availability schedule. |
| `--google-calendar-id` | string | ID of the google calendar associated with this record |
| `--kisi-group-id` | string | ID of the kisi group associated with this record |
| `--access-control-group-id` | string | ID of the access control group associated with this record |
| `--longitude` | decimal | GPS longitude coordinate of the resource's physical location. |
| `--from-longitude` | range | |
| `--to-longitude` | range | |
| `--latitude` | decimal | GPS latitude coordinate of the resource's physical location. |
| `--from-latitude` | range | |
| `--to-latitude` | range | |
| `--hide-in-calendar` | bool | When true, this resource does not appear on the booking calendar view. |
| `--archived` | bool | When true, the resource is archived and hidden from all views. It cannot be booked. |
| `--use-shared-zoom-account` | bool | When true, bookings for this resource use the location's shared Zoom account to create virtual meetings. |
| `--zoom-access-token` | string | The zoom access token value for this resource |
| `--zoom-refresh-token` | string | The zoom refresh token value for this resource |
| `--zoom-user-id` | string | Zoom user ID used to host virtual meetings when UseSharedZoomAccount is false. |
| `--last-cleaned-at` | DateTime | Timestamp of the last cleaning event for this resource. |
| `--from-last-cleaned-at` | range | |
| `--to-last-cleaned-at` | range | |
| `--office365-calendar-id` | string | ID of the office365 calendar associated with this record |
| `--linked-resource-ids` | string | Comma-separated string of linked resource IDs (read-only alternative view of LinkedResources). |
| `--only-for-contacts` | bool | When true, only contacts (non-member customers) can book this resource. |
| `--only-for-members` | bool | When true, only active members (coworkers with a plan) can book this resource. |
| `--only-for-invoicing-business` | bool | When true, only coworkers invoiced by this specific location can book this resource. |
| `--cancellation-fee-product-id` | long | ID of the cancellation fee product linked to this record |
| `--charge-cancellation-fee` | bool | When true, a fee is charged for late cancellations (past the LateCancellationLimit). |
| `--cancellation-fee-type` | enum | How the cancellation fee is calculated: Absolute (fixed amount) or Percentage (of booking cost). |
| `--cancellation-fee-amount` | decimal | Fixed cancellation fee amount. Used when CancellationFeeType is Absolute. |
| `--from-cancellation-fee-amount` | range | |
| `--to-cancellation-fee-amount` | range | |
| `--cancellation-fee-percentage` | decimal | Cancellation fee as a percentage of the booking cost. Used when CancellationFeeType is Percentage. |
| `--from-cancellation-fee-percentage` | range | |
| `--to-cancellation-fee-percentage` | range | |
| `--repeat-booking-quantity-limit` | int | Maximum number of occurrences allowed when creating a recurring booking for this resource. |
| `--from-repeat-booking-quantity-limit` | range | |
| `--to-repeat-booking-quantity-limit` | range | |
| `--repeat-booking-period-limit-in-months` | int | Maximum time span (in months) over which a recurring booking series can extend. |
| `--from-repeat-booking-period-limit-in-months` | range | |
| `--to-repeat-booking-period-limit-in-months` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Resource create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Display name of the resource (e.g., 'Board Room A', 'Phone Booth 3'). |
| `--system-resource-type` | enum, required | Built-in resource category used for system behaviour (e.g., MeetingRoom, HotDesk, PhoneBooth). Distinct from the custom ResourceType. |
| `--resource-type-id` | long, required | ID of the resource type linked to this record |
| `--description` | string | Free-text description shown to users when viewing the resource details. |
| `--new-picture-url` | string | URL of a new file to upload as the picture |
| `--clear-picture-file` | bool | Set to true to remove the current picture file |
| `--email-confirmation-content` | string | Custom HTML or text included in booking confirmation emails for this resource. |
| `--visible` | bool | Whether the resource is visible and bookable by end users. Hidden resources can still be booked by admins. |
| `--requires-confirmation` | bool | When true, bookings for this resource are held as pending until an admin approves them. |
| `--display-order` | int, required | Sort position when listing resources. Lower values appear first. |
| `--group-name` | string | Optional grouping label used to cluster related resources together in the UI (e.g., 'Floor 2'). |
| `--projector` | bool | Amenity flag: resource has a projector. |
| `--internet` | bool | Amenity flag: resource has internet access. |
| `--conference-phone` | bool | Amenity flag: resource has a conference phone. |
| `--standard-phone` | bool | Amenity flag: resource has a standard phone. |
| `--white-board` | bool | Amenity flag: resource has a whiteboard. |
| `--large-display` | bool | Amenity flag: resource has a large display. |
| `--catering` | bool | Amenity flag: catering is available for this resource. |
| `--tea-and-coffee` | bool | Amenity flag: tea and coffee are available. |
| `--drinks` | bool | Amenity flag: drinks are available. |
| `--security-lock` | bool | Amenity flag: resource has a security lock. |
| `--cctv` | bool | Amenity flag: resource has CCTV coverage. |
| `--voice-recorder` | bool | Amenity flag: resource has a voice recorder. |
| `--air-conditioning` | bool | Amenity flag: resource has air conditioning. |
| `--heating` | bool | Amenity flag: resource has heating. |
| `--natural-light` | bool | Amenity flag: resource has natural light. |
| `--standing-desk` | bool | Amenity flag: resource has a standing desk. |
| `--quiet-zone` | bool | Amenity flag: resource is located in a quiet zone. |
| `--wireless-charger` | bool | Amenity flag: resource has a wireless charger. |
| `--privacy-screen` | bool | Amenity flag: resource has a privacy screen. |
| `--soundproof` | bool | Amenity flag: resource is soundproof. |
| `--video-conferencing` | bool | Amenity flag: resource has video conferencing equipment. |
| `--dual-display-screen` | bool | Amenity flag: resource has a dual display screen. |
| `--display-screen` | bool | Amenity flag: resource has a display screen. |
| `--wireless-presentation` | bool | Amenity flag: resource has wireless presentation capabilities. |
| `--pa-system` | bool | Amenity flag: resource has a PA system. |
| `--desktop-monitor` | bool | Amenity flag: resource has a desktop monitor. |
| `--flip-chart` | bool | Amenity flag: resource has a flip chart. |
| `--secure-storage` | bool | Amenity flag: resource has secure storage. |
| `--allow-multiple-bookings` | bool | When true, overlapping bookings are permitted up to the Allocation capacity. |
| `--allocation` | int | Maximum number of attendees or concurrent bookings allowed. Used with AllowMultipleBookings to control capacity. |
| `--limit-visitors-to-allocation` | bool | When true, the total number of visitors added to a booking cannot exceed the Allocation capacity. |
| `--book-in-advance-limit` | decimal | Maximum number of days in advance a booking can be made for this resource. Null means no limit. |
| `--late-booking-limit` | decimal | Minimum lead time (in minutes) required before a booking can start. Prevents last-minute bookings. |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee. |
| `--interval-limit` | int | Minimum interval (in minutes) between consecutive bookings on this resource, used as a buffer for setup or cleaning. |
| `--no-return-policy` | int | Cooldown in minutes: prevents the same user from booking this specific resource again within this window after their last booking ends. |
| `--no-return-policy-all-resources` | int | Cooldown in minutes: prevents the same user from booking any resource after booking this one, for the specified window. |
| `--no-return-policy-all-users` | int | Cooldown in minutes: prevents any user from booking this resource within the specified window after the previous booking ends. |
| `--max-booking-length` | int | Maximum allowed duration for a single booking on this resource, in minutes. |
| `--min-booking-length` | int | Minimum allowed duration for a single booking on this resource, in minutes. |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this resource |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this resource |
| `--teams` | list, repeat flag | List of teams linked to this record |
| `--added-teams` | list, repeat flag | The added teams value for this resource |
| `--removed-teams` | list, repeat flag | The removed teams value for this resource |
| `--shifts` | string | JSON-encoded shifts configuration defining the resource's availability schedule. |
| `--linked-resources` | list, repeat flag | List of linked resources linked to this record |
| `--added-linked-resources` | list, repeat flag | The added linked resources value for this resource |
| `--removed-linked-resources` | list, repeat flag | The removed linked resources value for this resource |
| `--google-calendar-id` | string | ID of the google calendar associated with this record |
| `--kisi-group-id` | string | ID of the kisi group associated with this record |
| `--access-control-group-id` | string | ID of the access control group associated with this record |
| `--longitude` | decimal | GPS longitude coordinate of the resource's physical location. |
| `--latitude` | decimal | GPS latitude coordinate of the resource's physical location. |
| `--hide-in-calendar` | bool | When true, this resource does not appear on the booking calendar view. |
| `--archived` | bool | When true, the resource is archived and hidden from all views. It cannot be booked. |
| `--use-shared-zoom-account` | bool | When true, bookings for this resource use the location's shared Zoom account to create virtual meetings. |
| `--zoom-access-token` | string | The zoom access token value for this resource |
| `--zoom-refresh-token` | string | The zoom refresh token value for this resource |
| `--zoom-user-id` | string | Zoom user ID used to host virtual meetings when UseSharedZoomAccount is false. |
| `--last-cleaned-at` | DateTime | Timestamp of the last cleaning event for this resource. |
| `--office365-calendar-id` | string | ID of the office365 calendar associated with this record |
| `--linked-resource-ids` | string | Comma-separated string of linked resource IDs (read-only alternative view of LinkedResources). |
| `--only-for-contacts` | bool | When true, only contacts (non-member customers) can book this resource. |
| `--only-for-members` | bool | When true, only active members (coworkers with a plan) can book this resource. |
| `--only-for-invoicing-business` | bool | When true, only coworkers invoiced by this specific location can book this resource. |
| `--booking-availability-exceptions` | list, repeat flag | List of booking availability exceptions linked to this record |
| `--added-booking-availability-exceptions` | list, repeat flag | The added booking availability exceptions value for this resource |
| `--removed-booking-availability-exceptions` | list, repeat flag | The removed booking availability exceptions value for this resource |
| `--cancellation-fee-product-id` | long | ID of the cancellation fee product linked to this record |
| `--charge-cancellation-fee` | bool | When true, a fee is charged for late cancellations (past the LateCancellationLimit). |
| `--cancellation-fee-type` | enum, required | How the cancellation fee is calculated: Absolute (fixed amount) or Percentage (of booking cost). |
| `--cancellation-fee-amount` | decimal | Fixed cancellation fee amount. Used when CancellationFeeType is Absolute. |
| `--cancellation-fee-percentage` | decimal | Cancellation fee as a percentage of the booking cost. Used when CancellationFeeType is Percentage. |
| `--repeat-booking-quantity-limit` | int | Maximum number of occurrences allowed when creating a recurring booking for this resource. |
| `--repeat-booking-period-limit-in-months` | int | Maximum time span (in months) over which a recurring booking series can extend. |
| `--time-slots` | JSON array or @filepath | The days and times this resource is available for booking. The year, month and day component of FromTime/ToTime is always 1976-01-01. |

#### Resource update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Display name of the resource (e.g., 'Board Room A', 'Phone Booth 3'). |
| `--system-resource-type` | enum | Built-in resource category used for system behaviour (e.g., MeetingRoom, HotDesk, PhoneBooth). Distinct from the custom ResourceType. |
| `--resource-type-id` | long | ID of the resource type linked to this record |
| `--description` | string | Free-text description shown to users when viewing the resource details. |
| `--new-picture-url` | string | URL of a new file to upload as the picture |
| `--clear-picture-file` | bool | Set to true to remove the current picture file |
| `--email-confirmation-content` | string | Custom HTML or text included in booking confirmation emails for this resource. |
| `--visible` | bool | Whether the resource is visible and bookable by end users. Hidden resources can still be booked by admins. |
| `--requires-confirmation` | bool | When true, bookings for this resource are held as pending until an admin approves them. |
| `--display-order` | int | Sort position when listing resources. Lower values appear first. |
| `--group-name` | string | Optional grouping label used to cluster related resources together in the UI (e.g., 'Floor 2'). |
| `--projector` | bool | Amenity flag: resource has a projector. |
| `--internet` | bool | Amenity flag: resource has internet access. |
| `--conference-phone` | bool | Amenity flag: resource has a conference phone. |
| `--standard-phone` | bool | Amenity flag: resource has a standard phone. |
| `--white-board` | bool | Amenity flag: resource has a whiteboard. |
| `--large-display` | bool | Amenity flag: resource has a large display. |
| `--catering` | bool | Amenity flag: catering is available for this resource. |
| `--tea-and-coffee` | bool | Amenity flag: tea and coffee are available. |
| `--drinks` | bool | Amenity flag: drinks are available. |
| `--security-lock` | bool | Amenity flag: resource has a security lock. |
| `--cctv` | bool | Amenity flag: resource has CCTV coverage. |
| `--voice-recorder` | bool | Amenity flag: resource has a voice recorder. |
| `--air-conditioning` | bool | Amenity flag: resource has air conditioning. |
| `--heating` | bool | Amenity flag: resource has heating. |
| `--natural-light` | bool | Amenity flag: resource has natural light. |
| `--standing-desk` | bool | Amenity flag: resource has a standing desk. |
| `--quiet-zone` | bool | Amenity flag: resource is located in a quiet zone. |
| `--wireless-charger` | bool | Amenity flag: resource has a wireless charger. |
| `--privacy-screen` | bool | Amenity flag: resource has a privacy screen. |
| `--soundproof` | bool | Amenity flag: resource is soundproof. |
| `--video-conferencing` | bool | Amenity flag: resource has video conferencing equipment. |
| `--dual-display-screen` | bool | Amenity flag: resource has a dual display screen. |
| `--display-screen` | bool | Amenity flag: resource has a display screen. |
| `--wireless-presentation` | bool | Amenity flag: resource has wireless presentation capabilities. |
| `--pa-system` | bool | Amenity flag: resource has a PA system. |
| `--desktop-monitor` | bool | Amenity flag: resource has a desktop monitor. |
| `--flip-chart` | bool | Amenity flag: resource has a flip chart. |
| `--secure-storage` | bool | Amenity flag: resource has secure storage. |
| `--allow-multiple-bookings` | bool | When true, overlapping bookings are permitted up to the Allocation capacity. |
| `--allocation` | int | Maximum number of attendees or concurrent bookings allowed. Used with AllowMultipleBookings to control capacity. |
| `--limit-visitors-to-allocation` | bool | When true, the total number of visitors added to a booking cannot exceed the Allocation capacity. |
| `--book-in-advance-limit` | decimal | Maximum number of days in advance a booking can be made for this resource. Null means no limit. |
| `--late-booking-limit` | decimal | Minimum lead time (in minutes) required before a booking can start. Prevents last-minute bookings. |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee. |
| `--interval-limit` | int | Minimum interval (in minutes) between consecutive bookings on this resource, used as a buffer for setup or cleaning. |
| `--no-return-policy` | int | Cooldown in minutes: prevents the same user from booking this specific resource again within this window after their last booking ends. |
| `--no-return-policy-all-resources` | int | Cooldown in minutes: prevents the same user from booking any resource after booking this one, for the specified window. |
| `--no-return-policy-all-users` | int | Cooldown in minutes: prevents any user from booking this resource within the specified window after the previous booking ends. |
| `--max-booking-length` | int | Maximum allowed duration for a single booking on this resource, in minutes. |
| `--min-booking-length` | int | Minimum allowed duration for a single booking on this resource, in minutes. |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this resource |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this resource |
| `--teams` | list, repeat flag | List of teams linked to this record |
| `--added-teams` | list, repeat flag | The added teams value for this resource |
| `--removed-teams` | list, repeat flag | The removed teams value for this resource |
| `--shifts` | string | JSON-encoded shifts configuration defining the resource's availability schedule. |
| `--linked-resources` | list, repeat flag | List of linked resources linked to this record |
| `--added-linked-resources` | list, repeat flag | The added linked resources value for this resource |
| `--removed-linked-resources` | list, repeat flag | The removed linked resources value for this resource |
| `--google-calendar-id` | string | ID of the google calendar associated with this record |
| `--kisi-group-id` | string | ID of the kisi group associated with this record |
| `--access-control-group-id` | string | ID of the access control group associated with this record |
| `--longitude` | decimal | GPS longitude coordinate of the resource's physical location. |
| `--latitude` | decimal | GPS latitude coordinate of the resource's physical location. |
| `--hide-in-calendar` | bool | When true, this resource does not appear on the booking calendar view. |
| `--archived` | bool | When true, the resource is archived and hidden from all views. It cannot be booked. |
| `--use-shared-zoom-account` | bool | When true, bookings for this resource use the location's shared Zoom account to create virtual meetings. |
| `--zoom-access-token` | string | The zoom access token value for this resource |
| `--zoom-refresh-token` | string | The zoom refresh token value for this resource |
| `--zoom-user-id` | string | Zoom user ID used to host virtual meetings when UseSharedZoomAccount is false. |
| `--last-cleaned-at` | DateTime | Timestamp of the last cleaning event for this resource. |
| `--office365-calendar-id` | string | ID of the office365 calendar associated with this record |
| `--linked-resource-ids` | string | Comma-separated string of linked resource IDs (read-only alternative view of LinkedResources). |
| `--only-for-contacts` | bool | When true, only contacts (non-member customers) can book this resource. |
| `--only-for-members` | bool | When true, only active members (coworkers with a plan) can book this resource. |
| `--only-for-invoicing-business` | bool | When true, only coworkers invoiced by this specific location can book this resource. |
| `--booking-availability-exceptions` | list, repeat flag | List of booking availability exceptions linked to this record |
| `--added-booking-availability-exceptions` | list, repeat flag | The added booking availability exceptions value for this resource |
| `--removed-booking-availability-exceptions` | list, repeat flag | The removed booking availability exceptions value for this resource |
| `--cancellation-fee-product-id` | long | ID of the cancellation fee product linked to this record |
| `--charge-cancellation-fee` | bool | When true, a fee is charged for late cancellations (past the LateCancellationLimit). |
| `--cancellation-fee-type` | enum | How the cancellation fee is calculated: Absolute (fixed amount) or Percentage (of booking cost). |
| `--cancellation-fee-amount` | decimal | Fixed cancellation fee amount. Used when CancellationFeeType is Absolute. |
| `--cancellation-fee-percentage` | decimal | Cancellation fee as a percentage of the booking cost. Used when CancellationFeeType is Percentage. |
| `--repeat-booking-quantity-limit` | int | Maximum number of occurrences allowed when creating a recurring booking for this resource. |
| `--repeat-booking-period-limit-in-months` | int | Maximum time span (in months) over which a recurring booking series can extend. |
| `--time-slots` | JSON array or @filepath | The days and times this resource is available for booking. The year, month and day component of FromTime/ToTime is always 1976-01-01. |

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
