# OpenAiChatMessages

<!-- BEGIN:GENERATED entity=OpenAiChatMessages -->

An OpenAiChatMessage is a single turn in an AI conversation — what the contact said, what the AI answered, a tool the AI ran, or a message an operator pushed into the thread. Messages belong to an AiChannelSession and share its ChatSession GUID, so filtering by conversation and ordering by creation time reproduces the transcript. This entity is read-only: turns are written by the AI pipeline as the conversation happens and are never edited afterwards.

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
| `--business-id` | long | ID of the location that owns this message, inherited from its conversation. |
| `--user-id` | long | ID of the platform user this message is attributed to. Set for messages exchanged inside an authenticated session; empty for anonymous web-chat and inbound email or WhatsApp contacts. |
| `--ai-channel-session-id` | long | ID of the conversation this message belongs to. Filter on it to read one conversation’s transcript in order. |
| `--ai-channel-session-external-identifier` | string | Display value for AiChannelSession.ExternalIdentifier. |
| `--ai-channel-session-coworker-id` | int | Display value for AiChannelSession.Coworker.Id. |
| `--from-ai-channel-session-coworker-id` | range | |
| `--to-ai-channel-session-coworker-id` | range | |
| `--ai-channel-session-coworker-coworker-type` | string | Display value for AiChannelSession.Coworker.CoworkerType. |
| `--ai-channel-session-coworker-full-name` | string | Display value for AiChannelSession.Coworker.FullName. |
| `--ai-channel-session-coworker-mobile-phone` | string | Display value for AiChannelSession.Coworker.MobilePhone. |
| `--ai-channel-session-coworker-land-line` | string | Display value for AiChannelSession.Coworker.LandLine. |
| `--ai-channel-session-coworker-billing-name` | string | Display value for AiChannelSession.Coworker.BillingName. |
| `--ai-channel-session-coworker-company-name` | string | Display value for AiChannelSession.Coworker.CompanyName. |
| `--ai-channel-session-coworker-team-names` | string | Display value for AiChannelSession.Coworker.TeamNames. |
| `--action` | enum | What this message was, beyond its role: Operator for ordinary AI or operator turns; OutboundCoworkerMessage and OutboundHelpDesk for AI replies delivered as a customer message or a help desk ticket; InboundCoworkerReply and InboundHelpDeskReply for the customer answering through those channels. Use it with the CoworkerMessage, HelpDeskMessage and HelpDeskComment links to show where a turn actually happened. |
| `--content` | string | Message body. User and assistant turns hold the text shown to people, in Markdown or HTML depending on channel; Tool turns hold a serialised tool result, and the assistant turn that requests tools holds a JSON array of tool calls rather than prose. |
| `--chat-session` | string | GUID of the conversation, matching AiChannelSession.ChatSession. Identical for every message in the same conversation. |
| `--responder-name` | string | Which internal responder produced the message, such as CompleteWithTools, KbOpenAiResponder or ProactiveExecutionEngine. Useful for tracing why the AI answered the way it did; empty for messages that came from a person. |
| `--chat-message-role` | string | Conversation role: User for the contact, Assistant for the AI, Tool for a tool result, System for prompt scaffolding, and operator-outbound for a message an operator sent into the thread. A transcript normally shows only User, Assistant and operator-outbound. |
| `--rating` | int | Feedback the recipient left on this answer through the members portal. Empty when nobody rated it. |
| `--from-rating` | range | |
| `--to-rating` | range | |
| `--channel` | string | Channel this turn travelled on, stored as text and matching its conversation: Chat, Email, WhatsApp, Voice, CoworkerMessage or HelpDesk. |
| `--coworker-message-id` | long | ID of the customer message this turn was delivered as or came from, when the AI replied over the CoworkerMessage channel. |
| `--help-desk-message-id` | long | ID of the help desk ticket this turn created or belongs to, set when the conversation was escalated to the help desk. |
| `--help-desk-comment-id` | long | ID of the help desk comment this turn came from, set when the customer or an operator replied on the escalated ticket. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### OpenAiChatMessage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` ascending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (ascending).

#### OpenAiChatMessage create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this message, inherited from its conversation. |
| `--user-id` | long | ID of the platform user this message is attributed to. Set for messages exchanged inside an authenticated session; empty for anonymous web-chat and inbound email or WhatsApp contacts. |
| `--ai-channel-session-id` | long | ID of the conversation this message belongs to. Filter on it to read one conversation’s transcript in order. |
| `--action` | enum, required | What this message was, beyond its role: Operator for ordinary AI or operator turns; OutboundCoworkerMessage and OutboundHelpDesk for AI replies delivered as a customer message or a help desk ticket; InboundCoworkerReply and InboundHelpDeskReply for the customer answering through those channels. Use it with the CoworkerMessage, HelpDeskMessage and HelpDeskComment links to show where a turn actually happened. |
| `--content` | string, required | Message body. User and assistant turns hold the text shown to people, in Markdown or HTML depending on channel; Tool turns hold a serialised tool result, and the assistant turn that requests tools holds a JSON array of tool calls rather than prose. |
| `--coworker-message-id` | long | ID of the customer message this turn was delivered as or came from, when the AI replied over the CoworkerMessage channel. |
| `--help-desk-message-id` | long | ID of the help desk ticket this turn created or belongs to, set when the conversation was escalated to the help desk. |
| `--help-desk-comment-id` | long | ID of the help desk comment this turn came from, set when the customer or an operator replied on the escalated ticket. |

#### OpenAiChatMessage update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this message, inherited from its conversation. |
| `--user-id` | long | ID of the platform user this message is attributed to. Set for messages exchanged inside an authenticated session; empty for anonymous web-chat and inbound email or WhatsApp contacts. |
| `--ai-channel-session-id` | long | ID of the conversation this message belongs to. Filter on it to read one conversation’s transcript in order. |
| `--action` | enum | What this message was, beyond its role: Operator for ordinary AI or operator turns; OutboundCoworkerMessage and OutboundHelpDesk for AI replies delivered as a customer message or a help desk ticket; InboundCoworkerReply and InboundHelpDeskReply for the customer answering through those channels. Use it with the CoworkerMessage, HelpDeskMessage and HelpDeskComment links to show where a turn actually happened. |
| `--content` | string | Message body. User and assistant turns hold the text shown to people, in Markdown or HTML depending on channel; Tool turns hold a serialised tool result, and the assistant turn that requests tools holds a JSON array of tool calls rather than prose. |
| `--coworker-message-id` | long | ID of the customer message this turn was delivered as or came from, when the AI replied over the CoworkerMessage channel. |
| `--help-desk-message-id` | long | ID of the help desk ticket this turn created or belongs to, set when the conversation was escalated to the help desk. |
| `--help-desk-comment-id` | long | ID of the help desk comment this turn came from, set when the customer or an operator replied on the escalated ticket. |

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
