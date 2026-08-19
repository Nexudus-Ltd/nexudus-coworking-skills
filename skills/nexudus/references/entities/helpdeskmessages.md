# HelpDeskMessages

<!-- BEGIN:GENERATED entity=HelpDeskMessages -->

Help desk messages are location-owned support tickets opened by customers, which can be assigned, categorized, prioritized, and closed.

HelpDeskMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus helpdeskmessages list --agent` | List all helpdeskmessages |
| `nexudus helpdeskmessages list --id <id> --agent` | Filter by single ID |
| `nexudus helpdeskmessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus helpdeskmessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus helpdeskmessages list --business-id <value> --coworker-id <value> --agent` | Filter helpdeskmessages by properties |
| `nexudus helpdeskmessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus helpdeskmessages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus helpdeskmessages get <id> --agent` | Get single helpdeskmessage |
| `nexudus helpdeskmessages create --business-id <value> --coworker-id <value> --subject <value> --message-text <value> --priority <value> --agent` | Create helpdeskmessage |
| `nexudus helpdeskmessages update <id> --name "New Name" --agent` | Update helpdeskmessage |
| `nexudus helpdeskmessages delete <id> --yes --agent` | Delete helpdeskmessage (no prompt) |

#### HelpDeskMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this support ticket; it is supplied from the agent context. |
| `--coworker-id` | long | ID of the customer who opened this support ticket. |
| `--coworker-full-name` | string | Display name of the linked coworker full (read-only) |
| `--help-desk-department-id` | long | Optional ID of the support department that receives the ticket and can trigger its task-list workflow. |
| `--help-desk-department-name` | string | Display name of the linked help desk department (read-only) |
| `--subject` | string | Required ticket subject, up to 254 characters. |
| `--message-text` | string | Required initial message describing the customer's support request; multiline text is allowed. |
| `--priority` | enum | Ticket urgency: Low, Normal, High, or Critical; new tickets default to Normal when no priority is supplied. |
| `--ai-processing-result` | enum | Read-only result of the automatic AI reply attempt: NotProcessed, Responded, or NotResponded. |
| `--support-issue-category` | enum | Read-only AI-generated issue category: Printing, WiFi, Access, Billing, Noise, HVAC, Cleaning, Booking, or Other; it remains empty until classified. |
| `--closed` | bool | Whether the ticket is closed; closing records the closure time and reopening clears it. |
| `--closed-on` | DateTime | Read-only UTC timestamp set when the ticket is closed and cleared when it is reopened. |
| `--from-closed-on` | range | |
| `--to-closed-on` | range | |
| `--owner-id` | long | Optional ID of the staff user currently assigned to own the ticket. |
| `--owner-full-name` | string | Display name of the linked owner full (read-only) |
| `--image-file-name` | string | Current file name of the image (read-only; upload via the corresponding URL field) |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--first-response-time-in-minutes` | int | Read-only first-response duration for this ticket, measured in whole minutes. |
| `--from-first-response-time-in-minutes` | range | |
| `--to-first-response-time-in-minutes` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### HelpDeskMessage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Subject` ascending. If no `--order-by` is specified, the API returns results ordered by `Subject` (ascending).

#### HelpDeskMessage create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this support ticket; it is supplied from the agent context. |
| `--coworker-id` | long, required | ID of the customer who opened this support ticket. |
| `--help-desk-department-id` | long | Optional ID of the support department that receives the ticket and can trigger its task-list workflow. |
| `--subject` | string, required | Required ticket subject, up to 254 characters. |
| `--message-text` | string, required | Required initial message describing the customer's support request; multiline text is allowed. |
| `--priority` | enum, required | Ticket urgency: Low, Normal, High, or Critical; new tickets default to Normal when no priority is supplied. |
| `--closed` | bool | Whether the ticket is closed; closing records the closure time and reopening clears it. |
| `--owner-id` | long | Optional ID of the staff user currently assigned to own the ticket. |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |

#### HelpDeskMessage update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this support ticket; it is supplied from the agent context. |
| `--coworker-id` | long | ID of the customer who opened this support ticket. |
| `--help-desk-department-id` | long | Optional ID of the support department that receives the ticket and can trigger its task-list workflow. |
| `--subject` | string | Required ticket subject, up to 254 characters. |
| `--message-text` | string | Required initial message describing the customer's support request; multiline text is allowed. |
| `--priority` | enum | Ticket urgency: Low, Normal, High, or Critical; new tickets default to Normal when no priority is supplied. |
| `--closed` | bool | Whether the ticket is closed; closing records the closure time and reopening clears it. |
| `--owner-id` | long | Optional ID of the staff user currently assigned to own the ticket. |
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

<!-- END:GENERATED entity=HelpDeskMessages -->
