# CalendarEvents

<!-- BEGIN:GENERATED entity=CalendarEvents -->

An event (CalendarEvent) is a physical, virtual, or hybrid event published on the Members Portal. Events can be free or monetised with ticket products. Physical events can be linked to a bookable resource, which blocks that resource from being booked for the event's duration. Virtual events use the Zoom integration for conference calls or webinars. Events support recurring series: set RepeatEvent = true on creation with Repeats, RepeatEvery, RepeatUntil, and the day-of-week flags; all repeat-configuration fields are create-only, and WhichEventsToUpdate controls the scope of updates or deletions to an existing series. Attendance can be restricted by customer type (OnlyForContacts, OnlyForMembers), plan, team, or specific customers. Set Allocation to cap total attendees and EnableWaitList to allow overflow sign-ups. Events with registered attendees cannot be deleted.

CalendarEvents support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus calendarevents list --agent` | List all calendarevents |
| `nexudus calendarevents list --id <id> --agent` | Filter by single ID |
| `nexudus calendarevents list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus calendarevents list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus calendarevents list --business-id <value> --name <value> --agent` | Filter calendarevents by properties |
| `nexudus calendarevents list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus calendarevents list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus calendarevents get <id> --agent` | Get single calendarevent |
| `nexudus calendarevents create --business-id <value> --name <value> --start-date <value> --end-date <value> --repeats <value> --which-events-to-update <value> --agent` | Create calendarevent |
| `nexudus calendarevents update <id> --name "New Name" --agent` | Update calendarevent |
| `nexudus calendarevents delete <id> --yes --agent` | Delete calendarevent (no prompt) |

#### CalendarEvent list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this event belongs to. |
| `--name` | string | Name of the event displayed on the Members Portal; required. |
| `--host-full-name` | string | Full name of the person hosting or presenting the event. |
| `--short-description` | string | Short plain-text summary shown under the event name on the Members Portal. |
| `--long-description` | string | Full HTML description shown when a customer opens the event on the Members Portal. |
| `--ticket-notes` | string | Additional notes appended to ticket confirmation emails. |
| `--enable-wait-list` | bool | Whether customers can join a waiting list when the event is at full capacity. |
| `--ask-buyer-address` | bool | Whether to request the buyer's postal address during ticket checkout. |
| `--show-event-attendees` | bool | Whether the attendee list is displayed on the Members Portal event page. |
| `--location` | string | Venue or room name displayed on the event page; changing it notifies registered attendees. |
| `--venue-address` | string | Street address of the event venue. |
| `--resource-id` | long | Optional ID of the bookable resource held for this event; it blocks that resource from being booked during the event's start and end times. |
| `--resource-name` | string |  |
| `--start-date` | DateTime | Event start date and time in UTC; must be before EndDate. |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--end-date` | DateTime | Event end date and time in UTC; must be after StartDate. |
| `--from-end-date` | range | |
| `--to-end-date` | range | |
| `--allocation` | int | Maximum total number of attendees for the event; leave empty for unlimited. The effective capacity is the lower of this value and the sum of the ticket products' allocations. |
| `--from-allocation` | range | |
| `--to-allocation` | range | |
| `--publish-date` | DateTime | UTC date and time the event becomes visible on the Members Portal; the system rounds it down to the nearest 15 minutes. Leave empty to keep the event unpublished. |
| `--from-publish-date` | range | |
| `--to-publish-date` | range | |
| `--show-in-home-banner` | bool | Whether this event is displayed in the home page banner on the Members Portal. |
| `--show-in-home-page` | bool | Whether this event is displayed on the Members Portal home page. |
| `--allow-comments` | bool | Whether customers can post comments on the event. |
| `--include-zoom-invite` | bool | Whether the system creates a Zoom conference call for this event and shares the link with attendees. |
| `--create-zoom-webinar-invite` | bool | Whether to create a Zoom webinar instead of a regular conference call for this event. |
| `--zoom-webinar-alternative-hosts` | string | Comma-separated email addresses of alternative Zoom hosts who can start the webinar. |
| `--only-for-contacts` | bool | Whether only customers without an active contract (contacts) can view and attend this event. |
| `--only-for-members` | bool | Whether only customers with an active contract (members) can view and attend this event. |
| `--small-logo-file-name` | string | Filename of the small event image shown in related-events sections (read-only; set via --new-small-logo-url) |
| `--new-small-logo-url` | string | URL of an image to upload as the small event image |
| `--clear-small-logo-file` | bool | Remove the current small event image |
| `--large-logo-file-name` | string | Filename of the large event image shown on the event list and detail page (read-only; set via --new-large-logo-url) |
| `--new-large-logo-url` | string | URL of an image to upload as the large event image |
| `--clear-large-logo-file` | bool | Remove the current large event image |
| `--web-address` | string | Optional URL of an external website related to this event. |
| `--facebook-page` | string | Optional URL of a Facebook event or page for this event. |
| `--tickets-page` | string | Optional URL of an external ticketing page for this event. |
| `--repeat-series-unique-id` | string | System-generated identifier shared by all occurrences in a recurring series; use it to find and update all events in that series. |
| `--repeat-event` | bool | Whether to create this event as a recurring series; only applies when creating the first event in the series. |
| `--repeats` | enum | Recurrence cycle for the series: Daily, Weekly, Monthly, Yearly, FirstOfMonth, SecondOfMonth, ThirdOfMonth, FourthOfMonth, or LastOfMonth. |
| `--which-events-to-update` | enum | For an update to a recurring event, selects the scope: UpdateThisEventOnly, UpdateFutureEventsOnly, UpdateAllEvents, DeleteAllEvents, DeleteEventsAfterThis, or UpdateEventProducts. |
| `--repeat-every` | int | Optional positive number of cycles between occurrences; for example, 2 with Weekly repeats every two weeks. |
| `--from-repeat-every` | range | |
| `--to-repeat-every` | range | |
| `--repeat-until` | DateTime | Optional final UTC date for creating occurrences in the recurring series; when omitted, occurrences are created for one year. |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--repeat-on-mondays` | bool | Whether the recurring series includes Mondays. |
| `--repeat-on-tuesdays` | bool | Whether the recurring series includes Tuesdays. |
| `--repeat-on-wednesdays` | bool | Whether the recurring series includes Wednesdays. |
| `--repeat-on-thursdays` | bool | Whether the recurring series includes Thursdays. |
| `--repeat-on-fridays` | bool | Whether the recurring series includes Fridays. |
| `--repeat-on-saturdays` | bool | Whether the recurring series includes Saturdays. |
| `--repeat-on-sundays` | bool | Whether the recurring series includes Sundays. |
| `--send-after-event-notification` | bool | Whether a follow-up notification email is sent to all attendees after the event ends. |
| `--after-event-notification-text` | string | Custom message body for the post-event notification email. |
| `--send-before-event-notification` | bool | Whether a reminder email is sent to attendees within 24 hours before the event starts. |
| `--has-event-form` | bool | Whether a form is linked to this event that attendees are asked to complete; the system sets this automatically from FormPage. |
| `--send-event-form-by-email` | bool | Whether the linked event form is sent to attendees by email, including follow-up reminders. |
| `--form-page-id` | long | Optional ID of the form page attendees are asked to complete for this event. |
| `--form-page-name` | string | Name of the linked form page |
| `--tariff-names` | string | Read-only display names of the plans this event is restricted to; change the Tariffs collection instead. |
| `--team-names` | string | Read-only display names of the teams this event is restricted to; change the Teams collection instead. |
| `--coworker-full-names` | string | Read-only display names of the customers this event is restricted to; change the Members collection instead. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CalendarEvent sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `StartDate` ascending. If no `--order-by` is specified, the API returns results ordered by `StartDate` (ascending).

#### CalendarEvent create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this event belongs to. |
| `--name` | string, required | Name of the event displayed on the Members Portal; required. |
| `--host-full-name` | string | Full name of the person hosting or presenting the event. |
| `--short-description` | string | Short plain-text summary shown under the event name on the Members Portal. |
| `--long-description` | string | Full HTML description shown when a customer opens the event on the Members Portal. |
| `--ticket-notes` | string | Additional notes appended to ticket confirmation emails. |
| `--enable-wait-list` | bool | Whether customers can join a waiting list when the event is at full capacity. |
| `--ask-buyer-address` | bool | Whether to request the buyer's postal address during ticket checkout. |
| `--show-event-attendees` | bool | Whether the attendee list is displayed on the Members Portal event page. |
| `--location` | string | Venue or room name displayed on the event page; changing it notifies registered attendees. |
| `--venue-address` | string | Street address of the event venue. |
| `--resource-id` | long | Optional ID of the bookable resource held for this event; it blocks that resource from being booked during the event's start and end times. |
| `--start-date` | DateTime, required | Event start date and time in UTC; must be before EndDate. |
| `--end-date` | DateTime, required | Event end date and time in UTC; must be after StartDate. |
| `--allocation` | int | Maximum total number of attendees for the event; leave empty for unlimited. The effective capacity is the lower of this value and the sum of the ticket products' allocations. |
| `--event-categories` | list, repeat flag | List of category IDs for this event; an empty list means the event has no categories. |
| `--added-event-categories` | list, repeat flag | The added event categories value for this calendar event |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this calendar event |
| `--publish-date` | DateTime | UTC date and time the event becomes visible on the Members Portal; the system rounds it down to the nearest 15 minutes. Leave empty to keep the event unpublished. |
| `--show-in-home-banner` | bool | Whether this event is displayed in the home page banner on the Members Portal. |
| `--show-in-home-page` | bool | Whether this event is displayed on the Members Portal home page. |
| `--allow-comments` | bool | Whether customers can post comments on the event. |
| `--include-zoom-invite` | bool | Whether the system creates a Zoom conference call for this event and shares the link with attendees. |
| `--create-zoom-webinar-invite` | bool | Whether to create a Zoom webinar instead of a regular conference call for this event. |
| `--zoom-webinar-alternative-hosts` | string | Comma-separated email addresses of alternative Zoom hosts who can start the webinar. |
| `--only-for-contacts` | bool | Whether only customers without an active contract (contacts) can view and attend this event. |
| `--only-for-members` | bool | Whether only customers with an active contract (members) can view and attend this event. |
| `--new-small-logo-url` | string | URL of an image to upload as the small event image |
| `--clear-small-logo-file` | bool | Remove the current small event image |
| `--new-large-logo-url` | string | URL of an image to upload as the large event image |
| `--clear-large-logo-file` | bool | Remove the current large event image |
| `--web-address` | string | Optional URL of an external website related to this event. |
| `--facebook-page` | string | Optional URL of a Facebook event or page for this event. |
| `--tickets-page` | string | Optional URL of an external ticketing page for this event. |
| `--repeat-series-unique-id` | string | System-generated identifier shared by all occurrences in a recurring series; use it to find and update all events in that series. |
| `--repeat-event` | bool | Whether to create this event as a recurring series; only applies when creating the first event in the series. |
| `--repeats` | enum, required | Recurrence cycle for the series: Daily, Weekly, Monthly, Yearly, FirstOfMonth, SecondOfMonth, ThirdOfMonth, FourthOfMonth, or LastOfMonth. |
| `--which-events-to-update` | enum, required | For an update to a recurring event, selects the scope: UpdateThisEventOnly, UpdateFutureEventsOnly, UpdateAllEvents, DeleteAllEvents, DeleteEventsAfterThis, or UpdateEventProducts. |
| `--repeat-every` | int | Optional positive number of cycles between occurrences; for example, 2 with Weekly repeats every two weeks. |
| `--repeat-until` | DateTime | Optional final UTC date for creating occurrences in the recurring series; when omitted, occurrences are created for one year. |
| `--repeat-on-mondays` | bool | Whether the recurring series includes Mondays. |
| `--repeat-on-tuesdays` | bool | Whether the recurring series includes Tuesdays. |
| `--repeat-on-wednesdays` | bool | Whether the recurring series includes Wednesdays. |
| `--repeat-on-thursdays` | bool | Whether the recurring series includes Thursdays. |
| `--repeat-on-fridays` | bool | Whether the recurring series includes Fridays. |
| `--repeat-on-saturdays` | bool | Whether the recurring series includes Saturdays. |
| `--repeat-on-sundays` | bool | Whether the recurring series includes Sundays. |
| `--send-after-event-notification` | bool | Whether a follow-up notification email is sent to all attendees after the event ends. |
| `--after-event-notification-text` | string | Custom message body for the post-event notification email. |
| `--send-before-event-notification` | bool | Whether a reminder email is sent to attendees within 24 hours before the event starts. |
| `--has-event-form` | bool | Whether a form is linked to this event that attendees are asked to complete; the system sets this automatically from FormPage. |
| `--send-event-form-by-email` | bool | Whether the linked event form is sent to attendees by email, including follow-up reminders. |
| `--form-page-id` | long | Optional ID of the form page attendees are asked to complete for this event. |
| `--tariffs` | list, repeat flag | List of plan IDs that restrict this event to members subscribed to those plans; an empty list means no plan restriction. |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--members` | list, repeat flag | List of customer IDs that restrict this event to those specific customers; an empty list means no customer restriction. |
| `--added-members` | list, repeat flag |  |
| `--removed-members` | list, repeat flag |  |
| `--teams` | list, repeat flag | List of team IDs that restrict this event to customers belonging to those teams; an empty list means no team restriction. |
| `--added-teams` | list, repeat flag |  |
| `--removed-teams` | list, repeat flag |  |

#### CalendarEvent update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this event belongs to. |
| `--name` | string | Name of the event displayed on the Members Portal; required. |
| `--host-full-name` | string | Full name of the person hosting or presenting the event. |
| `--short-description` | string | Short plain-text summary shown under the event name on the Members Portal. |
| `--long-description` | string | Full HTML description shown when a customer opens the event on the Members Portal. |
| `--ticket-notes` | string | Additional notes appended to ticket confirmation emails. |
| `--enable-wait-list` | bool | Whether customers can join a waiting list when the event is at full capacity. |
| `--ask-buyer-address` | bool | Whether to request the buyer's postal address during ticket checkout. |
| `--show-event-attendees` | bool | Whether the attendee list is displayed on the Members Portal event page. |
| `--location` | string | Venue or room name displayed on the event page; changing it notifies registered attendees. |
| `--venue-address` | string | Street address of the event venue. |
| `--resource-id` | long | Optional ID of the bookable resource held for this event; it blocks that resource from being booked during the event's start and end times. |
| `--start-date` | DateTime | Event start date and time in UTC; must be before EndDate. |
| `--end-date` | DateTime | Event end date and time in UTC; must be after StartDate. |
| `--allocation` | int | Maximum total number of attendees for the event; leave empty for unlimited. The effective capacity is the lower of this value and the sum of the ticket products' allocations. |
| `--event-categories` | list, repeat flag | List of category IDs for this event; an empty list means the event has no categories. |
| `--added-event-categories` | list, repeat flag | The added event categories value for this calendar event |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this calendar event |
| `--publish-date` | DateTime | UTC date and time the event becomes visible on the Members Portal; the system rounds it down to the nearest 15 minutes. Leave empty to keep the event unpublished. |
| `--show-in-home-banner` | bool | Whether this event is displayed in the home page banner on the Members Portal. |
| `--show-in-home-page` | bool | Whether this event is displayed on the Members Portal home page. |
| `--allow-comments` | bool | Whether customers can post comments on the event. |
| `--include-zoom-invite` | bool | Whether the system creates a Zoom conference call for this event and shares the link with attendees. |
| `--create-zoom-webinar-invite` | bool | Whether to create a Zoom webinar instead of a regular conference call for this event. |
| `--zoom-webinar-alternative-hosts` | string | Comma-separated email addresses of alternative Zoom hosts who can start the webinar. |
| `--only-for-contacts` | bool | Whether only customers without an active contract (contacts) can view and attend this event. |
| `--only-for-members` | bool | Whether only customers with an active contract (members) can view and attend this event. |
| `--new-small-logo-url` | string | URL of an image to upload as the small event image |
| `--clear-small-logo-file` | bool | Remove the current small event image |
| `--new-large-logo-url` | string | URL of an image to upload as the large event image |
| `--clear-large-logo-file` | bool | Remove the current large event image |
| `--web-address` | string | Optional URL of an external website related to this event. |
| `--facebook-page` | string | Optional URL of a Facebook event or page for this event. |
| `--tickets-page` | string | Optional URL of an external ticketing page for this event. |
| `--repeat-series-unique-id` | string | System-generated identifier shared by all occurrences in a recurring series; use it to find and update all events in that series. |
| `--repeats` | enum | Recurrence cycle for the series: Daily, Weekly, Monthly, Yearly, FirstOfMonth, SecondOfMonth, ThirdOfMonth, FourthOfMonth, or LastOfMonth. |
| `--which-events-to-update` | enum | For an update to a recurring event, selects the scope: UpdateThisEventOnly, UpdateFutureEventsOnly, UpdateAllEvents, DeleteAllEvents, DeleteEventsAfterThis, or UpdateEventProducts. |
| `--repeat-on-mondays` | bool | Whether the recurring series includes Mondays. |
| `--repeat-on-tuesdays` | bool | Whether the recurring series includes Tuesdays. |
| `--repeat-on-wednesdays` | bool | Whether the recurring series includes Wednesdays. |
| `--repeat-on-thursdays` | bool | Whether the recurring series includes Thursdays. |
| `--repeat-on-fridays` | bool | Whether the recurring series includes Fridays. |
| `--repeat-on-saturdays` | bool | Whether the recurring series includes Saturdays. |
| `--repeat-on-sundays` | bool | Whether the recurring series includes Sundays. |
| `--send-after-event-notification` | bool | Whether a follow-up notification email is sent to all attendees after the event ends. |
| `--after-event-notification-text` | string | Custom message body for the post-event notification email. |
| `--send-before-event-notification` | bool | Whether a reminder email is sent to attendees within 24 hours before the event starts. |
| `--has-event-form` | bool | Whether a form is linked to this event that attendees are asked to complete; the system sets this automatically from FormPage. |
| `--send-event-form-by-email` | bool | Whether the linked event form is sent to attendees by email, including follow-up reminders. |
| `--form-page-id` | long | Optional ID of the form page attendees are asked to complete for this event. |
| `--tariffs` | list, repeat flag | List of plan IDs that restrict this event to members subscribed to those plans; an empty list means no plan restriction. |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--members` | list, repeat flag | List of customer IDs that restrict this event to those specific customers; an empty list means no customer restriction. |
| `--added-members` | list, repeat flag |  |
| `--removed-members` | list, repeat flag |  |
| `--teams` | list, repeat flag | List of team IDs that restrict this event to customers belonging to those teams; an empty list means no team restriction. |
| `--added-teams` | list, repeat flag |  |
| `--removed-teams` | list, repeat flag |  |

#### CalendarEvent PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--host-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--send-event-form-by-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--coworker-full-names` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus calendarevents update <id> --host-full-name "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Members`, `AddedMembers`, `RemovedMembers`, `Teams`, `AddedTeams`, `RemovedTeams`

#### CalendarEvent enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeats` | `1` Daily, `2` Weekly, `3` Monthly, `4` Yearly, `5` FirstOfMonth, `6` SecondOfMonth, `7` ThirdOfMonth, `8` LastOfMonth, `9` FourthOfMonth |
| `--which-events-to-update` | `1` UpdateThisEventOnly, `2` UpdateFutureEventsOnly, `3` UpdateAllEvents, `4` DeleteAllEvents, `5` DeleteEventsAfterThis, `6` UpdateEventProducts |

<!-- END:GENERATED entity=CalendarEvents -->
