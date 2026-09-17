# AdminAgentMessages

<!-- BEGIN:GENERATED entity=AdminAgentMessages -->

An individual message within an admin agent session conversation. Messages can be from the user, assistant, system, or tool calls/results. Each message tracks its role, content, and any tool interactions including tool name, arguments, and results. Token usage is tracked per message for cost monitoring.

AdminAgentMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus adminagentmessages list --agent` | List all adminagentmessages |
| `nexudus adminagentmessages list --id <id> --agent` | Filter by single ID |
| `nexudus adminagentmessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus adminagentmessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus adminagentmessages list --admin-agent-session-id <value> --role <value> --agent` | Filter adminagentmessages by properties |
| `nexudus adminagentmessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus adminagentmessages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus adminagentmessages get <id> --agent` | Get single adminagentmessage |
| `nexudus adminagentmessages create --admin-agent-session-id <value> --role <value> --tokens-used <value> --target <value> --agent` | Create adminagentmessage |
| `nexudus adminagentmessages update <id> --name "New Name" --agent` | Update adminagentmessage |
| `nexudus adminagentmessages delete <id> --yes --agent` | Delete adminagentmessage (no prompt) |

#### AdminAgentMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--admin-agent-session-id` | long | ID of the admin agent session linked to this message |
| `--role` | enum | Role of the message sender: User, Assistant, System, ToolCall, or ToolResult |
| `--content` | string | The text content of the message |
| `--tool-name` | string | Name of the tool that was called or produced a result |
| `--tool-arguments` | string | JSON-formatted arguments passed to the tool |
| `--tool-result` | string | JSON-formatted result returned by the tool |
| `--tokens-used` | int | Number of LLM tokens consumed by this message |
| `--from-tokens-used` | range | |
| `--to-tokens-used` | range | |
| `--author-id` | long | User who wrote the message (people only) |
| `--author-full-name` | string | Display value for Author.FullName. |
| `--author-email` | string | Display value for Author.Email. |
| `--target` | enum | Agent when the assistant was asked to answer, Chat when the message was for the people in the conversation |
| `--mentions` | string | JSON with the users and/or agent mentioned in the message |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AdminAgentMessage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### AdminAgentMessage create options

| Option | Type | Description |
| --- | --- | --- |
| `--admin-agent-session-id` | long, required | ID of the admin agent session linked to this message |
| `--role` | enum, required | Role of the message sender: User, Assistant, System, ToolCall, or ToolResult |
| `--content` | string | The text content of the message |
| `--tool-name` | string | Name of the tool that was called or produced a result |
| `--tool-arguments` | string | JSON-formatted arguments passed to the tool |
| `--tool-result` | string | JSON-formatted result returned by the tool |
| `--tokens-used` | int, required | Number of LLM tokens consumed by this message |
| `--author-id` | long | User who wrote the message (people only) |
| `--target` | enum, required | Agent when the assistant was asked to answer, Chat when the message was for the people in the conversation |
| `--mentions` | string | JSON with the users and/or agent mentioned in the message |

#### AdminAgentMessage update options

| Option | Type | Description |
| --- | --- | --- |
| `--admin-agent-session-id` | long | ID of the admin agent session linked to this message |
| `--role` | enum | Role of the message sender: User, Assistant, System, ToolCall, or ToolResult |
| `--content` | string | The text content of the message |
| `--tool-name` | string | Name of the tool that was called or produced a result |
| `--tool-arguments` | string | JSON-formatted arguments passed to the tool |
| `--tool-result` | string | JSON-formatted result returned by the tool |
| `--tokens-used` | int | Number of LLM tokens consumed by this message |
| `--author-id` | long | User who wrote the message (people only) |
| `--target` | enum | Agent when the assistant was asked to answer, Chat when the message was for the people in the conversation |
| `--mentions` | string | JSON with the users and/or agent mentioned in the message |

#### AdminAgentMessage PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--author-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--author-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus adminagentmessages update <id> --author-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### AdminAgentMessage enum values

| Option | Valid values |
| ------ | ------------ |
| `--role` | `1` User, `2` Assistant, `3` System, `4` ToolCall, `5` ToolResult |
| `--target` | `1` Agent, `2` Chat |

<!-- END:GENERATED entity=AdminAgentMessages -->
