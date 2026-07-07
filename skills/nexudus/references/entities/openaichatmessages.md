# OpenAiChatMessages

<!-- BEGIN:GENERATED entity=OpenAiChatMessages -->

An **OpenAiChatMessage** records a message in an AI-powered chat conversation. Each message tracks the content, the associated customer or operator, and the action type.

OpenAiChatMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus openaichatmessages list --agent` | List all openaichatmessages |
| `nexudus openaichatmessages list --id <id> --agent` | Filter by single ID |
| `nexudus openaichatmessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus openaichatmessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus openaichatmessages list --business-id <value> --user-id <value> --agent` | Filter openaichatmessages by properties |
| `nexudus openaichatmessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus openaichatmessages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus openaichatmessages get <id> --agent` | Get single openaichatmessage |
| `nexudus openaichatmessages create --business-id <value> --action <value> --content <value> --agent` | Create openaichatmessage |
| `nexudus openaichatmessages update <id> --name "New Name" --agent` | Update openaichatmessage |
| `nexudus openaichatmessages delete <id> --yes --agent` | Delete openaichatmessage (no prompt) |

#### OpenAiChatMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--user-id` | long | ID of the user linked to this record |
| `--ai-channel-session-id` | long | ID of the AI channel session linked to this message. Sessions group all messages in a conversation and link it to a specific user and AI channel (e.g. email, chat, WhatsApp) |
| `--action` | enum | The action value for this open ai chat message |
| `--content` | string | The content value for this open ai chat message |
| `--coworker-message-id` | long | ID of the customer message linked to this AI chat message, if the message was part of a customer communication thread |
| `--help-desk-message-id` | long | ID of the help desk ticket linked to this AI chat message, if the message was part of a support ticket conversation |
| `--help-desk-comment-id` | long | ID of the help desk comment linked to this AI chat message, if the message was a reply on a support ticket |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### OpenAiChatMessage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### OpenAiChatMessage create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--user-id` | long | ID of the user linked to this record |
| `--ai-channel-session-id` | long | ID of the AI channel session linked to this message. Sessions group all messages in a conversation and link it to a specific user and AI channel (e.g. email, chat, WhatsApp) |
| `--action` | enum, required | The action value for this open ai chat message |
| `--content` | string, required | The content value for this open ai chat message |
| `--coworker-message-id` | long | ID of the customer message linked to this AI chat message, if the message was part of a customer communication thread |
| `--help-desk-message-id` | long | ID of the help desk ticket linked to this AI chat message, if the message was part of a support ticket conversation |
| `--help-desk-comment-id` | long | ID of the help desk comment linked to this AI chat message, if the message was a reply on a support ticket |

#### OpenAiChatMessage update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--user-id` | long | ID of the user linked to this record |
| `--ai-channel-session-id` | long | ID of the AI channel session linked to this message. Sessions group all messages in a conversation and link it to a specific user and AI channel (e.g. email, chat, WhatsApp) |
| `--action` | enum | The action value for this open ai chat message |
| `--content` | string | The content value for this open ai chat message |
| `--coworker-message-id` | long | ID of the customer message linked to this AI chat message, if the message was part of a customer communication thread |
| `--help-desk-message-id` | long | ID of the help desk ticket linked to this AI chat message, if the message was part of a support ticket conversation |
| `--help-desk-comment-id` | long | ID of the help desk comment linked to this AI chat message, if the message was a reply on a support ticket |

#### OpenAiChatMessage PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--ai-channel-session-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--ai-channel-session-coworker-mobile-phone` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--ai-channel-session-coworker-land-line` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--ai-channel-session-coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--ai-channel-session-coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus openaichatmessages update <id> --ai-channel-session-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### OpenAiChatMessage enum values

| Option | Valid values |
| ------ | ------------ |
| `--action` | `1` Operator |

<!-- END:GENERATED entity=OpenAiChatMessages -->
