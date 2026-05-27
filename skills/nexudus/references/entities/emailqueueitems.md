# EmailQueueItems

<!-- BEGIN:GENERATED entity=EmailQueueItems -->

An **EmailQueueItem** represents a single email queued for delivery. Each record tracks the sender, recipient, subject, body, and delivery status of an outgoing email message.

EmailQueueItems support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus emailqueueitems list --agent` | List all emailqueueitems |
| `nexudus emailqueueitems list --id <id> --agent` | Filter by single ID |
| `nexudus emailqueueitems list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus emailqueueitems list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus emailqueueitems list --business-id <value> --email-account-id <value> --agent` | Filter emailqueueitems by properties |
| `nexudus emailqueueitems list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus emailqueueitems get <id> --agent` | Get single emailqueueitem |

#### EmailQueueItem list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--email-account-id` | long | ID of the email account linked to this record |
| `--from-user-id` | long | ID of the from user linked to this record |
| `--header` | string | The header value for this email queue item |
| `--body` | string | The body value for this email queue item |
| `--from-email` | string | The from email value for this email queue item |
| `--to-emails` | string | The to emails value for this email queue item |
| `--c-c-emails` | string | The cc emails value for this email queue item |
| `--c-c-o-emails` | string | The cco emails value for this email queue item |
| `--sent` | bool | Whether sent is enabled |
| `--sent-attempts` | int | The sent attempts value for this email queue item |
| `--from-sent-attempts` | range | |
| `--to-sent-attempts` | range | |
| `--delivered` | bool | Whether delivered is enabled |
| `--last-send-error` | string | The last send error value for this email queue item |
| `--send-date` | DateTime | Date/time value for send date |
| `--from-send-date` | range | |
| `--to-send-date` | range | |
| `--queued` | bool | Whether queued is enabled |
| `--from-name` | string | The from name value for this email queue item |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EmailQueueItem PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--from-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:


<!-- END:GENERATED entity=EmailQueueItems -->
