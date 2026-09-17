# AiChannelSessions

<!-- BEGIN:GENERATED entity=AiChannelSessions -->

An AiChannelSession is one conversation between a contact and the AI, on whichever channel it happened — the web chat widget, email, WhatsApp or a voice call. It links to a Coworker when the contact is a member, and otherwise identifies them by ExternalIdentifier. The transcript lives in OpenAiChatMessage records sharing this record’s ChatSession GUID. Custom fields named Nexudus.Ai.VisitorId, Nexudus.Ai.CoworkerId, Nexudus.Ai.CoworkerContractId, Nexudus.Ai.CoworkerProductId and Nexudus.Ai.BookingId record what the conversation produced, so they are how you tell which conversations converted into a tour, a signup, a contract, a day pass or a booking. This entity is read-only: conversations are written by the inbound message pipeline and the proactive outreach engine, never by hand.

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
| `--business-id` | long | ID of the location that owns this conversation. Set from the location the inbound message arrived at, or from the location whose agent started the outreach. |
| `--coworker-id` | long | ID of the customer this conversation is with. Empty when the contact is not a member yet, in which case ExternalIdentifier holds their email address or phone number. |
| `--coworker-coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-mobile-phone` | string | Display value for Coworker.MobilePhone. |
| `--coworker-land-line` | string | Display value for Coworker.LandLine. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-team-names` | string | Display value for Coworker.TeamNames. |
| `--channel` | string | Channel the conversation runs on, stored as text: Chat for the web widget, Email, WhatsApp or Voice for inbound contact; proactive outreach also writes CoworkerMessage and HelpDesk. Determines how ExternalIdentifier is interpreted. |
| `--external-identifier` | string | How the outside contact is addressed on this channel: an email address for Email, a phone number for WhatsApp and Voice. It is how a conversation is matched to an incoming reply, and how dormant non-member leads are followed up. |
| `--chat-session` | string | GUID that groups the conversation’s messages. Every OpenAiChatMessage in this conversation carries the same value, so it is the key to reading the transcript. |
| `--external-thread-id` | string | Threading key from the channel provider — the email In-Reply-To/References header, or the WhatsApp conversation ID — used to attach later replies to this same conversation. |
| `--last-activity-utc` | DateTime | UTC time of the most recent message in either direction. Drives conversation ordering, session expiry, and the dormant-lead follow-up agent. |
| `--from-last-activity-utc` | range | |
| `--to-last-activity-utc` | range | |
| `--subject` | string | Conversation subject, taken from the first email or inferred from the opening messages. On the Email channel a different subject from the same address starts a new conversation rather than continuing this one. |
| `--escalation-status` | enum | How far this conversation has been handed over to a person: None while the AI is handling it alone; Pending once the AI escalates and a help desk ticket is waiting; Active once someone comments on that ticket or an operator takes the thread; Resolved when the ticket is closed. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AiChannelSession sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `LastActivityUtc` descending. If no `--order-by` is specified, the API returns results ordered by `LastActivityUtc` (descending).

#### AiChannelSession create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this conversation. Set from the location the inbound message arrived at, or from the location whose agent started the outreach. |
| `--coworker-id` | long | ID of the customer this conversation is with. Empty when the contact is not a member yet, in which case ExternalIdentifier holds their email address or phone number. |
| `--channel` | string, required | Channel the conversation runs on, stored as text: Chat for the web widget, Email, WhatsApp or Voice for inbound contact; proactive outreach also writes CoworkerMessage and HelpDesk. Determines how ExternalIdentifier is interpreted. |
| `--external-identifier` | string, required | How the outside contact is addressed on this channel: an email address for Email, a phone number for WhatsApp and Voice. It is how a conversation is matched to an incoming reply, and how dormant non-member leads are followed up. |
| `--chat-session` | string | GUID that groups the conversation’s messages. Every OpenAiChatMessage in this conversation carries the same value, so it is the key to reading the transcript. |
| `--external-thread-id` | string | Threading key from the channel provider — the email In-Reply-To/References header, or the WhatsApp conversation ID — used to attach later replies to this same conversation. |
| `--last-activity-utc` | DateTime | UTC time of the most recent message in either direction. Drives conversation ordering, session expiry, and the dormant-lead follow-up agent. |
| `--subject` | string | Conversation subject, taken from the first email or inferred from the opening messages. On the Email channel a different subject from the same address starts a new conversation rather than continuing this one. |
| `--escalation-status` | enum, required | How far this conversation has been handed over to a person: None while the AI is handling it alone; Pending once the AI escalates and a help desk ticket is waiting; Active once someone comments on that ticket or an operator takes the thread; Resolved when the ticket is closed. |

#### AiChannelSession update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this conversation. Set from the location the inbound message arrived at, or from the location whose agent started the outreach. |
| `--coworker-id` | long | ID of the customer this conversation is with. Empty when the contact is not a member yet, in which case ExternalIdentifier holds their email address or phone number. |
| `--channel` | string | Channel the conversation runs on, stored as text: Chat for the web widget, Email, WhatsApp or Voice for inbound contact; proactive outreach also writes CoworkerMessage and HelpDesk. Determines how ExternalIdentifier is interpreted. |
| `--external-identifier` | string | How the outside contact is addressed on this channel: an email address for Email, a phone number for WhatsApp and Voice. It is how a conversation is matched to an incoming reply, and how dormant non-member leads are followed up. |
| `--chat-session` | string | GUID that groups the conversation’s messages. Every OpenAiChatMessage in this conversation carries the same value, so it is the key to reading the transcript. |
| `--external-thread-id` | string | Threading key from the channel provider — the email In-Reply-To/References header, or the WhatsApp conversation ID — used to attach later replies to this same conversation. |
| `--last-activity-utc` | DateTime | UTC time of the most recent message in either direction. Drives conversation ordering, session expiry, and the dormant-lead follow-up agent. |
| `--subject` | string | Conversation subject, taken from the first email or inferred from the opening messages. On the Email channel a different subject from the same address starts a new conversation rather than continuing this one. |
| `--escalation-status` | enum | How far this conversation has been handed over to a person: None while the AI is handling it alone; Pending once the AI escalates and a help desk ticket is waiting; Active once someone comments on that ticket or an operator takes the thread; Resolved when the ticket is closed. |

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
