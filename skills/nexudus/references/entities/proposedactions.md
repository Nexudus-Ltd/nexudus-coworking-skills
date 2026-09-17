# ProposedActions

<!-- BEGIN:GENERATED entity=ProposedActions -->

A ProposedAction is an AI-generated recommendation waiting in the operator AI Inbox, produced when one of the proactive agents spots an opportunity such as an overdue invoice, an expiring contract, a run of support tickets, a spike in one issue category or a gap in the FAQ. Each one carries a drafted message or an internal alert, a confidence score and a review deadline. Records are created by the proactive agents, never by hand, and cannot be deleted. Fields such as the drafted subject and body, the delivery channel and the review notes may be edited before the action goes out. Its lifecycle, however, is driven by the review operations: use the approve and reject commands (PROPOSEDACTION_APPROVE, PROPOSEDACTION_REJECT), which also deliver the message, rather than writing Status directly — setting Status by hand marks an action as handled without ever sending it. Which agents run and how they behave is configured through ProactiveActionConfig.

ProposedActions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proposedactions list --agent` | List all proposedactions |
| `nexudus proposedactions list --id <id> --agent` | Filter by single ID |
| `nexudus proposedactions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proposedactions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proposedactions list --business-id <value> --coworker-id <value> --agent` | Filter proposedactions by properties |
| `nexudus proposedactions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposedactions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus proposedactions get <id> --agent` | Get single proposedaction |
| `nexudus proposedactions create --business-id <value> --criteria-type <value> --action-type <value> --channel <value> --confidence <value> --priority <value> --status <value> --deferral-count <value> --agent` | Create proposedaction |
| `nexudus proposedactions update <id> --name "New Name" --agent` | Update proposedaction |
| `nexudus proposedactions delete <id> --yes --agent` | Delete proposedaction (no prompt) |

#### ProposedAction list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this proposed action. Set from the location whose agents produced it. |
| `--coworker-id` | long | ID of the customer this action targets. Empty for internal alerts and for leads that have no customer record yet. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-email` | string | Display value for Coworker.Email. |
| `--coworker-coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--ai-channel-session-id` | long | ID of the AI conversation that triggered this action. Only set for criteria that evaluate conversations, such as unanswered-question and dormant-lead detection. |
| `--criteria-type` | string | Identifier of the agent that produced this action, matching a criteria evaluator name such as DueInvoiceCriteria, ContractExpiryCriteria, SupportPatternCriteria, SupportIssueCategoryCriteria or MissingFaqCriteria. Behaviour for each is configured through ProactiveActionConfig. |
| `--criteria-payload` | string | Read-only JSON snapshot of the evidence the criteria evaluator collected (for example invoice amounts and due dates, contract dates, support ticket summaries, or a drafted FAQ article). Shape varies per criteria type; returned by the detail operation only. |
| `--action-type` | enum | What the action does once approved: DraftMessage sends a composed message to the customer, VoiceOutreach places an AI call, InternalNote raises an operator-only alert with no customer contact, TaskReminder records a follow-up. InternalNote actions have no customer target and no delivery channel. |
| `--channel` | enum | How an approved action reaches the customer: Email for an AI-tracked email conversation, Voice for an outbound AI call, CoworkerMessage for a message sent from a connected email account, HelpDesk to raise a ticket, or WhatsApp. Operators can change the channel at approval time. Ignored for InternalNote actions. |
| `--draft-subject` | string | AI-composed subject line for the proposed message. Operators may edit it before approving; for internal alerts it doubles as the alert headline. |
| `--draft-body` | string | AI-composed message body, call script, or — for internal alerts — the alert text itself. Operators may edit it before approving. |
| `--confidence` | decimal | AI confidence in this recommendation, on a 0.0–1.0 scale (not a percentage). When the matching ProactiveActionConfig enables auto-execution, an action at or above its AutoExecuteMinConfidence skips the review inbox. |
| `--from-confidence` | range | |
| `--to-confidence` | range | |
| `--priority` | enum | Urgency assigned by the agent that raised the action: Low, Medium, High or Critical. Drives inbox ordering and the urgency indicator; it does not change delivery behaviour. |
| `--status` | enum | Where the action sits in its lifecycle: Pending awaits review; Snoozed is hidden until its wake time; Approved has been accepted for delivery; AutoExecuted was sent without review because confidence cleared the configured threshold; Deferred is approved but waiting for the recipient's next calling window; AwaitingReply has sent a WhatsApp opt-in template and is waiting on the customer; Rejected was dismissed; Expired passed its review deadline unattended. Change it through the approve, reject and snooze operations rather than by writing this field. |
| `--reviewed-by-id` | long | ID of the operator who last reviewed this action. Empty while it is still awaiting review or when the system expired it unattended. |
| `--reviewed-by-full-name` | string | Display value for ReviewedBy.FullName. |
| `--reviewed-by-email` | string | Display value for ReviewedBy.Email. |
| `--reviewed-on` | DateTime | UTC time an operator last approved, rejected or snoozed this action. |
| `--from-reviewed-on` | range | |
| `--to-reviewed-on` | range | |
| `--review-notes` | string | Notes recorded when an operator approves, rejects or snoozes the action. The system also appends here when it expires an action, for example because no calling window was available. |
| `--executed-on` | DateTime | UTC time the approved action was actually delivered or the outbound call placed. Empty while the action is still queued or deferred. |
| `--from-executed-on` | range | |
| `--to-executed-on` | range | |
| `--outcome-session-id` | long | ID of the AI conversation created when this action was delivered. Use it to follow the reply thread, escalated tickets and messages that came out of the outreach. |
| `--expires-on` | DateTime | UTC review deadline, defaulting to three days after the action is created. A Pending action past this point is moved to Expired; for a Snoozed action this instead holds the wake time set by the snooze duration. |
| `--from-expires-on` | range | |
| `--to-expires-on` | range | |
| `--deduplication-key` | string | Read-only key that prevents duplicate proposals for the same trigger, shaped as "criteria-type:{identifier}:{tier}" (for example "invoice:123:reminder:1"). A new proposal is suppressed while a non-expired action with the same key exists inside the criteria's cooldown window. |
| `--scheduled-execution-time` | DateTime | UTC time a Deferred action becomes due, set automatically to the recipient's next calling window when approval lands outside permitted outbound hours. |
| `--from-scheduled-execution-time` | range | |
| `--to-scheduled-execution-time` | range | |
| `--deferral-reason` | string | System-written explanation of why delivery was postponed, recorded when an approved action falls outside the recipient's permitted calling hours. |
| `--deferral-count` | int | Number of times delivery has been postponed for calling hours. Counts up from zero and helps spot actions that keep missing their window. |
| `--from-deferral-count` | range | |
| `--to-deferral-count` | range | |
| `--email-account-id` | long | ID of the connected email account used as the sender when an approved action goes out over the CoworkerMessage channel. Empty means the location's default outgoing mail settings are used and customer replies are not tracked back into the AI conversation. |
| `--email-account-display-name` | string | Display value for EmailAccount.DisplayName. |
| `--email-account-email-address` | string | Display value for EmailAccount.EmailAddress. |
| `--internal-notes` | string | Internal context carried onto the help desk ticket created when a HelpDesk-channel action is approved. Visible to operators only, never to the customer. |
| `--help-desk-department-id` | long | ID of the help desk department the ticket is filed under when a HelpDesk-channel action is approved. Empty leaves the ticket unassigned. |
| `--help-desk-department-name` | string | Display value for HelpDeskDepartment.Name. |
| `--help-desk-priority` | enum | Priority applied to the help desk ticket created when a HelpDesk-channel action is approved (Low, Normal, High, Critical). Empty for actions on any other channel. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProposedAction sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` descending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (descending).

#### ProposedAction create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this proposed action. Set from the location whose agents produced it. |
| `--coworker-id` | long | ID of the customer this action targets. Empty for internal alerts and for leads that have no customer record yet. |
| `--ai-channel-session-id` | long | ID of the AI conversation that triggered this action. Only set for criteria that evaluate conversations, such as unanswered-question and dormant-lead detection. |
| `--criteria-type` | string, required | Identifier of the agent that produced this action, matching a criteria evaluator name such as DueInvoiceCriteria, ContractExpiryCriteria, SupportPatternCriteria, SupportIssueCategoryCriteria or MissingFaqCriteria. Behaviour for each is configured through ProactiveActionConfig. |
| `--action-type` | enum, required | What the action does once approved: DraftMessage sends a composed message to the customer, VoiceOutreach places an AI call, InternalNote raises an operator-only alert with no customer contact, TaskReminder records a follow-up. InternalNote actions have no customer target and no delivery channel. |
| `--channel` | enum, required | How an approved action reaches the customer: Email for an AI-tracked email conversation, Voice for an outbound AI call, CoworkerMessage for a message sent from a connected email account, HelpDesk to raise a ticket, or WhatsApp. Operators can change the channel at approval time. Ignored for InternalNote actions. |
| `--draft-subject` | string | AI-composed subject line for the proposed message. Operators may edit it before approving; for internal alerts it doubles as the alert headline. |
| `--draft-body` | string | AI-composed message body, call script, or — for internal alerts — the alert text itself. Operators may edit it before approving. |
| `--confidence` | decimal, required | AI confidence in this recommendation, on a 0.0–1.0 scale (not a percentage). When the matching ProactiveActionConfig enables auto-execution, an action at or above its AutoExecuteMinConfidence skips the review inbox. |
| `--priority` | enum, required | Urgency assigned by the agent that raised the action: Low, Medium, High or Critical. Drives inbox ordering and the urgency indicator; it does not change delivery behaviour. |
| `--status` | enum, required | Where the action sits in its lifecycle: Pending awaits review; Snoozed is hidden until its wake time; Approved has been accepted for delivery; AutoExecuted was sent without review because confidence cleared the configured threshold; Deferred is approved but waiting for the recipient's next calling window; AwaitingReply has sent a WhatsApp opt-in template and is waiting on the customer; Rejected was dismissed; Expired passed its review deadline unattended. Change it through the approve, reject and snooze operations rather than by writing this field. |
| `--reviewed-by-id` | long | ID of the operator who last reviewed this action. Empty while it is still awaiting review or when the system expired it unattended. |
| `--reviewed-on` | DateTime | UTC time an operator last approved, rejected or snoozed this action. |
| `--review-notes` | string | Notes recorded when an operator approves, rejects or snoozes the action. The system also appends here when it expires an action, for example because no calling window was available. |
| `--executed-on` | DateTime | UTC time the approved action was actually delivered or the outbound call placed. Empty while the action is still queued or deferred. |
| `--outcome-session-id` | long | ID of the AI conversation created when this action was delivered. Use it to follow the reply thread, escalated tickets and messages that came out of the outreach. |
| `--expires-on` | DateTime | UTC review deadline, defaulting to three days after the action is created. A Pending action past this point is moved to Expired; for a Snoozed action this instead holds the wake time set by the snooze duration. |
| `--deduplication-key` | string | Read-only key that prevents duplicate proposals for the same trigger, shaped as "criteria-type:{identifier}:{tier}" (for example "invoice:123:reminder:1"). A new proposal is suppressed while a non-expired action with the same key exists inside the criteria's cooldown window. |
| `--scheduled-execution-time` | DateTime | UTC time a Deferred action becomes due, set automatically to the recipient's next calling window when approval lands outside permitted outbound hours. |
| `--deferral-reason` | string | System-written explanation of why delivery was postponed, recorded when an approved action falls outside the recipient's permitted calling hours. |
| `--deferral-count` | int, required | Number of times delivery has been postponed for calling hours. Counts up from zero and helps spot actions that keep missing their window. |
| `--email-account-id` | long | ID of the connected email account used as the sender when an approved action goes out over the CoworkerMessage channel. Empty means the location's default outgoing mail settings are used and customer replies are not tracked back into the AI conversation. |
| `--internal-notes` | string | Internal context carried onto the help desk ticket created when a HelpDesk-channel action is approved. Visible to operators only, never to the customer. |
| `--help-desk-department-id` | long | ID of the help desk department the ticket is filed under when a HelpDesk-channel action is approved. Empty leaves the ticket unassigned. |
| `--help-desk-priority` | enum | Priority applied to the help desk ticket created when a HelpDesk-channel action is approved (Low, Normal, High, Critical). Empty for actions on any other channel. |

#### ProposedAction update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this proposed action. Set from the location whose agents produced it. |
| `--coworker-id` | long | ID of the customer this action targets. Empty for internal alerts and for leads that have no customer record yet. |
| `--ai-channel-session-id` | long | ID of the AI conversation that triggered this action. Only set for criteria that evaluate conversations, such as unanswered-question and dormant-lead detection. |
| `--criteria-type` | string | Identifier of the agent that produced this action, matching a criteria evaluator name such as DueInvoiceCriteria, ContractExpiryCriteria, SupportPatternCriteria, SupportIssueCategoryCriteria or MissingFaqCriteria. Behaviour for each is configured through ProactiveActionConfig. |
| `--action-type` | enum | What the action does once approved: DraftMessage sends a composed message to the customer, VoiceOutreach places an AI call, InternalNote raises an operator-only alert with no customer contact, TaskReminder records a follow-up. InternalNote actions have no customer target and no delivery channel. |
| `--channel` | enum | How an approved action reaches the customer: Email for an AI-tracked email conversation, Voice for an outbound AI call, CoworkerMessage for a message sent from a connected email account, HelpDesk to raise a ticket, or WhatsApp. Operators can change the channel at approval time. Ignored for InternalNote actions. |
| `--draft-subject` | string | AI-composed subject line for the proposed message. Operators may edit it before approving; for internal alerts it doubles as the alert headline. |
| `--draft-body` | string | AI-composed message body, call script, or — for internal alerts — the alert text itself. Operators may edit it before approving. |
| `--confidence` | decimal | AI confidence in this recommendation, on a 0.0–1.0 scale (not a percentage). When the matching ProactiveActionConfig enables auto-execution, an action at or above its AutoExecuteMinConfidence skips the review inbox. |
| `--priority` | enum | Urgency assigned by the agent that raised the action: Low, Medium, High or Critical. Drives inbox ordering and the urgency indicator; it does not change delivery behaviour. |
| `--status` | enum | Where the action sits in its lifecycle: Pending awaits review; Snoozed is hidden until its wake time; Approved has been accepted for delivery; AutoExecuted was sent without review because confidence cleared the configured threshold; Deferred is approved but waiting for the recipient's next calling window; AwaitingReply has sent a WhatsApp opt-in template and is waiting on the customer; Rejected was dismissed; Expired passed its review deadline unattended. Change it through the approve, reject and snooze operations rather than by writing this field. |
| `--reviewed-by-id` | long | ID of the operator who last reviewed this action. Empty while it is still awaiting review or when the system expired it unattended. |
| `--reviewed-on` | DateTime | UTC time an operator last approved, rejected or snoozed this action. |
| `--review-notes` | string | Notes recorded when an operator approves, rejects or snoozes the action. The system also appends here when it expires an action, for example because no calling window was available. |
| `--executed-on` | DateTime | UTC time the approved action was actually delivered or the outbound call placed. Empty while the action is still queued or deferred. |
| `--outcome-session-id` | long | ID of the AI conversation created when this action was delivered. Use it to follow the reply thread, escalated tickets and messages that came out of the outreach. |
| `--expires-on` | DateTime | UTC review deadline, defaulting to three days after the action is created. A Pending action past this point is moved to Expired; for a Snoozed action this instead holds the wake time set by the snooze duration. |
| `--deduplication-key` | string | Read-only key that prevents duplicate proposals for the same trigger, shaped as "criteria-type:{identifier}:{tier}" (for example "invoice:123:reminder:1"). A new proposal is suppressed while a non-expired action with the same key exists inside the criteria's cooldown window. |
| `--scheduled-execution-time` | DateTime | UTC time a Deferred action becomes due, set automatically to the recipient's next calling window when approval lands outside permitted outbound hours. |
| `--deferral-reason` | string | System-written explanation of why delivery was postponed, recorded when an approved action falls outside the recipient's permitted calling hours. |
| `--deferral-count` | int | Number of times delivery has been postponed for calling hours. Counts up from zero and helps spot actions that keep missing their window. |
| `--email-account-id` | long | ID of the connected email account used as the sender when an approved action goes out over the CoworkerMessage channel. Empty means the location's default outgoing mail settings are used and customer replies are not tracked back into the AI conversation. |
| `--internal-notes` | string | Internal context carried onto the help desk ticket created when a HelpDesk-channel action is approved. Visible to operators only, never to the customer. |
| `--help-desk-department-id` | long | ID of the help desk department the ticket is filed under when a HelpDesk-channel action is approved. Empty leaves the ticket unassigned. |
| `--help-desk-priority` | enum | Priority applied to the help desk ticket created when a HelpDesk-channel action is approved (Low, Normal, High, Critical). Empty for actions on any other channel. |

#### ProposedAction PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--reviewed-by-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--reviewed-by-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus proposedactions update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### ProposedAction enum values

| Option | Valid values |
| ------ | ------------ |
| `--action-type` | `1` DraftMessage, `2` VoiceOutreach, `3` InternalNote, `4` TaskReminder |
| `--channel` | `1` Email, `2` Voice, `3` CoworkerMessage, `4` HelpDesk, `5` WhatsApp |
| `--priority` | `1` Low, `2` Medium, `3` High, `4` Critical |
| `--status` | `1` Pending, `2` Approved, `3` Rejected, `4` Expired, `5` AutoExecuted, `6` Snoozed, `7` Deferred, `8` AwaitingReply |

<!-- END:GENERATED entity=ProposedActions -->
