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
| `nexudus calendarevents create --business-id <value> --name <value> --start-date <value> --end-date <value> --repeats <value> --which-events-to-update <value> --agent` | Create calendarevent |
| `nexudus calendarevents update <id> --name "New Name" --agent` | Update calendarevent |
| `nexudus calendarevents delete <id> --yes --agent` | Delete calendarevent (no prompt) |

#### CalendarEvent list filter options

`--business-id` (long), `--name`, `--host-full-name`, `--short-description`, `--long-description`, `--ticket-notes`, `--enable-wait-list` (bool), `--ask-buyer-address` (bool), `--show-event-attendees` (bool), `--location`, `--venue-address`, `--resource-id` (long), `--start-date` (DateTime), `--from-start-date` (range), `--to-start-date` (range), `--end-date` (DateTime), `--from-end-date` (range), `--to-end-date` (range), `--allocation` (int), `--from-allocation` (range), `--to-allocation` (range), `--publish-date` (DateTime), `--from-publish-date` (range), `--to-publish-date` (range), `--show-in-home-banner` (bool), `--show-in-home-page` (bool), `--allow-comments` (bool), `--include-zoom-invite` (bool), `--create-zoom-webinar-invite` (bool), `--zoom-webinar-alternative-hosts`, `--zoom-event-data`, `--zoom-meeting-id`, `--only-for-contacts` (bool), `--only-for-members` (bool), `--new-small-logo-url`, `--clear-small-logo-file` (bool), `--new-large-logo-url`, `--clear-large-logo-file` (bool), `--web-address`, `--facebook-page`, `--tickets-page`, `--repeat-series-unique-id`, `--repeat-event` (bool), `--repeats` (enum), `--which-events-to-update` (enum), `--repeat-every` (int), `--from-repeat-every` (range), `--to-repeat-every` (range), `--repeat-until` (DateTime), `--from-repeat-until` (range), `--to-repeat-until` (range), `--repeat-on-mondays` (bool), `--repeat-on-tuesdays` (bool), `--repeat-on-wednesdays` (bool), `--repeat-on-thursdays` (bool), `--repeat-on-fridays` (bool), `--repeat-on-saturdays` (bool), `--repeat-on-sundays` (bool), `--start-date-local` (DateTime), `--from-start-date-local` (range), `--to-start-date-local` (range), `--end-date-local` (DateTime), `--from-end-date-local` (range), `--to-end-date-local` (range), `--publish-date-local` (DateTime), `--from-publish-date-local` (range), `--to-publish-date-local` (range), `--after-event-notification-job-id`, `--send-after-event-notification` (bool), `--after-event-notification-text`, `--send-before-event-notification` (bool), `--has-event-form` (bool), `--send-event-form-by-email` (bool), `--form-page-id` (long), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CalendarEvent create options

`--business-id` (long, required), `--name` (required), `--host-full-name`, `--short-description`, `--long-description`, `--ticket-notes`, `--enable-wait-list` (bool), `--ask-buyer-address` (bool), `--show-event-attendees` (bool), `--location`, `--venue-address`, `--resource-id` (long), `--start-date` (DateTime, required), `--end-date` (DateTime, required), `--allocation` (int), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--publish-date` (DateTime), `--show-in-home-banner` (bool), `--show-in-home-page` (bool), `--allow-comments` (bool), `--include-zoom-invite` (bool), `--create-zoom-webinar-invite` (bool), `--zoom-webinar-alternative-hosts`, `--zoom-event-data`, `--zoom-meeting-id`, `--only-for-contacts` (bool), `--only-for-members` (bool), `--new-small-logo-url`, `--clear-small-logo-file` (bool), `--new-large-logo-url`, `--clear-large-logo-file` (bool), `--web-address`, `--facebook-page`, `--tickets-page`, `--repeat-series-unique-id`, `--repeat-event` (bool), `--repeats` (enum, required), `--which-events-to-update` (enum, required), `--repeat-every` (int), `--repeat-until` (DateTime), `--repeat-on-mondays` (bool), `--repeat-on-tuesdays` (bool), `--repeat-on-wednesdays` (bool), `--repeat-on-thursdays` (bool), `--repeat-on-fridays` (bool), `--repeat-on-saturdays` (bool), `--repeat-on-sundays` (bool), `--start-date-local` (DateTime), `--end-date-local` (DateTime), `--publish-date-local` (DateTime), `--after-event-notification-job-id`, `--send-after-event-notification` (bool), `--after-event-notification-text`, `--send-before-event-notification` (bool), `--has-event-form` (bool), `--send-event-form-by-email` (bool), `--form-page-id` (long)

#### CalendarEvent update options

`--business-id` (long), `--name`, `--host-full-name`, `--short-description`, `--long-description`, `--ticket-notes`, `--enable-wait-list` (bool), `--ask-buyer-address` (bool), `--show-event-attendees` (bool), `--location`, `--venue-address`, `--resource-id` (long), `--start-date` (DateTime), `--end-date` (DateTime), `--allocation` (int), `--event-categories` (list, repeat flag), `--added-event-categories` (list, repeat flag), `--removed-event-categories` (list, repeat flag), `--publish-date` (DateTime), `--show-in-home-banner` (bool), `--show-in-home-page` (bool), `--allow-comments` (bool), `--include-zoom-invite` (bool), `--create-zoom-webinar-invite` (bool), `--zoom-webinar-alternative-hosts`, `--zoom-event-data`, `--zoom-meeting-id`, `--only-for-contacts` (bool), `--only-for-members` (bool), `--new-small-logo-url`, `--clear-small-logo-file` (bool), `--new-large-logo-url`, `--clear-large-logo-file` (bool), `--web-address`, `--facebook-page`, `--tickets-page`, `--repeat-series-unique-id`, `--repeats` (enum), `--which-events-to-update` (enum), `--repeat-on-mondays` (bool), `--repeat-on-tuesdays` (bool), `--repeat-on-wednesdays` (bool), `--repeat-on-thursdays` (bool), `--repeat-on-fridays` (bool), `--repeat-on-saturdays` (bool), `--repeat-on-sundays` (bool), `--start-date-local` (DateTime), `--end-date-local` (DateTime), `--publish-date-local` (DateTime), `--after-event-notification-job-id`, `--send-after-event-notification` (bool), `--after-event-notification-text`, `--send-before-event-notification` (bool), `--has-event-form` (bool), `--send-event-form-by-email` (bool), `--form-page-id` (long)

**List properties (only returned by `get`, not by `list`):** `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`

#### CalendarEvent enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeats` | `1` Daily, `2` Weekly, `3` Monthly, `4` Yearly, `5` FirstOfMonth, `6` SecondOfMonth, `7` ThirdOfMonth, `8` LastOfMonth, `9` FourthOfMonth |
| `--which-events-to-update` | `1` UpdateThisEventOnly, `2` UpdateFutureEventsOnly, `3` UpdateAllEvents, `4` DeleteAllEvents, `5` DeleteEventsAfterThis, `6` UpdateEventProducts |

<!-- END:GENERATED entity=CalendarEvents -->
