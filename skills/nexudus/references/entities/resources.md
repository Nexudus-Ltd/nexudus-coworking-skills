# Resources

<!-- BEGIN:GENERATED entity=Resources -->

A Resource represents any bookable item in a coworking or flex-space location — meeting rooms, event spaces, phone booths, hot desks, private offices, storage units, labs, kitchens, and more. Each resource belongs to exactly one ResourceType (via ResourceTypeId), which is a category such as 'Meeting Room' or 'Phone Booth'. Pricing is not set directly on a resource or its type. Instead, one or more booking rates (ExtraService records) are linked to a ResourceType to define pricing rules — each covering a specific charge period (hourly, daily, etc.) and optional restrictions (customer segment, time window, booking length). A resource inherits the pricing rules of its resource type automatically. This means that resources needing a different set of rates also need a different type. You must know the ResourceTypeId before creating a resource.

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
| `nexudus resources list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus resources get <id> --agent` | Get single resource |
| `nexudus resources create --business-id <value> --name <value> --system-resource-type <value> --resource-type-id <value> --display-order <value> --cancellation-fee-type <value> --agent` | Create resource |
| `nexudus resources update <id> --name "New Name" --agent` | Update resource |
| `nexudus resources delete <id> --yes --agent` | Delete resource (no prompt) |
| `nexudus resources run-command <key> <ids> --agent` | Run entity command |

#### Resource list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location where this resource is located. |
| `--name` | string | Display name of the resource (e.g., 'Board Room A', 'Phone Booth 3'). |
| `--system-resource-type` | enum | Built-in resource category used for system behaviour (e.g., MeetingRoom, HotDesk, PhoneBooth). AI agents use this value to guide customers asking for specific type of services to the right resource. Distinct from the custom ResourceType. |
| `--resource-type-id` | long | ID of the resource type assigned to this resource. The resource inherits every applicable booking rate (ExtraService) whose ResourceTypes relationship includes this type; use a different resource type when a resource needs a different set of rates. |
| `--description` | string | Free-text description shown to users when viewing the resource details. |
| `--new-picture-url` | string | URL of a new file to upload as the picture |
| `--clear-picture-file` | bool | Set to true to remove the current picture file |
| `--email-confirmation-content` | string | Custom HTML or text included in booking confirmation emails for this resource. |
| `--visible` | bool | Whether the resource is published and bookable by end users from the Members Portal and the app. Hidden resources can still be booked by admins. |
| `--requires-confirmation` | bool | When true, bookings for this resource are held as pending until an admin user approves them. |
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
| `--allow-multiple-bookings` | bool | When true, overlapping bookings are permitted and Allocation controls the maximum number of concurrent bookings. When false, only one booking at a time is allowed and Allocation is purely informational (physical capacity). |
| `--allocation` | int | When AllowMultipleBookings is true, this is the maximum number of overlapping bookings accepted. When AllowMultipleBookings is false, this is informational physical capacity (e.g., number of seats) and does not affect booking limits. |
| `--from-allocation` | range | |
| `--to-allocation` | range | |
| `--limit-visitors-to-allocation` | bool | When true, the total number of visitors added to a booking cannot exceed the Allocation capacity. |
| `--book-in-advance-limit` | decimal | Maximum number of hours in advance a booking can be made for this resource. Null means no limit. |
| `--from-book-in-advance-limit` | range | |
| `--to-book-in-advance-limit` | range | |
| `--late-booking-limit` | decimal | Minimum lead time in hours required before a booking can start. Negative values allow bookings after the start time. |
| `--from-late-booking-limit` | range | |
| `--to-late-booking-limit` | range | |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee. |
| `--from-late-cancellation-limit` | range | |
| `--to-late-cancellation-limit` | range | |
| `--interval-limit` | int | Fixed interval in minutes used for booking start times, end times, and durations. Must be a non-zero multiple of 15 minutes. |
| `--from-interval-limit` | range | |
| `--to-interval-limit` | range | |
| `--no-return-policy` | int | Required gap in minutes between bookings made by the same customer or team for this resource. |
| `--from-no-return-policy` | range | |
| `--to-no-return-policy` | range | |
| `--no-return-policy-all-resources` | int | Required gap in minutes before the same customer or team can book this or any other resource. |
| `--from-no-return-policy-all-resources` | range | |
| `--to-no-return-policy-all-resources` | range | |
| `--no-return-policy-all-users` | int | Required gap in minutes between all consecutive bookings for this resource, regardless of customer. |
| `--from-no-return-policy-all-users` | range | |
| `--to-no-return-policy-all-users` | range | |
| `--max-booking-length` | int | Maximum allowed duration for a single booking on this resource, in minutes. |
| `--from-max-booking-length` | range | |
| `--to-max-booking-length` | range | |
| `--min-booking-length` | int | Minimum allowed duration for a single booking on this resource, in minutes. |
| `--from-min-booking-length` | range | |
| `--to-min-booking-length` | range | |
| `--shifts` | string | Comma-separated list of shifts defining when the resource is available. Each shift uses the format 'NAME: START_TIME->END_TIME' where NAME is a descriptive label (cannot contain colons), and times are in 24-hour HH:MM format. Example: 'FULL DAY (9AM - 6PM): 09:00->18:00, MORNING (9AM - 1PM): 09:00->13:00, AFTERNOON (1PM - 6PM): 13:00->18:00'. The shift name must NOT contain ':' as it breaks parsing. |
| `--google-calendar-id` | string | ID of the google calendar associated with this record |
| `--kisi-group-id` | string | ID of the kisi group associated with this record |
| `--access-control-group-id` | string | ID of the access control group associated with this record (deprecated) |
| `--longitude` | decimal | GPS longitude coordinate of the resource's physical location. |
| `--from-longitude` | range | |
| `--to-longitude` | range | |
| `--latitude` | decimal | GPS latitude coordinate of the resource's physical location. |
| `--from-latitude` | range | |
| `--to-latitude` | range | |
| `--hide-in-calendar` | bool | When true, this resource does not appear on the booking calendar view in the admin panel. Use 'Visible' to control if the resource is visible in the Members Portal and the App |
| `--archived` | bool | When true, the resource is archived and hidden from all views. It cannot be booked. |
| `--use-shared-zoom-account` | bool | When true, bookings for this resource use the location's shared Zoom account to create virtual meetings. |
| `--zoom-access-token` | string | The zoom access token value for this resource |
| `--zoom-refresh-token` | string | The zoom refresh token value for this resource |
| `--zoom-user-id` | string | Zoom user ID used to host virtual meetings when UseSharedZoomAccount is false. |
| `--last-cleaned-at` | DateTime | Timestamp of the last cleaning event for this resource. |
| `--from-last-cleaned-at` | range | |
| `--to-last-cleaned-at` | range | |
| `--office365-calendar-id` | string | ID of the office365 calendar associated with this record |
| `--linked-resource-ids` | string | Comma-separated string of linked resource IDs (read-only view of LinkedResources). |
| `--only-for-contacts` | bool | When true, only contacts (customers without an active contract for a plan) can book this resource. |
| `--only-for-members` | bool | When true, only active members (customers with an active contract for a plan) can book this resource. |
| `--only-for-invoicing-business` | bool | When true, only customers with a home location set to the resource's location can book this resource. |
| `--cancellation-fee-product-id` | long | ID of the product representing the cancellation fee linked to this resource |
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

#### Resource sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### Resource create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location where this resource is located. |
| `--name` | string, required | Display name of the resource (e.g., 'Board Room A', 'Phone Booth 3'). |
| `--system-resource-type` | enum, required | Built-in resource category used for system behaviour (e.g., MeetingRoom, HotDesk, PhoneBooth). AI agents use this value to guide customers asking for specific type of services to the right resource. Distinct from the custom ResourceType. |
| `--resource-type-id` | long, required | ID of the resource type assigned to this resource. The resource inherits every applicable booking rate (ExtraService) whose ResourceTypes relationship includes this type; use a different resource type when a resource needs a different set of rates. |
| `--description` | string | Free-text description shown to users when viewing the resource details. |
| `--new-picture-url` | string | URL of a new file to upload as the picture |
| `--clear-picture-file` | bool | Set to true to remove the current picture file |
| `--email-confirmation-content` | string | Custom HTML or text included in booking confirmation emails for this resource. |
| `--visible` | bool | Whether the resource is published and bookable by end users from the Members Portal and the app. Hidden resources can still be booked by admins. |
| `--requires-confirmation` | bool | When true, bookings for this resource are held as pending until an admin user approves them. |
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
| `--allow-multiple-bookings` | bool | When true, overlapping bookings are permitted and Allocation controls the maximum number of concurrent bookings. When false, only one booking at a time is allowed and Allocation is purely informational (physical capacity). |
| `--allocation` | int | When AllowMultipleBookings is true, this is the maximum number of overlapping bookings accepted. When AllowMultipleBookings is false, this is informational physical capacity (e.g., number of seats) and does not affect booking limits. |
| `--limit-visitors-to-allocation` | bool | When true, the total number of visitors added to a booking cannot exceed the Allocation capacity. |
| `--book-in-advance-limit` | decimal | Maximum number of hours in advance a booking can be made for this resource. Null means no limit. |
| `--late-booking-limit` | decimal | Minimum lead time in hours required before a booking can start. Negative values allow bookings after the start time. |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee. |
| `--interval-limit` | int | Fixed interval in minutes used for booking start times, end times, and durations. Must be a non-zero multiple of 15 minutes. |
| `--no-return-policy` | int | Required gap in minutes between bookings made by the same customer or team for this resource. |
| `--no-return-policy-all-resources` | int | Required gap in minutes before the same customer or team can book this or any other resource. |
| `--no-return-policy-all-users` | int | Required gap in minutes between all consecutive bookings for this resource, regardless of customer. |
| `--max-booking-length` | int | Maximum allowed duration for a single booking on this resource, in minutes. |
| `--min-booking-length` | int | Minimum allowed duration for a single booking on this resource, in minutes. |
| `--tariffs` | list, repeat flag | List of tariffs (pricing plans) linked to this resource. Restricts bookings to customers on specific pricing plans. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this resource |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this resource |
| `--teams` | list, repeat flag | List of teams linked to this resource. Restricts bookings to members of specific teams. |
| `--added-teams` | list, repeat flag | The added teams value for this resource |
| `--removed-teams` | list, repeat flag | The removed teams value for this resource |
| `--shifts` | string | Comma-separated list of shifts defining when the resource is available. Each shift uses the format 'NAME: START_TIME->END_TIME' where NAME is a descriptive label (cannot contain colons), and times are in 24-hour HH:MM format. Example: 'FULL DAY (9AM - 6PM): 09:00->18:00, MORNING (9AM - 1PM): 09:00->13:00, AFTERNOON (1PM - 6PM): 13:00->18:00'. The shift name must NOT contain ':' as it breaks parsing. |
| `--linked-resources` | list, repeat flag | List of linked resources. Used to associate resources that make each other unavailable. For example, a larger room that divided and booked individually would be represented as three resources: A (linked to C), B (linked to C) and C (linked to A+B) |
| `--added-linked-resources` | list, repeat flag | The added linked resources value for this resource |
| `--removed-linked-resources` | list, repeat flag | The removed linked resources value for this resource |
| `--google-calendar-id` | string | ID of the google calendar associated with this record |
| `--kisi-group-id` | string | ID of the kisi group associated with this record |
| `--access-control-group-id` | string | ID of the access control group associated with this record (deprecated) |
| `--longitude` | decimal | GPS longitude coordinate of the resource's physical location. |
| `--latitude` | decimal | GPS latitude coordinate of the resource's physical location. |
| `--hide-in-calendar` | bool | When true, this resource does not appear on the booking calendar view in the admin panel. Use 'Visible' to control if the resource is visible in the Members Portal and the App |
| `--archived` | bool | When true, the resource is archived and hidden from all views. It cannot be booked. |
| `--use-shared-zoom-account` | bool | When true, bookings for this resource use the location's shared Zoom account to create virtual meetings. |
| `--zoom-access-token` | string | The zoom access token value for this resource |
| `--zoom-refresh-token` | string | The zoom refresh token value for this resource |
| `--zoom-user-id` | string | Zoom user ID used to host virtual meetings when UseSharedZoomAccount is false. |
| `--last-cleaned-at` | DateTime | Timestamp of the last cleaning event for this resource. |
| `--office365-calendar-id` | string | ID of the office365 calendar associated with this record |
| `--linked-resource-ids` | string | Comma-separated string of linked resource IDs (read-only view of LinkedResources). |
| `--only-for-contacts` | bool | When true, only contacts (customers without an active contract for a plan) can book this resource. |
| `--only-for-members` | bool | When true, only active members (customers with an active contract for a plan) can book this resource. |
| `--only-for-invoicing-business` | bool | When true, only customers with a home location set to the resource's location can book this resource. |
| `--booking-availability-exceptions` | list, repeat flag | List of booking availability exceptions (date ranges when this resource is unavailable or has special availability rules). |
| `--added-booking-availability-exceptions` | list, repeat flag | The added booking availability exceptions value for this resource |
| `--removed-booking-availability-exceptions` | list, repeat flag | The removed booking availability exceptions value for this resource |
| `--cancellation-fee-product-id` | long | ID of the product representing the cancellation fee linked to this resource |
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
| `--business-id` | long | ID of the location where this resource is located. |
| `--name` | string | Display name of the resource (e.g., 'Board Room A', 'Phone Booth 3'). |
| `--system-resource-type` | enum | Built-in resource category used for system behaviour (e.g., MeetingRoom, HotDesk, PhoneBooth). AI agents use this value to guide customers asking for specific type of services to the right resource. Distinct from the custom ResourceType. |
| `--resource-type-id` | long | ID of the resource type assigned to this resource. The resource inherits every applicable booking rate (ExtraService) whose ResourceTypes relationship includes this type; use a different resource type when a resource needs a different set of rates. |
| `--description` | string | Free-text description shown to users when viewing the resource details. |
| `--new-picture-url` | string | URL of a new file to upload as the picture |
| `--clear-picture-file` | bool | Set to true to remove the current picture file |
| `--email-confirmation-content` | string | Custom HTML or text included in booking confirmation emails for this resource. |
| `--visible` | bool | Whether the resource is published and bookable by end users from the Members Portal and the app. Hidden resources can still be booked by admins. |
| `--requires-confirmation` | bool | When true, bookings for this resource are held as pending until an admin user approves them. |
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
| `--allow-multiple-bookings` | bool | When true, overlapping bookings are permitted and Allocation controls the maximum number of concurrent bookings. When false, only one booking at a time is allowed and Allocation is purely informational (physical capacity). |
| `--allocation` | int | When AllowMultipleBookings is true, this is the maximum number of overlapping bookings accepted. When AllowMultipleBookings is false, this is informational physical capacity (e.g., number of seats) and does not affect booking limits. |
| `--limit-visitors-to-allocation` | bool | When true, the total number of visitors added to a booking cannot exceed the Allocation capacity. |
| `--book-in-advance-limit` | decimal | Maximum number of hours in advance a booking can be made for this resource. Null means no limit. |
| `--late-booking-limit` | decimal | Minimum lead time in hours required before a booking can start. Negative values allow bookings after the start time. |
| `--late-cancellation-limit` | int | Cut-off in minutes before the booking start time. Cancellations after this point are considered late and may incur a fee. |
| `--interval-limit` | int | Fixed interval in minutes used for booking start times, end times, and durations. Must be a non-zero multiple of 15 minutes. |
| `--no-return-policy` | int | Required gap in minutes between bookings made by the same customer or team for this resource. |
| `--no-return-policy-all-resources` | int | Required gap in minutes before the same customer or team can book this or any other resource. |
| `--no-return-policy-all-users` | int | Required gap in minutes between all consecutive bookings for this resource, regardless of customer. |
| `--max-booking-length` | int | Maximum allowed duration for a single booking on this resource, in minutes. |
| `--min-booking-length` | int | Minimum allowed duration for a single booking on this resource, in minutes. |
| `--tariffs` | list, repeat flag | List of tariffs (pricing plans) linked to this resource. Restricts bookings to customers on specific pricing plans. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this resource |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this resource |
| `--teams` | list, repeat flag | List of teams linked to this resource. Restricts bookings to members of specific teams. |
| `--added-teams` | list, repeat flag | The added teams value for this resource |
| `--removed-teams` | list, repeat flag | The removed teams value for this resource |
| `--shifts` | string | Comma-separated list of shifts defining when the resource is available. Each shift uses the format 'NAME: START_TIME->END_TIME' where NAME is a descriptive label (cannot contain colons), and times are in 24-hour HH:MM format. Example: 'FULL DAY (9AM - 6PM): 09:00->18:00, MORNING (9AM - 1PM): 09:00->13:00, AFTERNOON (1PM - 6PM): 13:00->18:00'. The shift name must NOT contain ':' as it breaks parsing. |
| `--linked-resources` | list, repeat flag | List of linked resources. Used to associate resources that make each other unavailable. For example, a larger room that divided and booked individually would be represented as three resources: A (linked to C), B (linked to C) and C (linked to A+B) |
| `--added-linked-resources` | list, repeat flag | The added linked resources value for this resource |
| `--removed-linked-resources` | list, repeat flag | The removed linked resources value for this resource |
| `--google-calendar-id` | string | ID of the google calendar associated with this record |
| `--kisi-group-id` | string | ID of the kisi group associated with this record |
| `--access-control-group-id` | string | ID of the access control group associated with this record (deprecated) |
| `--longitude` | decimal | GPS longitude coordinate of the resource's physical location. |
| `--latitude` | decimal | GPS latitude coordinate of the resource's physical location. |
| `--hide-in-calendar` | bool | When true, this resource does not appear on the booking calendar view in the admin panel. Use 'Visible' to control if the resource is visible in the Members Portal and the App |
| `--archived` | bool | When true, the resource is archived and hidden from all views. It cannot be booked. |
| `--use-shared-zoom-account` | bool | When true, bookings for this resource use the location's shared Zoom account to create virtual meetings. |
| `--zoom-access-token` | string | The zoom access token value for this resource |
| `--zoom-refresh-token` | string | The zoom refresh token value for this resource |
| `--zoom-user-id` | string | Zoom user ID used to host virtual meetings when UseSharedZoomAccount is false. |
| `--last-cleaned-at` | DateTime | Timestamp of the last cleaning event for this resource. |
| `--office365-calendar-id` | string | ID of the office365 calendar associated with this record |
| `--linked-resource-ids` | string | Comma-separated string of linked resource IDs (read-only view of LinkedResources). |
| `--only-for-contacts` | bool | When true, only contacts (customers without an active contract for a plan) can book this resource. |
| `--only-for-members` | bool | When true, only active members (customers with an active contract for a plan) can book this resource. |
| `--only-for-invoicing-business` | bool | When true, only customers with a home location set to the resource's location can book this resource. |
| `--booking-availability-exceptions` | list, repeat flag | List of booking availability exceptions (date ranges when this resource is unavailable or has special availability rules). |
| `--added-booking-availability-exceptions` | list, repeat flag | The added booking availability exceptions value for this resource |
| `--removed-booking-availability-exceptions` | list, repeat flag | The removed booking availability exceptions value for this resource |
| `--cancellation-fee-product-id` | long | ID of the product representing the cancellation fee linked to this resource |
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
| `--system-resource-type` | `1` MeetingRoom, `2` HotDesk, `3` PrivateOffice, `4` EventSpace, `5` Lab, `6` Kitchen, `7` TreatmentRoom, `9` StorageUnit, `10` Machine, `11` DayPass, `12` PhoneBooth, `99` Other |
| `--cancellation-fee-type` | `1` Absolute, `2` Percentage |

<!-- END:GENERATED entity=Resources -->
