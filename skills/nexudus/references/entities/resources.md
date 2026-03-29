# Resources

<!-- BEGIN:GENERATED entity=Resources -->

> **Resource → ResourceType → ExtraService (pricing):** Every resource belongs to exactly one `ResourceType` (via `ResourceTypeId`). A resource type is a category of bookable space (e.g., "Meeting Room", "Hot Desk"). Pricing rules for a resource type are defined as `ExtraService` records — each extra service can apply to one or more resource types and represents a specific price for a given charge period and set of restrictions. You cannot create a resource without first knowing the ID of an existing resource type.

Resources support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resources list --agent` | List all resources |
| `nexudus resources list --query "search" --agent` | Search resources by name |
| `nexudus resources list --page 2 --size 10 --agent` | Paginated list |
| `nexudus resources get <id> --agent` | Get single resource |
| `nexudus resources create --business <value> --name <value> --resource-type-id <value> --agent` | Create resource |
| `nexudus resources update <id> --name "New Name" --agent` | Update resource |
| `nexudus resources delete <id> --yes --agent` | Delete resource (no prompt) |

#### Resource create options

`--business` (required), `--name` (required), `--system-resource-type`, `--resource-type-id` (required), `--description`, `--email-confirmation-content`, `--visible`, `--requires-confirmation`, `--display-order`, `--group-name`, `--projector`, `--internet`, `--conference-phone`, `--standard-phone`, `--white-board`, `--large-display`, `--catering`, `--tea-and-coffee`, `--drinks`, `--security-lock`, `--cctv`, `--voice-recorder`, `--air-conditioning`, `--heating`, `--natural-light`, `--standing-desk`, `--quiet-zone`, `--wireless-charger`, `--privacy-screen`, `--soundproof`, `--video-conferencing`, `--dual-display-screen`, `--display-screen`, `--wireless-presentation`, `--pa-system`, `--desktop-monitor`, `--flip-chart`, `--secure-storage`, `--allow-multiple-bookings`, `--allocation`, `--limit-visitors-to-allocation`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--max-booking-length`, `--min-booking-length`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--shifts`, `--linked-resources` (list, repeat flag), `--added-linked-resources` (list, repeat flag), `--removed-linked-resources` (list, repeat flag), `--longitude`, `--latitude`, `--hide-in-calendar`, `--archived`, `--use-shared-zoom-account`, `--zoom-user-id`, `--last-cleaned-at`, `--linked-resource-ids`, `--only-for-contacts`, `--only-for-members`, `--only-for-invoicing-business`, `--booking-availability-exceptions` (list, repeat flag), `--added-booking-availability-exceptions` (list, repeat flag), `--removed-booking-availability-exceptions` (list, repeat flag), `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`, `--new-picture-url`, `--picture-file-name`, `--clear-picture-file`

#### Resource update options

`--name`, `--system-resource-type`, `--resource-type-id`, `--description`, `--email-confirmation-content`, `--visible`, `--requires-confirmation`, `--display-order`, `--group-name`, `--projector`, `--internet`, `--conference-phone`, `--standard-phone`, `--white-board`, `--large-display`, `--catering`, `--tea-and-coffee`, `--drinks`, `--security-lock`, `--cctv`, `--voice-recorder`, `--air-conditioning`, `--heating`, `--natural-light`, `--standing-desk`, `--quiet-zone`, `--wireless-charger`, `--privacy-screen`, `--soundproof`, `--video-conferencing`, `--dual-display-screen`, `--display-screen`, `--wireless-presentation`, `--pa-system`, `--desktop-monitor`, `--flip-chart`, `--secure-storage`, `--allow-multiple-bookings`, `--allocation`, `--limit-visitors-to-allocation`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--max-booking-length`, `--min-booking-length`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--shifts`, `--linked-resources` (list, repeat flag), `--added-linked-resources` (list, repeat flag), `--removed-linked-resources` (list, repeat flag), `--longitude`, `--latitude`, `--hide-in-calendar`, `--archived`, `--use-shared-zoom-account`, `--zoom-user-id`, `--last-cleaned-at`, `--linked-resource-ids`, `--only-for-contacts`, `--only-for-members`, `--only-for-invoicing-business`, `--booking-availability-exceptions` (list, repeat flag), `--added-booking-availability-exceptions` (list, repeat flag), `--removed-booking-availability-exceptions` (list, repeat flag), `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`, `--new-picture-url`, `--picture-file-name`, `--clear-picture-file`

### Resource (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`, `ResourceTypeId`, `ResourceTypeName`, `Visible`, `GroupName`, `Allocation`, `Archived`, `OnlyForContacts`, `OnlyForMembers`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Teams`, `AddedTeams`, `RemovedTeams`, `LinkedResources`, `AddedLinkedResources`, `RemovedLinkedResources`, `BookingAvailabilityExceptions`, `AddedBookingAvailabilityExceptions`, `RemovedBookingAvailabilityExceptions`

#### Resource enum values

| Option | Valid values |
| ------ | ------------ |
| `--system-resource-type` | `0` None, `1` MeetingRoom, `2` HotDesk, `3` PrivateOffice, `4` EventSpace, `5` Lab, `6` Kitchen, `7` TreatmentRoom, `9` StorageUnit, `10` Machine, `11` DayPass, `12` PhoneBooth, `99` Other |
| `--cancellation-fee-type` | `0` None, `1` Absolute, `2` Percentage |

<!-- END:GENERATED entity=Resources -->
