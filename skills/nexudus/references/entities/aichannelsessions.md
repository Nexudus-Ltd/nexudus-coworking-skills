# AiChannelSessions

<!-- BEGIN:GENERATED entity=AiChannelSessions -->

An **AiChannelSession** represents a conversation session between a customer (or external contact) and the AI agent across any channel (email, chat, WhatsApp, voice, etc.).

Each session groups all messages in a single conversation and links to a specific `Coworker` (if the contact is a member) or an `ExternalIdentifier` (email address, phone number, etc.) for non-members. Sessions are the primary tracking mechanism for AI-powered interactions and serve as the source for proactive outbound messaging when `ExternalIdentifier` is used to follow up with dormant leads.

AiChannelSessions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus aichannelsessions list --agent` | List all aichannelsessions |
| `nexudus aichannelsessions list --id <id> --agent` | Filter by single ID |
| `nexudus aichannelsessions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus aichannelsessions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus aichannelsessions list --business-id <value> --coworker-id <value> --agent` | Filter aichannelsessions by properties |
| `nexudus aichannelsessions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus aichannelsessions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus aichannelsessions get <id> --agent` | Get single aichannelsession |
| `nexudus aichannelsessions create --business-id <value> --channel <value> --external-identifier <value> --escalation-status <value> --agent` | Create aichannelsession |
| `nexudus aichannelsessions update <id> --name "New Name" --agent` | Update aichannelsession |
| `nexudus aichannelsessions delete <id> --yes --agent` | Delete aichannelsession (no prompt) |

#### AiChannelSession list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this session. Null for sessions with external contacts who are not members. |
| `--coworker-coworker-type` | string | Whether the linked coworker is an individual or a company. |
| `--coworker-full-name` | string | Full name of the coworker associated with this session. |
| `--coworker-mobile-phone` | string | Mobile phone number of the coworker associated with this session. |
| `--coworker-land-line` | string | Landline phone number of the coworker associated with this session. |
| `--coworker-billing-name` | string | Billing name of the coworker associated with this session. |
| `--coworker-company-name` | string | Company name of the coworker associated with this session. |
| `--coworker-team-names` | string | Comma-separated list of team names the coworker belongs to. |
| `--channel` | string | Communication channel for this session (e.g. Email, Chat, WhatsApp, Voice). |
| `--external-identifier` | string | External contact identifier — email address for email sessions, phone number for WhatsApp or voice sessions. Used to identify non-member contacts and for proactive follow-up of dormant leads. |
| `--chat-session` | string | Internal chat session identifier used by the AI platform for context tracking. |
| `--external-thread-id` | string | External thread identifier from the channel provider (e.g. WhatsApp conversation ID, email thread ID) used for message threading. |
| `--last-activity-utc` | DateTime | Timestamp of the last activity in this session (last message sent or received). Used by proactive criteria to detect dormant sessions. |
| `--from-last-activity-utc` | range | |
| `--to-last-activity-utc` | range | |
| `--subject` | string | Subject line for the conversation, typically set from the first email or inferred from conversation context. |
| `--escalation-status` | enum | Current escalation state of this session — None, Pending (awaiting human review), Active (human is handling), or Resolved. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AiChannelSession sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### AiChannelSession create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this session. Null for sessions with external contacts who are not members. |
| `--channel` | string, required | Communication channel for this session (e.g. Email, Chat, WhatsApp, Voice). |
| `--external-identifier` | string, required | External contact identifier — email address for email sessions, phone number for WhatsApp or voice sessions. Used to identify non-member contacts and for proactive follow-up of dormant leads. |
| `--chat-session` | string | Internal chat session identifier used by the AI platform for context tracking. |
| `--external-thread-id` | string | External thread identifier from the channel provider (e.g. WhatsApp conversation ID, email thread ID) used for message threading. |
| `--last-activity-utc` | DateTime | Timestamp of the last activity in this session (last message sent or received). Used by proactive criteria to detect dormant sessions. |
| `--subject` | string | Subject line for the conversation, typically set from the first email or inferred from conversation context. |
| `--escalation-status` | enum, required | Current escalation state of this session — None, Pending (awaiting human review), Active (human is handling), or Resolved. |

#### AiChannelSession update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this session. Null for sessions with external contacts who are not members. |
| `--channel` | string | Communication channel for this session (e.g. Email, Chat, WhatsApp, Voice). |
| `--external-identifier` | string | External contact identifier — email address for email sessions, phone number for WhatsApp or voice sessions. Used to identify non-member contacts and for proactive follow-up of dormant leads. |
| `--chat-session` | string | Internal chat session identifier used by the AI platform for context tracking. |
| `--external-thread-id` | string | External thread identifier from the channel provider (e.g. WhatsApp conversation ID, email thread ID) used for message threading. |
| `--last-activity-utc` | DateTime | Timestamp of the last activity in this session (last message sent or received). Used by proactive criteria to detect dormant sessions. |
| `--subject` | string | Subject line for the conversation, typically set from the first email or inferred from conversation context. |
| `--escalation-status` | enum | Current escalation state of this session — None, Pending (awaiting human review), Active (human is handling), or Resolved. |

#### AiChannelSession PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-mobile-phone` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--coworker-land-line` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus aichannelsessions update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### AiChannelSession enum values

| Option | Valid values |
| ------ | ------------ |
| `--escalation-status` | `1` Pending, `2` Active, `3` Resolved |

<!-- END:GENERATED entity=AiChannelSessions -->
