# CalendarEvents

<!-- BEGIN:GENERATED entity=CalendarEvents -->

A **CalendarEvent** represents a physical, virtual, or hybrid event published on the Members Portal. Events can be free or monetised with ticket products.

Physical events can be linked to a space resource via `ResourceId`, which automatically blocks that resource from being booked for the event's duration. Virtual events require the Zoom integration and support both conference calls (`IncludeZoomInvite`) and webinars (`CreateZoomWebinarInvite`).

Events support recurring schedules: set `RepeatEvent = true` on creation and configure `Repeats`, `RepeatEvery`, `RepeatUntil`, and the day-of-week flags. `RepeatEvent` and all repeat-configuration fields (`Repeats`, `RepeatEvery`, `RepeatUntil`, `RepeatOn*`) are create-only. Once an event series is created, only `WhichEventsToUpdate` can be used to update or delete events in the series. New events cannot be added to an existing series.

Attendance can be restricted to all customers, contacts only (`OnlyForContacts`), or members only (`OnlyForMembers`). Set `Allocation` to cap total attendees and enable `EnableWaitList` to allow overflow sign-ups.

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

`--business-id`, `--name`, `--host-full-name`, `--short-description`, `--long-description`, `--ticket-notes`, `--enable-wait-list`, `--ask-buyer-address`, `--show-event-attendees`, `--location`, `--venue-address`, `--resource-id`, `--start-date`, `--from-start-date` (range), `--to-start-date` (range), `--end-date`, `--from-end-date` (range), `--to-end-date` (range), `--allocation`, `--from-allocation` (range), `--to-allocation` (range), `--publish-date`, `--from-publish-date` (range), `--to-publish-date` (range), `--show-in-home-banner`, `--show-in-home-page`, `--allow-comments`, `--include-zoom-invite`, `--create-zoom-webinar-invite`, `--zoom-webinar-alternative-hosts`, `--zoom-event-data`, `--zoom-meeting-id`, `--only-for-contacts`, `--only-for-members`, `--new-small-logo-url`, `--clear-small-logo-file`, `--new-large-logo-url`, `--clear-large-logo-file`, `--web-address`, `--facebook-page`, `--tickets-page`, `--repeat-series-unique-id`, `--repeat-event`, `--repeats`, `--which-events-to-update`, `--repeat-every`, `--from-repeat-every` (range), `--to-repeat-every` (range), `--repeat-until`, `--from-repeat-until` (range), `--to-repeat-until` (range), `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--start-date-local`, `--from-start-date-local` (range), `--to-start-date-local` (range), `--end-date-local`, `--from-end-date-local` (range), `--to-end-date-local` (range), `--publish-date-local`, `--from-publish-date-local` (range), `--to-publish-date-local` (range), `--after-event-notification-job-id`, `--send-after-event-notification`, `--after-event-notification-text`, `--send-before-event-notification`, `--has-event-form`, `--send-event-form-by-email`, `--form-page-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CalendarEvent create options

`--business-id` (required), `--name` (required), `--host-full-name`, `--short-description`, `--long-description`, `--ticket-notes`, `--enable-wait-list`, `--ask-buyer-address`, `--show-event-attendees`, `--location`, `--venue-address`, `--resource-id`, `--start-date` (required), `--end-date` (required), `--allocation`, `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--publish-date`, `--show-in-home-banner`, `--show-in-home-page`, `--allow-comments`, `--include-zoom-invite`, `--create-zoom-webinar-invite`, `--zoom-webinar-alternative-hosts`, `--zoom-event-data`, `--zoom-meeting-id`, `--only-for-contacts`, `--only-for-members`, `--new-small-logo-url`, `--clear-small-logo-file`, `--new-large-logo-url`, `--clear-large-logo-file`, `--web-address`, `--facebook-page`, `--tickets-page`, `--repeat-series-unique-id`, `--repeat-event`, `--repeats`, `--which-events-to-update`, `--repeat-every`, `--repeat-until`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--start-date-local`, `--end-date-local`, `--publish-date-local`, `--after-event-notification-job-id`, `--send-after-event-notification`, `--after-event-notification-text`, `--send-before-event-notification`, `--has-event-form`, `--send-event-form-by-email`, `--form-page-id`

#### CalendarEvent update options

`--business-id`, `--name`, `--host-full-name`, `--short-description`, `--long-description`, `--ticket-notes`, `--enable-wait-list`, `--ask-buyer-address`, `--show-event-attendees`, `--location`, `--venue-address`, `--resource-id`, `--start-date`, `--end-date`, `--allocation`, `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--publish-date`, `--show-in-home-banner`, `--show-in-home-page`, `--allow-comments`, `--include-zoom-invite`, `--create-zoom-webinar-invite`, `--zoom-webinar-alternative-hosts`, `--zoom-event-data`, `--zoom-meeting-id`, `--only-for-contacts`, `--only-for-members`, `--new-small-logo-url`, `--clear-small-logo-file`, `--new-large-logo-url`, `--clear-large-logo-file`, `--web-address`, `--facebook-page`, `--tickets-page`, `--repeat-series-unique-id`, `--repeats`, `--which-events-to-update`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--start-date-local`, `--end-date-local`, `--publish-date-local`, `--after-event-notification-job-id`, `--send-after-event-notification`, `--after-event-notification-text`, `--send-before-event-notification`, `--has-event-form`, `--send-event-form-by-email`, `--form-page-id`

**List properties (only returned by `get`, not by `list`):** `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`

#### CalendarEvent enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeats` | `1` Daily, `2` Weekly, `3` Monthly, `4` Yearly, `5` FirstOfMonth, `6` SecondOfMonth, `7` ThirdOfMonth, `8` LastOfMonth, `9` FourthOfMonth |
| `--which-events-to-update` | `1` UpdateThisEventOnly, `2` UpdateFutureEventsOnly, `3` UpdateAllEvents, `4` DeleteAllEvents, `5` DeleteEventsAfterThis, `6` UpdateEventProducts |

<!-- END:GENERATED entity=CalendarEvents -->
