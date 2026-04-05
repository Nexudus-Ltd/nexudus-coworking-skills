# EmailQueueItemAttachments

<!-- BEGIN:GENERATED entity=EmailQueueItemAttachments -->

EmailQueueItemAttachments support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus emailqueueitemattachments list --agent` | List all emailqueueitemattachments |
| `nexudus emailqueueitemattachments list --id <id> --agent` | Filter by single ID |
| `nexudus emailqueueitemattachments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus emailqueueitemattachments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus emailqueueitemattachments list --email-queue-item-id <value> --name <value> --agent` | Filter emailqueueitemattachments by properties |
| `nexudus emailqueueitemattachments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus emailqueueitemattachments get <id> --agent` | Get single emailqueueitemattachment |
| `nexudus emailqueueitemattachments update <id> --name "New Name" --agent` | Update emailqueueitemattachment |

#### EmailQueueItemAttachment list filter options

`--email-queue-item-id`, `--name`, `--extension`, `--new-binary-url`, `--clear-binary-file`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### EmailQueueItemAttachment update options

`--email-queue-item-id`, `--name`, `--extension`, `--new-binary-url`, `--clear-binary-file`

<!-- END:GENERATED entity=EmailQueueItemAttachments -->
