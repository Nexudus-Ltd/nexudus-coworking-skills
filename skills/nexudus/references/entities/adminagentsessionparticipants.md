# AdminAgentSessionParticipants

<!-- BEGIN:GENERATED entity=AdminAgentSessionParticipants -->

A person taking part in an admin agent conversation

AdminAgentSessionParticipants support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus adminagentsessionparticipants list --agent` | List all adminagentsessionparticipants |
| `nexudus adminagentsessionparticipants list --id <id> --agent` | Filter by single ID |
| `nexudus adminagentsessionparticipants list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus adminagentsessionparticipants list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus adminagentsessionparticipants list --admin-agent-session-id <value> --admin-agent-session-session-id <value> --agent` | Filter adminagentsessionparticipants by properties |
| `nexudus adminagentsessionparticipants list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus adminagentsessionparticipants list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus adminagentsessionparticipants get <id> --agent` | Get single adminagentsessionparticipant |
| `nexudus adminagentsessionparticipants create --admin-agent-session-id <value> --user-id <value> --role <value> --status <value> --joined-on <value> --agent` | Create adminagentsessionparticipant |
| `nexudus adminagentsessionparticipants update <id> --name "New Name" --agent` | Update adminagentsessionparticipant |
| `nexudus adminagentsessionparticipants delete <id> --yes --agent` | Delete adminagentsessionparticipant (no prompt) |

#### AdminAgentSessionParticipant list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--admin-agent-session-id` | long | ID of the admin agent session |
| `--admin-agent-session-session-id` | string | Display value for AdminAgentSession.SessionId. |
| `--admin-agent-session-title` | string | Display value for AdminAgentSession.Title. |
| `--user-id` | long | ID of the person taking part in the conversation |
| `--user-full-name` | string | Display value for User.FullName. |
| `--user-email` | string | Display value for User.Email. |
| `--invited-by-full-name` | string | Display value for InvitedBy.FullName. |
| `--role` | enum | Owner (started the conversation) or Member (invited) |
| `--status` | enum | Active, Left or Removed |
| `--joined-on` | DateTime | UTC time the person joined the conversation |
| `--from-joined-on` | range | |
| `--to-joined-on` | range | |
| `--last-read-on` | DateTime | UTC time of the newest message this person has seen; messages after it count as unread |
| `--from-last-read-on` | range | |
| `--to-last-read-on` | range | |
| `--last-digest-on` | DateTime | UTC time of the newest message included in the last unread-messages email sent to this person |
| `--from-last-digest-on` | range | |
| `--to-last-digest-on` | range | |
| `--digest-muted` | bool | True when this person asked not to receive unread-message emails for this conversation |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AdminAgentSessionParticipant sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `JoinedOn` ascending. If no `--order-by` is specified, the API returns results ordered by `JoinedOn` (ascending).

#### AdminAgentSessionParticipant create options

| Option | Type | Description |
| --- | --- | --- |
| `--admin-agent-session-id` | long, required | ID of the admin agent session |
| `--user-id` | long, required | ID of the person taking part in the conversation |
| `--role` | enum, required | Owner (started the conversation) or Member (invited) |
| `--status` | enum, required | Active, Left or Removed |
| `--joined-on` | DateTime, required | UTC time the person joined the conversation |
| `--digest-muted` | bool | True when this person asked not to receive unread-message emails for this conversation |

#### AdminAgentSessionParticipant update options

| Option | Type | Description |
| --- | --- | --- |
| `--admin-agent-session-id` | long | ID of the admin agent session |
| `--user-id` | long | ID of the person taking part in the conversation |
| `--role` | enum | Owner (started the conversation) or Member (invited) |
| `--status` | enum | Active, Left or Removed |
| `--joined-on` | DateTime | UTC time the person joined the conversation |
| `--digest-muted` | bool | True when this person asked not to receive unread-message emails for this conversation |

#### AdminAgentSessionParticipant PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--user-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--invited-by-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus adminagentsessionparticipants update <id> --user-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### AdminAgentSessionParticipant enum values

| Option | Valid values |
| ------ | ------------ |
| `--role` | `1` Owner, `2` Member |
| `--status` | `1` Active, `2` Left, `3` Removed |

<!-- END:GENERATED entity=AdminAgentSessionParticipants -->
