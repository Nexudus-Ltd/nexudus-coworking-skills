# HelpDeskMessages

<!-- BEGIN:GENERATED entity=HelpDeskMessages -->

HelpDeskMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus helpdeskmessages list --agent` | List all helpdeskmessages |
| `nexudus helpdeskmessages list --id <id> --agent` | Filter by single ID |
| `nexudus helpdeskmessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus helpdeskmessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus helpdeskmessages list --business-id <value> --coworker-id <value> --agent` | Filter helpdeskmessages by properties |
| `nexudus helpdeskmessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus helpdeskmessages get <id> --agent` | Get single helpdeskmessage |
| `nexudus helpdeskmessages create --business-id <value> --coworker-id <value> --subject <value> --message-text <value> --agent` | Create helpdeskmessage |
| `nexudus helpdeskmessages update <id> --name "New Name" --agent` | Update helpdeskmessage |
| `nexudus helpdeskmessages delete <id> --yes --agent` | Delete helpdeskmessage (no prompt) |

#### HelpDeskMessage list filter options

`--business-id`, `--coworker-id`, `--help-desk-department-id`, `--subject`, `--message-text`, `--priority`, `--ai-processing-result`, `--closed`, `--owner-id`, `--new-image-url`, `--clear-image-file`

#### HelpDeskMessage create options

`--business-id` (required), `--coworker-id` (required), `--help-desk-department-id`, `--subject` (required), `--message-text` (required), `--priority`, `--ai-processing-result`, `--closed`, `--comments` (list, repeat flag), `--added-comments` (list, repeat flag), `--removed-comments` (list, repeat flag), `--owner-id`, `--new-image-url`, `--clear-image-file`

#### HelpDeskMessage update options

`--business-id`, `--coworker-id`, `--help-desk-department-id`, `--subject`, `--message-text`, `--priority`, `--ai-processing-result`, `--closed`, `--comments` (list, repeat flag), `--added-comments` (list, repeat flag), `--removed-comments` (list, repeat flag), `--owner-id`, `--new-image-url`, `--clear-image-file`

**List properties (only returned by `get`, not by `list`):** `Comments`, `AddedComments`, `RemovedComments`

<!-- END:GENERATED entity=HelpDeskMessages -->
