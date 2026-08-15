# ProposedActions

<!-- BEGIN:GENERATED entity=ProposedActions -->

A **ProposedAction** is an AI-generated recommendation for proactive outreach to a customer, surfaced in an operator action inbox for review and approval.

The system identifies opportunities through criteria evaluators (e.g. overdue invoices, contract expirations, support patterns, dormant leads) and proposes actions with AI-composed draft content. Operators can approve, edit, reject, or snooze each proposal. Over time, high-confidence criteria can be promoted to auto-execute mode.

**Workflow:** Pending → Approved/Rejected/Snoozed/Deferred → Executed (on approval) → AwaitingReply (for channels expecting responses). Actions auto-expire if not reviewed within their expiry window.

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
| `--business-id` | long | ID of the business linked to this record |
| `--coworker-id` | long | ID of the target coworker for this proposed action. |
| `--ai-channel-session-id` | long | ID of the source AI channel session that triggered this proposed action (for session-based criteria). |
| `--criteria-type` | string | Identifier of the criteria evaluator that produced this action (e.g. DueInvoiceCriteria, ContractExpiryCriteria). |
| `--criteria-payload` | string | JSON-serialized context data from the criteria evaluation (e.g. invoice details, contract dates, support ticket summaries). |
| `--action-type` | enum | Type of proposed action: DraftMessage (compose outbound message), VoiceOutreach (initiate voice call), InternalNote (operator notification), or TaskReminder. |
| `--channel` | enum | Proposed delivery channel for the action (Email, Voice, CoworkerMessage, HelpDesk, WhatsApp). |
| `--draft-subject` | string | AI-composed subject line for the proposed outbound message. |
| `--draft-body` | string | AI-composed message body or call script content for the proposed action. |
| `--confidence` | decimal | AI confidence score (0.0–1.0) indicating how appropriate this action is. High-confidence actions may auto-execute if configured. |
| `--from-confidence` | range | |
| `--to-confidence` | range | |
| `--priority` | enum | Priority level of the proposed action (Low, Medium, High, Critical). Used for inbox sorting and urgency indicators. |
| `--status` | enum | Current lifecycle status: Pending (awaiting review), Approved, Rejected, Expired (not reviewed in time), AutoExecuted, Snoozed, Deferred, or AwaitingReply. |
| `--reviewed-by-id` | long | ID of the operator who reviewed this proposed action. |
| `--reviewed-on` | DateTime | Timestamp when the action was reviewed by an operator. |
| `--from-reviewed-on` | range | |
| `--to-reviewed-on` | range | |
| `--review-notes` | string | Operator notes added during review (e.g. reason for rejection, edits made before approval). |
| `--executed-on` | DateTime | Timestamp when the approved action was actually sent or executed. |
| `--from-executed-on` | range | |
| `--to-executed-on` | range | |
| `--outcome-session-id` | long | ID of the resulting AI channel session created when the action was executed (for tracking conversation outcomes). |
| `--expires-on` | DateTime | Unique key to prevent duplicate proposals for the same trigger (e.g. "invoice:123:reminder:1" for first invoice reminder). Format is "criteria-type:{identifier}:{tier}". |
| `--from-expires-on` | range | |
| `--to-expires-on` | range | |
| `--deduplication-key` | string | Planned execution time for the action (e.g. to respect business hours or timezone preferences). |
| `--scheduled-execution-time` | DateTime | Operator-provided reason for deferring this action to a later time. |
| `--from-scheduled-execution-time` | range | |
| `--to-scheduled-execution-time` | range | |
| `--deferral-reason` | string | Number of times this action has been deferred. Used to prevent indefinite postponement. |
| `--deferral-count` | int | ID of the email account to use as the sender for email-based actions. |
| `--from-deferral-count` | range | |
| `--to-deferral-count` | range | |
| `--email-account-id` | long | Email address of the sender account used for this action. |
| `--internal-notes` | string | Internal notes added by operators for context or tracking purposes. |
| `--help-desk-department-id` | long | ID of the help desk department to associate with this action (for HelpDesk channel actions). |
| `--help-desk-priority` | enum | Priority level for the help desk ticket created from this action (Low, Normal, High, Critical). |
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
| `--business-id` | long, required | ID of the business linked to this record |
| `--coworker-id` | long | ID of the target coworker for this proposed action. |
| `--ai-channel-session-id` | long | ID of the source AI channel session that triggered this proposed action (for session-based criteria). |
| `--criteria-type` | string, required | Identifier of the criteria evaluator that produced this action (e.g. DueInvoiceCriteria, ContractExpiryCriteria). |
| `--criteria-payload` | string | JSON-serialized context data from the criteria evaluation (e.g. invoice details, contract dates, support ticket summaries). |
| `--action-type` | enum, required | Type of proposed action: DraftMessage (compose outbound message), VoiceOutreach (initiate voice call), InternalNote (operator notification), or TaskReminder. |
| `--channel` | enum, required | Proposed delivery channel for the action (Email, Voice, CoworkerMessage, HelpDesk, WhatsApp). |
| `--draft-subject` | string | AI-composed subject line for the proposed outbound message. |
| `--draft-body` | string | AI-composed message body or call script content for the proposed action. |
| `--confidence` | decimal, required | AI confidence score (0.0–1.0) indicating how appropriate this action is. High-confidence actions may auto-execute if configured. |
| `--priority` | enum, required | Priority level of the proposed action (Low, Medium, High, Critical). Used for inbox sorting and urgency indicators. |
| `--status` | enum, required | Current lifecycle status: Pending (awaiting review), Approved, Rejected, Expired (not reviewed in time), AutoExecuted, Snoozed, Deferred, or AwaitingReply. |
| `--reviewed-by-id` | long | ID of the operator who reviewed this proposed action. |
| `--reviewed-on` | DateTime | Timestamp when the action was reviewed by an operator. |
| `--review-notes` | string | Operator notes added during review (e.g. reason for rejection, edits made before approval). |
| `--executed-on` | DateTime | Timestamp when the approved action was actually sent or executed. |
| `--outcome-session-id` | long | ID of the resulting AI channel session created when the action was executed (for tracking conversation outcomes). |
| `--expires-on` | DateTime | Unique key to prevent duplicate proposals for the same trigger (e.g. "invoice:123:reminder:1" for first invoice reminder). Format is "criteria-type:{identifier}:{tier}". |
| `--deduplication-key` | string | Planned execution time for the action (e.g. to respect business hours or timezone preferences). |
| `--scheduled-execution-time` | DateTime | Operator-provided reason for deferring this action to a later time. |
| `--deferral-reason` | string | Number of times this action has been deferred. Used to prevent indefinite postponement. |
| `--deferral-count` | int, required | ID of the email account to use as the sender for email-based actions. |
| `--email-account-id` | long | Email address of the sender account used for this action. |
| `--internal-notes` | string | Internal notes added by operators for context or tracking purposes. |
| `--help-desk-department-id` | long | ID of the help desk department to associate with this action (for HelpDesk channel actions). |
| `--help-desk-priority` | enum | Priority level for the help desk ticket created from this action (Low, Normal, High, Critical). |

#### ProposedAction update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--coworker-id` | long | ID of the target coworker for this proposed action. |
| `--ai-channel-session-id` | long | ID of the source AI channel session that triggered this proposed action (for session-based criteria). |
| `--criteria-type` | string | Identifier of the criteria evaluator that produced this action (e.g. DueInvoiceCriteria, ContractExpiryCriteria). |
| `--criteria-payload` | string | JSON-serialized context data from the criteria evaluation (e.g. invoice details, contract dates, support ticket summaries). |
| `--action-type` | enum | Type of proposed action: DraftMessage (compose outbound message), VoiceOutreach (initiate voice call), InternalNote (operator notification), or TaskReminder. |
| `--channel` | enum | Proposed delivery channel for the action (Email, Voice, CoworkerMessage, HelpDesk, WhatsApp). |
| `--draft-subject` | string | AI-composed subject line for the proposed outbound message. |
| `--draft-body` | string | AI-composed message body or call script content for the proposed action. |
| `--confidence` | decimal | AI confidence score (0.0–1.0) indicating how appropriate this action is. High-confidence actions may auto-execute if configured. |
| `--priority` | enum | Priority level of the proposed action (Low, Medium, High, Critical). Used for inbox sorting and urgency indicators. |
| `--status` | enum | Current lifecycle status: Pending (awaiting review), Approved, Rejected, Expired (not reviewed in time), AutoExecuted, Snoozed, Deferred, or AwaitingReply. |
| `--reviewed-by-id` | long | ID of the operator who reviewed this proposed action. |
| `--reviewed-on` | DateTime | Timestamp when the action was reviewed by an operator. |
| `--review-notes` | string | Operator notes added during review (e.g. reason for rejection, edits made before approval). |
| `--executed-on` | DateTime | Timestamp when the approved action was actually sent or executed. |
| `--outcome-session-id` | long | ID of the resulting AI channel session created when the action was executed (for tracking conversation outcomes). |
| `--expires-on` | DateTime | Unique key to prevent duplicate proposals for the same trigger (e.g. "invoice:123:reminder:1" for first invoice reminder). Format is "criteria-type:{identifier}:{tier}". |
| `--deduplication-key` | string | Planned execution time for the action (e.g. to respect business hours or timezone preferences). |
| `--scheduled-execution-time` | DateTime | Operator-provided reason for deferring this action to a later time. |
| `--deferral-reason` | string | Number of times this action has been deferred. Used to prevent indefinite postponement. |
| `--deferral-count` | int | ID of the email account to use as the sender for email-based actions. |
| `--email-account-id` | long | Email address of the sender account used for this action. |
| `--internal-notes` | string | Internal notes added by operators for context or tracking purposes. |
| `--help-desk-department-id` | long | ID of the help desk department to associate with this action (for HelpDesk channel actions). |
| `--help-desk-priority` | enum | Priority level for the help desk ticket created from this action (Low, Normal, High, Critical). |

#### ProposedAction PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
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
