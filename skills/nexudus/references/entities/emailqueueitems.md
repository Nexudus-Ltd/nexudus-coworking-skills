# EmailQueueItems

<!-- BEGIN:GENERATED entity=EmailQueueItems -->

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

`--business-id`, `--email-account-id`, `--from-user-id`, `--header`, `--body`, `--from-email`, `--to-emails`, `--c-c-emails`, `--c-c-o-emails`, `--sent`, `--sent-attempts`, `--from-sent-attempts` (range), `--to-sent-attempts` (range), `--delivered`, `--last-send-error`, `--send-date`, `--from-send-date` (range), `--to-send-date` (range), `--queued`, `--from-name`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

<!-- END:GENERATED entity=EmailQueueItems -->
