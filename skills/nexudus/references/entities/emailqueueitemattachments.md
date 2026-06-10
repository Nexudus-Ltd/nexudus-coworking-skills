# EmailQueueItemAttachments

<!-- BEGIN:GENERATED entity=EmailQueueItemAttachments -->

An **EmailQueueItemAttachment** represents a file attached to a queued email. Each record links an attachment file to its parent `EmailQueueItem`.

EmailQueueItemAttachments support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus emailqueueitemattachments list --agent` | List all emailqueueitemattachments |
| `nexudus emailqueueitemattachments list --id <id> --agent` | Filter by single ID |
| `nexudus emailqueueitemattachments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus emailqueueitemattachments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus emailqueueitemattachments list --email-queue-item-id <value> --name <value> --agent` | Filter emailqueueitemattachments by properties |
| `nexudus emailqueueitemattachments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus emailqueueitemattachments list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus emailqueueitemattachments get <id> --agent` | Get single emailqueueitemattachment |
| `nexudus emailqueueitemattachments update <id> --name "New Name" --agent` | Update emailqueueitemattachment |

#### EmailQueueItemAttachment list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--email-queue-item-id` | long | ID of the email queue item linked to this record |
| `--name` | string | The name value for this email queue item attachment |
| `--extension` | string | The extension value for this email queue item attachment |
| `--new-binary-url` | string | URL of a new file to upload as the binary |
| `--clear-binary-file` | bool | Set to true to remove the current binary file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EmailQueueItemAttachment sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### EmailQueueItemAttachment update options

| Option | Type | Description |
| --- | --- | --- |
| `--email-queue-item-id` | long | ID of the email queue item linked to this record |
| `--name` | string | The name value for this email queue item attachment |
| `--extension` | string | The extension value for this email queue item attachment |
| `--new-binary-url` | string | URL of a new file to upload as the binary |
| `--clear-binary-file` | bool | Set to true to remove the current binary file |

<!-- END:GENERATED entity=EmailQueueItemAttachments -->
