# HelpDeskMessages

<!-- BEGIN:GENERATED entity=HelpDeskMessages -->

A **HelpDeskMessage** represents a support ticket submitted by a customer or created by staff. Each message has a priority level, can be assigned to a department, and tracks its resolution status.

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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--help-desk-department-id` | long | ID of the help desk department linked to this record |
| `--subject` | string | The subject value for this help desk message |
| `--message-text` | string | The message text value for this help desk message |
| `--priority` | enum | The priority value for this help desk message |
| `--ai-processing-result` | enum | The ai processing result value for this help desk message |
| `--closed` | bool | Whether closed is enabled |
| `--owner-id` | long | ID of the owner linked to this record |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### HelpDeskMessage create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--help-desk-department-id` | long | ID of the help desk department linked to this record |
| `--subject` | string, required | The subject value for this help desk message |
| `--message-text` | string, required | The message text value for this help desk message |
| `--priority` | enum, required | The priority value for this help desk message |
| `--ai-processing-result` | enum, required | The ai processing result value for this help desk message |
| `--closed` | bool | Whether closed is enabled |
| `--owner-id` | long | ID of the owner linked to this record |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |

#### HelpDeskMessage update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--help-desk-department-id` | long | ID of the help desk department linked to this record |
| `--subject` | string | The subject value for this help desk message |
| `--message-text` | string | The message text value for this help desk message |
| `--priority` | enum | The priority value for this help desk message |
| `--ai-processing-result` | enum | The ai processing result value for this help desk message |
| `--closed` | bool | Whether closed is enabled |
| `--owner-id` | long | ID of the owner linked to this record |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |

#### HelpDeskMessage PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--owner-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus helpdeskmessages update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### HelpDeskMessage enum values

| Option | Valid values |
| ------ | ------------ |
| `--priority` | `1` Low, `2` Normal, `3` High, `4` Critical |
| `--ai-processing-result` | `1` NotProcessed, `2` Responded, `3` NotResponded |

<!-- END:GENERATED entity=HelpDeskMessages -->
