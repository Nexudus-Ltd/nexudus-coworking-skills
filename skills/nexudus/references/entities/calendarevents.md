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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | The location this event belongs to |
| `--name` | string | Event name |
| `--host-full-name` | string | Full name of the event host or presenter |
| `--short-description` | string | Brief summary shown under the event name on the Members Portal |
| `--long-description` | string | Full event description visible when a customer opens the event on the Members Portal |
| `--ticket-notes` | string | Additional notes included in ticket confirmation emails |
| `--enable-wait-list` | bool | Allow customers to join a waiting list when the event is at full capacity |
| `--ask-buyer-address` | bool | Request the buyer's postal address during ticket checkout |
| `--show-event-attendees` | bool | Display the attendee list on the Members Portal event page |
| `--location` | string | Venue or room name displayed on the event page |
| `--venue-address` | string | Street address of the event venue |
| `--resource-id` | long | Resource linked to this event; automatically blocked from bookings for the event's duration |
| `--start-date` | DateTime | Event start date and time (UTC) |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--end-date` | DateTime | Event end date and time (UTC) |
| `--from-end-date` | range | |
| `--to-end-date` | range | |
| `--allocation` | int | Maximum number of attendees; leave empty for unlimited |
| `--from-allocation` | range | |
| `--to-allocation` | range | |
| `--publish-date` | DateTime | Date and time the event becomes visible on the Members Portal (UTC) |
| `--from-publish-date` | range | |
| `--to-publish-date` | range | |
| `--show-in-home-banner` | bool | Display this event in the home page banner on the Members Portal |
| `--show-in-home-page` | bool | Display this event on the Members Portal home page |
| `--allow-comments` | bool | Allow customers to post comments on the event |
| `--include-zoom-invite` | bool | Attach a Zoom conference call link to this event |
| `--create-zoom-webinar-invite` | bool | Create a Zoom webinar instead of a regular conference call |
| `--zoom-webinar-alternative-hosts` | string | Comma-separated email addresses of alternative Zoom hosts who can start the meeting |
| `--zoom-event-data` | string | Raw Zoom meeting data returned after the Zoom event is created |
| `--zoom-meeting-id` | string | Zoom meeting or webinar ID |
| `--only-for-contacts` | bool | Restrict event attendance to contacts only |
| `--only-for-members` | bool | Restrict event attendance to members only |
| `--new-small-logo-url` | string | URL of an image to upload as the small event image |
| `--clear-small-logo-file` | bool | Remove the current small event image |
| `--new-large-logo-url` | string | URL of an image to upload as the large event image |
| `--clear-large-logo-file` | bool | Remove the current large event image |
| `--web-address` | string | URL of an external website related to this event |
| `--facebook-page` | string | URL of a Facebook event or page for this event |
| `--tickets-page` | string | URL of an external ticketing page for this event |
| `--repeat-series-unique-id` | string | Unique identifier shared by all occurrences in a repeat series |
| `--repeat-event` | bool | Create this event as a recurring series (create only) |
| `--repeats` | enum | Recurrence pattern for the event series |
| `--which-events-to-update` | enum | Which events in the recurring series to update (update only) |
| `--repeat-every` | int | Number of cycles between occurrences (e.g. 2 with Weekly means every two weeks) |
| `--from-repeat-every` | range | |
| `--to-repeat-every` | range | |
| `--repeat-until` | DateTime | Date the recurring series ends (create only) |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--repeat-on-mondays` | bool | Include Mondays in the recurring schedule |
| `--repeat-on-tuesdays` | bool | Include Tuesdays in the recurring schedule |
| `--repeat-on-wednesdays` | bool | Include Wednesdays in the recurring schedule |
| `--repeat-on-thursdays` | bool | Include Thursdays in the recurring schedule |
| `--repeat-on-fridays` | bool | Include Fridays in the recurring schedule |
| `--repeat-on-saturdays` | bool | Include Saturdays in the recurring schedule |
| `--repeat-on-sundays` | bool | Include Sundays in the recurring schedule |
| `--start-date-local` | DateTime | Event start date and time in the location's local timezone |
| `--from-start-date-local` | range | |
| `--to-start-date-local` | range | |
| `--end-date-local` | DateTime | Event end date and time in the location's local timezone |
| `--from-end-date-local` | range | |
| `--to-end-date-local` | range | |
| `--publish-date-local` | DateTime | Publish date and time in the location's local timezone |
| `--from-publish-date-local` | range | |
| `--to-publish-date-local` | range | |
| `--after-event-notification-job-id` | string | Background job ID for the scheduled post-event notification email |
| `--send-after-event-notification` | bool | Send a follow-up notification email to attendees after the event ends |
| `--after-event-notification-text` | string | Custom message body for the post-event notification email |
| `--send-before-event-notification` | bool | Send a reminder notification email to attendees before the event starts |
| `--has-event-form` | bool | A form is linked to this event that attendees are asked to complete |
| `--send-event-form-by-email` | bool | Send the linked event form to attendees by email |
| `--form-page-id` | long | ID of the form page linked to this event |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CalendarEvent create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | The location this event belongs to |
| `--name` | string, required | Event name |
| `--host-full-name` | string | Full name of the event host or presenter |
| `--short-description` | string | Brief summary shown under the event name on the Members Portal |
| `--long-description` | string | Full event description visible when a customer opens the event on the Members Portal |
| `--ticket-notes` | string | Additional notes included in ticket confirmation emails |
| `--enable-wait-list` | bool | Allow customers to join a waiting list when the event is at full capacity |
| `--ask-buyer-address` | bool | Request the buyer's postal address during ticket checkout |
| `--show-event-attendees` | bool | Display the attendee list on the Members Portal event page |
| `--location` | string | Venue or room name displayed on the event page |
| `--venue-address` | string | Street address of the event venue |
| `--resource-id` | long | Resource linked to this event; automatically blocked from bookings for the event's duration |
| `--start-date` | DateTime, required | Event start date and time (UTC) |
| `--end-date` | DateTime, required | Event end date and time (UTC) |
| `--allocation` | int | Maximum number of attendees; leave empty for unlimited |
| `--event-categories` | list, repeat flag | Categories assigned to this event |
| `--added-event-categories` | list, repeat flag | The added event categories value for this calendar event |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this calendar event |
| `--publish-date` | DateTime | Date and time the event becomes visible on the Members Portal (UTC) |
| `--show-in-home-banner` | bool | Display this event in the home page banner on the Members Portal |
| `--show-in-home-page` | bool | Display this event on the Members Portal home page |
| `--allow-comments` | bool | Allow customers to post comments on the event |
| `--include-zoom-invite` | bool | Attach a Zoom conference call link to this event |
| `--create-zoom-webinar-invite` | bool | Create a Zoom webinar instead of a regular conference call |
| `--zoom-webinar-alternative-hosts` | string | Comma-separated email addresses of alternative Zoom hosts who can start the meeting |
| `--zoom-event-data` | string | Raw Zoom meeting data returned after the Zoom event is created |
| `--zoom-meeting-id` | string | Zoom meeting or webinar ID |
| `--only-for-contacts` | bool | Restrict event attendance to contacts only |
| `--only-for-members` | bool | Restrict event attendance to members only |
| `--new-small-logo-url` | string | URL of an image to upload as the small event image |
| `--clear-small-logo-file` | bool | Remove the current small event image |
| `--new-large-logo-url` | string | URL of an image to upload as the large event image |
| `--clear-large-logo-file` | bool | Remove the current large event image |
| `--web-address` | string | URL of an external website related to this event |
| `--facebook-page` | string | URL of a Facebook event or page for this event |
| `--tickets-page` | string | URL of an external ticketing page for this event |
| `--repeat-series-unique-id` | string | Unique identifier shared by all occurrences in a repeat series |
| `--repeat-event` | bool | Create this event as a recurring series (create only) |
| `--repeats` | enum, required | Recurrence pattern for the event series |
| `--which-events-to-update` | enum, required | Which events in the recurring series to update (update only) |
| `--repeat-every` | int | Number of cycles between occurrences (e.g. 2 with Weekly means every two weeks) |
| `--repeat-until` | DateTime | Date the recurring series ends (create only) |
| `--repeat-on-mondays` | bool | Include Mondays in the recurring schedule |
| `--repeat-on-tuesdays` | bool | Include Tuesdays in the recurring schedule |
| `--repeat-on-wednesdays` | bool | Include Wednesdays in the recurring schedule |
| `--repeat-on-thursdays` | bool | Include Thursdays in the recurring schedule |
| `--repeat-on-fridays` | bool | Include Fridays in the recurring schedule |
| `--repeat-on-saturdays` | bool | Include Saturdays in the recurring schedule |
| `--repeat-on-sundays` | bool | Include Sundays in the recurring schedule |
| `--start-date-local` | DateTime | Event start date and time in the location's local timezone |
| `--end-date-local` | DateTime | Event end date and time in the location's local timezone |
| `--publish-date-local` | DateTime | Publish date and time in the location's local timezone |
| `--after-event-notification-job-id` | string | Background job ID for the scheduled post-event notification email |
| `--send-after-event-notification` | bool | Send a follow-up notification email to attendees after the event ends |
| `--after-event-notification-text` | string | Custom message body for the post-event notification email |
| `--send-before-event-notification` | bool | Send a reminder notification email to attendees before the event starts |
| `--has-event-form` | bool | A form is linked to this event that attendees are asked to complete |
| `--send-event-form-by-email` | bool | Send the linked event form to attendees by email |
| `--form-page-id` | long | ID of the form page linked to this event |

#### CalendarEvent update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | The location this event belongs to |
| `--name` | string | Event name |
| `--host-full-name` | string | Full name of the event host or presenter |
| `--short-description` | string | Brief summary shown under the event name on the Members Portal |
| `--long-description` | string | Full event description visible when a customer opens the event on the Members Portal |
| `--ticket-notes` | string | Additional notes included in ticket confirmation emails |
| `--enable-wait-list` | bool | Allow customers to join a waiting list when the event is at full capacity |
| `--ask-buyer-address` | bool | Request the buyer's postal address during ticket checkout |
| `--show-event-attendees` | bool | Display the attendee list on the Members Portal event page |
| `--location` | string | Venue or room name displayed on the event page |
| `--venue-address` | string | Street address of the event venue |
| `--resource-id` | long | Resource linked to this event; automatically blocked from bookings for the event's duration |
| `--start-date` | DateTime | Event start date and time (UTC) |
| `--end-date` | DateTime | Event end date and time (UTC) |
| `--allocation` | int | Maximum number of attendees; leave empty for unlimited |
| `--event-categories` | list, repeat flag | Categories assigned to this event |
| `--added-event-categories` | list, repeat flag | The added event categories value for this calendar event |
| `--removed-event-categories` | list, repeat flag | The removed event categories value for this calendar event |
| `--publish-date` | DateTime | Date and time the event becomes visible on the Members Portal (UTC) |
| `--show-in-home-banner` | bool | Display this event in the home page banner on the Members Portal |
| `--show-in-home-page` | bool | Display this event on the Members Portal home page |
| `--allow-comments` | bool | Allow customers to post comments on the event |
| `--include-zoom-invite` | bool | Attach a Zoom conference call link to this event |
| `--create-zoom-webinar-invite` | bool | Create a Zoom webinar instead of a regular conference call |
| `--zoom-webinar-alternative-hosts` | string | Comma-separated email addresses of alternative Zoom hosts who can start the meeting |
| `--zoom-event-data` | string | Raw Zoom meeting data returned after the Zoom event is created |
| `--zoom-meeting-id` | string | Zoom meeting or webinar ID |
| `--only-for-contacts` | bool | Restrict event attendance to contacts only |
| `--only-for-members` | bool | Restrict event attendance to members only |
| `--new-small-logo-url` | string | URL of an image to upload as the small event image |
| `--clear-small-logo-file` | bool | Remove the current small event image |
| `--new-large-logo-url` | string | URL of an image to upload as the large event image |
| `--clear-large-logo-file` | bool | Remove the current large event image |
| `--web-address` | string | URL of an external website related to this event |
| `--facebook-page` | string | URL of a Facebook event or page for this event |
| `--tickets-page` | string | URL of an external ticketing page for this event |
| `--repeat-series-unique-id` | string | Unique identifier shared by all occurrences in a repeat series |
| `--repeats` | enum | Recurrence pattern for the event series |
| `--which-events-to-update` | enum | Which events in the recurring series to update (update only) |
| `--repeat-on-mondays` | bool | Include Mondays in the recurring schedule |
| `--repeat-on-tuesdays` | bool | Include Tuesdays in the recurring schedule |
| `--repeat-on-wednesdays` | bool | Include Wednesdays in the recurring schedule |
| `--repeat-on-thursdays` | bool | Include Thursdays in the recurring schedule |
| `--repeat-on-fridays` | bool | Include Fridays in the recurring schedule |
| `--repeat-on-saturdays` | bool | Include Saturdays in the recurring schedule |
| `--repeat-on-sundays` | bool | Include Sundays in the recurring schedule |
| `--start-date-local` | DateTime | Event start date and time in the location's local timezone |
| `--end-date-local` | DateTime | Event end date and time in the location's local timezone |
| `--publish-date-local` | DateTime | Publish date and time in the location's local timezone |
| `--after-event-notification-job-id` | string | Background job ID for the scheduled post-event notification email |
| `--send-after-event-notification` | bool | Send a follow-up notification email to attendees after the event ends |
| `--after-event-notification-text` | string | Custom message body for the post-event notification email |
| `--send-before-event-notification` | bool | Send a reminder notification email to attendees before the event starts |
| `--has-event-form` | bool | A form is linked to this event that attendees are asked to complete |
| `--send-event-form-by-email` | bool | Send the linked event form to attendees by email |
| `--form-page-id` | long | ID of the form page linked to this event |

#### CalendarEvent PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--host-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--send-event-form-by-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus calendarevents update <id> --host-full-name "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `EventCategories`, `AddedEventCategories`, `RemovedEventCategories`

#### CalendarEvent enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeats` | `1` Daily, `2` Weekly, `3` Monthly, `4` Yearly, `5` FirstOfMonth, `6` SecondOfMonth, `7` ThirdOfMonth, `8` LastOfMonth, `9` FourthOfMonth |
| `--which-events-to-update` | `1` UpdateThisEventOnly, `2` UpdateFutureEventsOnly, `3` UpdateAllEvents, `4` DeleteAllEvents, `5` DeleteEventsAfterThis, `6` UpdateEventProducts |

<!-- END:GENERATED entity=CalendarEvents -->
