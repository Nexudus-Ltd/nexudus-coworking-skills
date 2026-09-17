# ProactiveActionConfigs

<!-- BEGIN:GENERATED entity=ProactiveActionConfigs -->

A ProactiveActionConfig is the settings row for one proactive AI agent at one location: whether it runs at all, whether it may act without human review and above what confidence, how many actions it may raise per day, how long it waits before repeating itself, which delivery channel it prefers, and any custom drafting or voice prompts. There is at most one row per location and CriteriaType, and an agent with no row is off. The default posture is human-in-the-loop: the agent raises ProposedAction records into the operator AI Inbox for review, and only turning on AutoExecute lets sufficiently confident actions go out unattended.

ProactiveActionConfigs support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proactiveactionconfigs list --agent` | List all proactiveactionconfigs |
| `nexudus proactiveactionconfigs list --id <id> --agent` | Filter by single ID |
| `nexudus proactiveactionconfigs list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proactiveactionconfigs list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proactiveactionconfigs list --business-id <value> --criteria-type <value> --agent` | Filter proactiveactionconfigs by properties |
| `nexudus proactiveactionconfigs list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proactiveactionconfigs list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus proactiveactionconfigs get <id> --agent` | Get single proactiveactionconfig |
| `nexudus proactiveactionconfigs create --business-id <value> --criteria-type <value> --auto-execute-min-confidence <value> --cooldown-hours <value> --agent` | Create proactiveactionconfig |
| `nexudus proactiveactionconfigs update <id> --name "New Name" --agent` | Update proactiveactionconfig |
| `nexudus proactiveactionconfigs delete <id> --yes --agent` | Delete proactiveactionconfig (no prompt) |

#### ProactiveActionConfig list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this agent configuration applies to. Each location holds at most one configuration per CriteriaType, and an agent with no configuration row is treated as off. |
| `--criteria-type` | string | Name of the proactive agent this configuration governs, matching a criteria evaluator: DueInvoiceCriteria, ContractExpiryCriteria, SupportPatternCriteria, SupportIssueCategoryCriteria or MissingFaqCriteria. Unique per location; the actions it produces carry the same value in ProposedAction.CriteriaType. |
| `--enabled` | bool | Whether this agent runs for the location. When false, or when no configuration row exists at all, the agent is skipped entirely and proposes nothing. |
| `--auto-execute` | bool | Whether this agent may act without human review. When true, an action whose confidence reaches AutoExecuteMinConfidence is delivered straight away and recorded as AutoExecuted; anything below it still lands in the inbox. Internal-alert agents ignore this. |
| `--auto-execute-min-confidence` | decimal | Confidence an action must reach before AutoExecute will send it without review, on a 0.0–1.0 scale (not a percentage). Defaults to 0.85. Has no effect while AutoExecute is false. |
| `--from-auto-execute-min-confidence` | range | |
| `--to-auto-execute-min-confidence` | range | |
| `--max-actions-per-day` | int | Cap on how many actions this agent may raise for the location in a single day; it also caps how many candidates one evaluation run will consider. Empty means uncapped, in which case a run still considers at most 20 candidates. |
| `--from-max-actions-per-day` | range | |
| `--to-max-actions-per-day` | range | |
| `--cooldown-hours` | int | How long the agent waits before raising the same trigger again, in hours; defaults to 24. A candidate is skipped when a non-expired action with the same deduplication key was created inside this window, so in practice it throttles repeat outreach about the same invoice, contract or customer. |
| `--from-cooldown-hours` | range | |
| `--to-cooldown-hours` | range | |
| `--channel-preference` | enum | Overrides the delivery channel this agent proposes: Email, Voice, CoworkerMessage, HelpDesk or WhatsApp. Empty leaves the choice to the agent's own default. Voice requires the location's AI voice channel to be enabled, and WhatsApp requires a configured WhatsApp number. |
| `--custom-prompt-override` | string | Extra drafting instructions for this agent, up to 2000 characters, appended to its built-in prompt — for example a tone or signature convention. Starting the text with "OVERRIDE:" (case-insensitive) replaces the agent's whole prompt template instead of adding to it. |
| `--first-message` | string | Opening line spoken or sent when this agent starts an outbound conversation, up to 500 characters. Supports {{variable}} placeholders such as {{company_name}} plus the agent-specific variables listed by the criteria-variables endpoint. Empty uses the built-in opening. |
| `--system-prompt` | string | Voice-agent system prompt for outbound conversations this agent starts, up to 2000 characters. By default the text is added to the standard prompt; starting it with "OVERRIDE:" (case-insensitive) replaces the standard prompt entirely, and the server then rejects the save unless the text also contains the {{voice_message}} placeholder. |
| `--criteria-configuration` | string | Agent-specific thresholds as a flat JSON object of string values, keyed by the parameter keys the criteria-parameters endpoint publishes for this CriteriaType — for example reminder day counts, minimum invoice amounts or ticket thresholds. Empty means every parameter falls back to its published default. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProactiveActionConfig sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CriteriaType` ascending. If no `--order-by` is specified, the API returns results ordered by `CriteriaType` (ascending).

#### ProactiveActionConfig create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this agent configuration applies to. Each location holds at most one configuration per CriteriaType, and an agent with no configuration row is treated as off. |
| `--criteria-type` | string, required | Name of the proactive agent this configuration governs, matching a criteria evaluator: DueInvoiceCriteria, ContractExpiryCriteria, SupportPatternCriteria, SupportIssueCategoryCriteria or MissingFaqCriteria. Unique per location; the actions it produces carry the same value in ProposedAction.CriteriaType. |
| `--enabled` | bool | Whether this agent runs for the location. When false, or when no configuration row exists at all, the agent is skipped entirely and proposes nothing. |
| `--auto-execute` | bool | Whether this agent may act without human review. When true, an action whose confidence reaches AutoExecuteMinConfidence is delivered straight away and recorded as AutoExecuted; anything below it still lands in the inbox. Internal-alert agents ignore this. |
| `--auto-execute-min-confidence` | decimal, required | Confidence an action must reach before AutoExecute will send it without review, on a 0.0–1.0 scale (not a percentage). Defaults to 0.85. Has no effect while AutoExecute is false. |
| `--max-actions-per-day` | int | Cap on how many actions this agent may raise for the location in a single day; it also caps how many candidates one evaluation run will consider. Empty means uncapped, in which case a run still considers at most 20 candidates. |
| `--cooldown-hours` | int, required | How long the agent waits before raising the same trigger again, in hours; defaults to 24. A candidate is skipped when a non-expired action with the same deduplication key was created inside this window, so in practice it throttles repeat outreach about the same invoice, contract or customer. |
| `--channel-preference` | enum | Overrides the delivery channel this agent proposes: Email, Voice, CoworkerMessage, HelpDesk or WhatsApp. Empty leaves the choice to the agent's own default. Voice requires the location's AI voice channel to be enabled, and WhatsApp requires a configured WhatsApp number. |
| `--custom-prompt-override` | string | Extra drafting instructions for this agent, up to 2000 characters, appended to its built-in prompt — for example a tone or signature convention. Starting the text with "OVERRIDE:" (case-insensitive) replaces the agent's whole prompt template instead of adding to it. |
| `--first-message` | string | Opening line spoken or sent when this agent starts an outbound conversation, up to 500 characters. Supports {{variable}} placeholders such as {{company_name}} plus the agent-specific variables listed by the criteria-variables endpoint. Empty uses the built-in opening. |
| `--system-prompt` | string | Voice-agent system prompt for outbound conversations this agent starts, up to 2000 characters. By default the text is added to the standard prompt; starting it with "OVERRIDE:" (case-insensitive) replaces the standard prompt entirely, and the server then rejects the save unless the text also contains the {{voice_message}} placeholder. |
| `--criteria-configuration` | string | Agent-specific thresholds as a flat JSON object of string values, keyed by the parameter keys the criteria-parameters endpoint publishes for this CriteriaType — for example reminder day counts, minimum invoice amounts or ticket thresholds. Empty means every parameter falls back to its published default. |

#### ProactiveActionConfig update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this agent configuration applies to. Each location holds at most one configuration per CriteriaType, and an agent with no configuration row is treated as off. |
| `--criteria-type` | string | Name of the proactive agent this configuration governs, matching a criteria evaluator: DueInvoiceCriteria, ContractExpiryCriteria, SupportPatternCriteria, SupportIssueCategoryCriteria or MissingFaqCriteria. Unique per location; the actions it produces carry the same value in ProposedAction.CriteriaType. |
| `--enabled` | bool | Whether this agent runs for the location. When false, or when no configuration row exists at all, the agent is skipped entirely and proposes nothing. |
| `--auto-execute` | bool | Whether this agent may act without human review. When true, an action whose confidence reaches AutoExecuteMinConfidence is delivered straight away and recorded as AutoExecuted; anything below it still lands in the inbox. Internal-alert agents ignore this. |
| `--auto-execute-min-confidence` | decimal | Confidence an action must reach before AutoExecute will send it without review, on a 0.0–1.0 scale (not a percentage). Defaults to 0.85. Has no effect while AutoExecute is false. |
| `--max-actions-per-day` | int | Cap on how many actions this agent may raise for the location in a single day; it also caps how many candidates one evaluation run will consider. Empty means uncapped, in which case a run still considers at most 20 candidates. |
| `--cooldown-hours` | int | How long the agent waits before raising the same trigger again, in hours; defaults to 24. A candidate is skipped when a non-expired action with the same deduplication key was created inside this window, so in practice it throttles repeat outreach about the same invoice, contract or customer. |
| `--channel-preference` | enum | Overrides the delivery channel this agent proposes: Email, Voice, CoworkerMessage, HelpDesk or WhatsApp. Empty leaves the choice to the agent's own default. Voice requires the location's AI voice channel to be enabled, and WhatsApp requires a configured WhatsApp number. |
| `--custom-prompt-override` | string | Extra drafting instructions for this agent, up to 2000 characters, appended to its built-in prompt — for example a tone or signature convention. Starting the text with "OVERRIDE:" (case-insensitive) replaces the agent's whole prompt template instead of adding to it. |
| `--first-message` | string | Opening line spoken or sent when this agent starts an outbound conversation, up to 500 characters. Supports {{variable}} placeholders such as {{company_name}} plus the agent-specific variables listed by the criteria-variables endpoint. Empty uses the built-in opening. |
| `--system-prompt` | string | Voice-agent system prompt for outbound conversations this agent starts, up to 2000 characters. By default the text is added to the standard prompt; starting it with "OVERRIDE:" (case-insensitive) replaces the standard prompt entirely, and the server then rejects the save unless the text also contains the {{voice_message}} placeholder. |
| `--criteria-configuration` | string | Agent-specific thresholds as a flat JSON object of string values, keyed by the parameter keys the criteria-parameters endpoint publishes for this CriteriaType — for example reminder day counts, minimum invoice amounts or ticket thresholds. Empty means every parameter falls back to its published default. |

<!-- END:GENERATED entity=ProactiveActionConfigs -->
