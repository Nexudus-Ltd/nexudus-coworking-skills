# AdminAgentSessions

<!-- BEGIN:GENERATED entity=AdminAgentSessions -->

An AdminAgentSession represents a conversation session between an admin user and the AI assistant within the Nexudus admin panel. Each session is linked to a specific Business and User (the operator), identified by a unique SessionId. Sessions track the conversation channel (Chat or API), status, and metadata such as page context.

AdminAgentSessions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus adminagentsessions list --agent` | List all adminagentsessions |
| `nexudus adminagentsessions list --id <id> --agent` | Filter by single ID |
| `nexudus adminagentsessions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus adminagentsessions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus adminagentsessions list --business-id <value> --user-id <value> --agent` | Filter adminagentsessions by properties |
| `nexudus adminagentsessions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus adminagentsessions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus adminagentsessions get <id> --agent` | Get single adminagentsession |
| `nexudus adminagentsessions create --business-id <value> --user-id <value> --channel <value> --started-on <value> --last-activity-on <value> --status <value> --mode <value> --agent` | Create adminagentsession |
| `nexudus adminagentsessions update <id> --name "New Name" --agent` | Update adminagentsession |
| `nexudus adminagentsessions delete <id> --yes --agent` | Delete adminagentsession (no prompt) |

#### AdminAgentSession list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | The business property |
| `--user-id` | long | The user property |
| `--user-full-name` | string | Display value for User.FullName. |
| `--user-email` | string | Display value for User.Email. |
| `--session-id` | string | The sessionid property |
| `--title` | string | The title property |
| `--channel` | enum | The channel property |
| `--started-on` | DateTime | The startedon property |
| `--from-started-on` | range | |
| `--to-started-on` | range | |
| `--last-activity-on` | DateTime | The lastactivityon property |
| `--from-last-activity-on` | range | |
| `--to-last-activity-on` | range | |
| `--status` | enum | The status property |
| `--metadata` | string | The metadata property |
| `--mode` | enum | Default routing of messages: Agent (assistant answers everything) or Chat (people talk, the assistant only answers when mentioned) |
| `--last-message-preview` | string | First characters of the most recent message (set automatically) |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AdminAgentSession sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### AdminAgentSession create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | The business property |
| `--user-id` | long, required | The user property |
| `--session-id` | string | The sessionid property |
| `--title` | string | The title property |
| `--channel` | enum, required | The channel property |
| `--started-on` | DateTime, required | The startedon property |
| `--last-activity-on` | DateTime, required | The lastactivityon property |
| `--status` | enum, required | The status property |
| `--metadata` | string | The metadata property |
| `--mode` | enum, required | Default routing of messages: Agent (assistant answers everything) or Chat (people talk, the assistant only answers when mentioned) |

#### AdminAgentSession update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | The business property |
| `--user-id` | long | The user property |
| `--session-id` | string | The sessionid property |
| `--title` | string | The title property |
| `--channel` | enum | The channel property |
| `--started-on` | DateTime | The startedon property |
| `--last-activity-on` | DateTime | The lastactivityon property |
| `--status` | enum | The status property |
| `--metadata` | string | The metadata property |
| `--mode` | enum | Default routing of messages: Agent (assistant answers everything) or Chat (people talk, the assistant only answers when mentioned) |

#### AdminAgentSession PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--user-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus adminagentsessions update <id> --user-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### AdminAgentSession enum values

| Option | Valid values |
| ------ | ------------ |
| `--channel` | `1` Chat, `2` Api |
| `--status` | `1` Active, `2` Completed, `3` Abandoned, `4` Deleted |
| `--mode` | `1` Agent, `2` Chat |

<!-- END:GENERATED entity=AdminAgentSessions -->
