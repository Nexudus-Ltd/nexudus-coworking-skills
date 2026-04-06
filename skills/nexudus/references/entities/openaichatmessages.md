# OpenAiChatMessages

<!-- BEGIN:GENERATED entity=OpenAiChatMessages -->

OpenAiChatMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus openaichatmessages list --agent` | List all openaichatmessages |
| `nexudus openaichatmessages list --id <id> --agent` | Filter by single ID |
| `nexudus openaichatmessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus openaichatmessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus openaichatmessages list --business-id <value> --user-id <value> --agent` | Filter openaichatmessages by properties |
| `nexudus openaichatmessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus openaichatmessages get <id> --agent` | Get single openaichatmessage |
| `nexudus openaichatmessages create --business-id <value> --action <value> --content <value> --agent` | Create openaichatmessage |
| `nexudus openaichatmessages update <id> --name "New Name" --agent` | Update openaichatmessage |
| `nexudus openaichatmessages delete <id> --yes --agent` | Delete openaichatmessage (no prompt) |

#### OpenAiChatMessage list filter options

`--business-id`, `--user-id`, `--action`, `--content`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### OpenAiChatMessage create options

`--business-id` (required), `--user-id`, `--action` (required), `--content` (required)

#### OpenAiChatMessage update options

`--business-id`, `--user-id`, `--action`, `--content`

<!-- END:GENERATED entity=OpenAiChatMessages -->
