# EmailQueueItems

<!-- BEGIN:GENERATED entity=EmailQueueItems -->

An EmailQueueItem is a read-only outgoing email delivery record for a location, tracking its recipients, content, sender, attempts, and delivery result. Every email the system sends from a location is one of these, so together they are the history of sent emails, shown on the dashboard's Email Queue screen.

EmailQueueItems support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus emailqueueitems list --agent` | List all emailqueueitems |
| `nexudus emailqueueitems list --id <id> --agent` | Filter by single ID |
| `nexudus emailqueueitems list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus emailqueueitems list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus emailqueueitems list --business-id <value> --email-account-id <value> --agent` | Filter emailqueueitems by properties |
| `nexudus emailqueueitems list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus emailqueueitems list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus emailqueueitems get <id> --agent` | Get single emailqueueitem |

#### EmailQueueItem list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this queued email. |
| `--email-account-id` | long | Optional ID of the email account whose outgoing server and sender details are used instead of the location's default email settings. |
| `--from-user-id` | long | Optional ID of the staff user recorded as the sender of this email. |
| `--header` | string | Email subject line, limited to 1,024 characters. |
| `--body` | string | Localized HTML content sent as the email body. |
| `--from-email` | string | Optional reply-to email address; when empty, the selected email account or location email settings provide it. |
| `--to-emails` | string | Required recipient email addresses, separated with semicolons. |
| `--c-c-emails` | string | Optional carbon-copy recipient email addresses, separated with semicolons. |
| `--c-c-o-emails` | string | Optional blind-carbon-copy recipient email addresses, separated with semicolons. |
| `--sent` | bool | Whether the system has completed a send attempt; this can be true even when Delivered is false. |
| `--sent-attempts` | int | Number of send attempts made by the email delivery process; retrying through the queue command resets it to zero. |
| `--from-sent-attempts` | range | |
| `--to-sent-attempts` | range | |
| `--delivered` | bool | Whether the most recent send attempt was accepted successfully by the email delivery process. |
| `--last-send-error` | string | Most recently recorded delivery error, including provider-reported bounces; empty when no error is currently recorded. |
| `--send-date` | DateTime | UTC date and time when the system last completed a send attempt; empty until an attempt is made. |
| `--from-send-date` | range | |
| `--to-send-date` | range | |
| `--from-name` | string | Optional sender display name that overrides the selected email account or location email settings. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EmailQueueItem sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### EmailQueueItem PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--from-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:


<!-- END:GENERATED entity=EmailQueueItems -->
