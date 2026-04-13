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
| `nexudus helpdeskmessages create --business-id <value> --coworker-id <value> --subject <value> --message-text <value> --priority <value> --ai-processing-result <value> --agent` | Create helpdeskmessage |
| `nexudus helpdeskmessages update <id> --name "New Name" --agent` | Update helpdeskmessage |
| `nexudus helpdeskmessages delete <id> --yes --agent` | Delete helpdeskmessage (no prompt) |

#### HelpDeskMessage list filter options

`--business-id` (long), `--coworker-id` (long), `--help-desk-department-id` (long), `--subject`, `--message-text`, `--priority` (enum), `--ai-processing-result` (enum), `--closed` (bool), `--owner-id` (long), `--new-image-url`, `--clear-image-file` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### HelpDeskMessage create options

`--business-id` (long, required), `--coworker-id` (long, required), `--help-desk-department-id` (long), `--subject` (required), `--message-text` (required), `--priority` (enum, required), `--ai-processing-result` (enum, required), `--closed` (bool), `--owner-id` (long), `--new-image-url`, `--clear-image-file` (bool)

#### HelpDeskMessage update options

`--business-id` (long), `--coworker-id` (long), `--help-desk-department-id` (long), `--subject`, `--message-text`, `--priority` (enum), `--ai-processing-result` (enum), `--closed` (bool), `--owner-id` (long), `--new-image-url`, `--clear-image-file` (bool)

<!-- END:GENERATED entity=HelpDeskMessages -->
