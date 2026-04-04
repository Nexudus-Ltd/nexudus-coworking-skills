# CalendarEvents

<!-- BEGIN:GENERATED entity=CalendarEvents -->

CalendarEvents support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus calendarevents list --agent` | List all calendarevents |
| `nexudus calendarevents list --id <id> --agent` | Filter by single ID |
| `nexudus calendarevents list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus calendarevents list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus calendarevents list --business-id <value> --name <value> --agent` | Filter calendarevents by properties |
| `nexudus calendarevents list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus calendarevents get <id> --agent` | Get single calendarevent |
| `nexudus calendarevents create --business-id <value> --name <value> --start-date <value> --end-date <value> --agent` | Create calendarevent |
| `nexudus calendarevents update <id> --name "New Name" --agent` | Update calendarevent |
| `nexudus calendarevents delete <id> --yes --agent` | Delete calendarevent (no prompt) |

#### CalendarEvent list filter options

`--business-id`, `--name`, `--host-full-name`, `--short-description`, `--long-description`, `--ticket-notes`, `--enable-wait-list`, `--ask-buyer-address`, `--show-event-attendees`, `--location`, `--venue-address`, `--resource-id`, `--start-date`, `--end-date`, `--allocation`, `--publish-date`, `--show-in-home-banner`, `--show-in-home-page`, `--allow-comments`, `--include-zoom-invite`, `--create-zoom-webinar-invite`, `--zoom-webinar-alternative-hosts`, `--zoom-event-data`, `--zoom-meeting-id`, `--only-for-contacts`, `--only-for-members`, `--new-small-logo-url`, `--clear-small-logo`, `--new-large-logo-url`, `--clear-large-logo`, `--web-address`, `--facebook-page`, `--tickets-page`, `--repeat-series-unique-id`, `--repeat-event`, `--repeats`, `--which-events-to-update`, `--repeat-every`, `--repeat-until`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--start-date-local`, `--end-date-local`, `--publish-date-local`, `--after-event-notification-job-id`, `--send-after-event-notification`, `--after-event-notification-text`, `--send-before-event-notification`, `--has-event-form`, `--send-event-form-by-email`, `--form-page-id`

#### CalendarEvent create options

`--business-id` (required), `--name` (required), `--host-full-name`, `--short-description`, `--long-description`, `--ticket-notes`, `--enable-wait-list`, `--ask-buyer-address`, `--show-event-attendees`, `--location`, `--venue-address`, `--resource-id`, `--start-date` (required), `--end-date` (required), `--allocation`, `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--publish-date`, `--show-in-home-banner`, `--show-in-home-page`, `--allow-comments`, `--include-zoom-invite`, `--create-zoom-webinar-invite`, `--zoom-webinar-alternative-hosts`, `--zoom-event-data`, `--zoom-meeting-id`, `--only-for-contacts`, `--only-for-members`, `--new-small-logo-url`, `--clear-small-logo`, `--new-large-logo-url`, `--clear-large-logo`, `--web-address`, `--facebook-page`, `--tickets-page`, `--comments` (list, repeat flag), `--added-comments` (list, repeat flag), `--removed-comments` (list, repeat flag), `--event-products` (list, repeat flag), `--added-event-products` (list, repeat flag), `--removed-event-products` (list, repeat flag), `--attendees` (list, repeat flag), `--added-attendees` (list, repeat flag), `--removed-attendees` (list, repeat flag), `--waiting-list` (list, repeat flag), `--added-waiting-list` (list, repeat flag), `--removed-waiting-list` (list, repeat flag), `--repeat-series-unique-id`, `--repeat-event`, `--repeats`, `--which-events-to-update`, `--repeat-every`, `--repeat-until`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--start-date-local`, `--end-date-local`, `--publish-date-local`, `--after-event-notification-job-id`, `--send-after-event-notification`, `--after-event-notification-text`, `--send-before-event-notification`, `--has-event-form`, `--send-event-form-by-email`, `--form-page-id`

#### CalendarEvent update options

`--business-id`, `--name`, `--host-full-name`, `--short-description`, `--long-description`, `--ticket-notes`, `--enable-wait-list`, `--ask-buyer-address`, `--show-event-attendees`, `--location`, `--venue-address`, `--resource-id`, `--start-date`, `--end-date`, `--allocation`, `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--publish-date`, `--show-in-home-banner`, `--show-in-home-page`, `--allow-comments`, `--include-zoom-invite`, `--create-zoom-webinar-invite`, `--zoom-webinar-alternative-hosts`, `--zoom-event-data`, `--zoom-meeting-id`, `--only-for-contacts`, `--only-for-members`, `--new-small-logo-url`, `--clear-small-logo`, `--new-large-logo-url`, `--clear-large-logo`, `--web-address`, `--facebook-page`, `--tickets-page`, `--comments` (list, repeat flag), `--added-comments` (list, repeat flag), `--removed-comments` (list, repeat flag), `--event-products` (list, repeat flag), `--added-event-products` (list, repeat flag), `--removed-event-products` (list, repeat flag), `--attendees` (list, repeat flag), `--added-attendees` (list, repeat flag), `--removed-attendees` (list, repeat flag), `--waiting-list` (list, repeat flag), `--added-waiting-list` (list, repeat flag), `--removed-waiting-list` (list, repeat flag), `--repeat-series-unique-id`, `--repeats`, `--which-events-to-update`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--start-date-local`, `--end-date-local`, `--publish-date-local`, `--after-event-notification-job-id`, `--send-after-event-notification`, `--after-event-notification-text`, `--send-before-event-notification`, `--has-event-form`, `--send-event-form-by-email`, `--form-page-id`

**List properties (only returned by `get`, not by `list`):** `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `Comments`, `AddedComments`, `RemovedComments`, `EventProducts`, `AddedEventProducts`, `RemovedEventProducts`, `Attendees`, `AddedAttendees`, `RemovedAttendees`, `WaitingList`, `AddedWaitingList`, `RemovedWaitingList`

<!-- END:GENERATED entity=CalendarEvents -->
