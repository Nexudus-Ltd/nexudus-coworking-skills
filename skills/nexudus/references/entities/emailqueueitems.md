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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--email-account-id` | long |  |
| `--from-user-id` | long |  |
| `--header` | string |  |
| `--body` | string |  |
| `--from-email` | string |  |
| `--to-emails` | string |  |
| `--c-c-emails` | string |  |
| `--c-c-o-emails` | string |  |
| `--sent` | bool |  |
| `--sent-attempts` | int |  |
| `--from-sent-attempts` | range | |
| `--to-sent-attempts` | range | |
| `--delivered` | bool |  |
| `--last-send-error` | string |  |
| `--send-date` | DateTime |  |
| `--from-send-date` | range | |
| `--to-send-date` | range | |
| `--queued` | bool |  |
| `--from-name` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

<!-- END:GENERATED entity=EmailQueueItems -->
