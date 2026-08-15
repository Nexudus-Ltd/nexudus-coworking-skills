# ProactiveActionConfigs

<!-- BEGIN:GENERATED entity=ProactiveActionConfigs -->

A **ProactiveActionConfig** defines how a specific proactive criteria type behaves for a business. Each configuration controls whether a criteria evaluator is enabled, whether approved actions can auto-execute, rate limits, cooldown periods, and channel preferences.

The system uses a **human-in-the-loop** approach by default — proposed actions surface in an operator inbox for review. Individual criteria can be promoted to auto-execute mode when `AutoExecute` is enabled and the AI confidence score meets `AutoExecuteMinConfidence`.

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
| `--business-id` | long | ID of the business linked to this record |
| `--criteria-type` | string | Identifier for the criteria evaluator this config applies to (e.g. DueInvoiceCriteria, ContractExpiryCriteria, SupportPatternCriteria). |
| `--enabled` | bool | Whether this criteria type is active for the business. Disabled criteria will not produce proposed actions. |
| `--auto-execute` | bool | When enabled, proposed actions from this criteria skip the operator inbox and execute immediately if confidence meets the minimum threshold. |
| `--auto-execute-min-confidence` | decimal | Minimum AI confidence score (0.0–1.0) required for auto-execution. Actions below this threshold still require operator approval. |
| `--from-auto-execute-min-confidence` | range | |
| `--to-auto-execute-min-confidence` | range | |
| `--max-actions-per-day` | int | Maximum number of actions this criteria can produce per day for the business. Null means no limit. |
| `--from-max-actions-per-day` | range | |
| `--to-max-actions-per-day` | range | |
| `--cooldown-hours` | int | Minimum hours between actions targeting the same customer for this criteria type. Prevents excessive outreach. |
| `--from-cooldown-hours` | range | |
| `--to-cooldown-hours` | range | |
| `--channel-preference` | enum | Preferred outbound channel for actions from this criteria (Email, Voice, CoworkerMessage, HelpDesk, WhatsApp). Null lets the AI choose. |
| `--custom-prompt-override` | string | Business-specific prompt customization for message composition. If it starts with 'OVERRIDE:' (case-insensitive), it replaces the entire criteria template; otherwise it appends as additional instructions. |
| `--first-message` | string | Custom first message template used when initiating outbound conversations for this criteria type. |
| `--system-prompt` | string | Custom system prompt for the AI agent during outbound conversations initiated by this criteria. |
| `--criteria-configuration` | string | JSON-serialized configuration specific to this criteria type (e.g. threshold values, tier definitions, day counts). |
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
| `--business-id` | long, required | ID of the business linked to this record |
| `--criteria-type` | string, required | Identifier for the criteria evaluator this config applies to (e.g. DueInvoiceCriteria, ContractExpiryCriteria, SupportPatternCriteria). |
| `--enabled` | bool | Whether this criteria type is active for the business. Disabled criteria will not produce proposed actions. |
| `--auto-execute` | bool | When enabled, proposed actions from this criteria skip the operator inbox and execute immediately if confidence meets the minimum threshold. |
| `--auto-execute-min-confidence` | decimal, required | Minimum AI confidence score (0.0–1.0) required for auto-execution. Actions below this threshold still require operator approval. |
| `--max-actions-per-day` | int | Maximum number of actions this criteria can produce per day for the business. Null means no limit. |
| `--cooldown-hours` | int, required | Minimum hours between actions targeting the same customer for this criteria type. Prevents excessive outreach. |
| `--channel-preference` | enum | Preferred outbound channel for actions from this criteria (Email, Voice, CoworkerMessage, HelpDesk, WhatsApp). Null lets the AI choose. |
| `--custom-prompt-override` | string | Business-specific prompt customization for message composition. If it starts with 'OVERRIDE:' (case-insensitive), it replaces the entire criteria template; otherwise it appends as additional instructions. |
| `--first-message` | string | Custom first message template used when initiating outbound conversations for this criteria type. |
| `--system-prompt` | string | Custom system prompt for the AI agent during outbound conversations initiated by this criteria. |
| `--criteria-configuration` | string | JSON-serialized configuration specific to this criteria type (e.g. threshold values, tier definitions, day counts). |

#### ProactiveActionConfig update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--criteria-type` | string | Identifier for the criteria evaluator this config applies to (e.g. DueInvoiceCriteria, ContractExpiryCriteria, SupportPatternCriteria). |
| `--enabled` | bool | Whether this criteria type is active for the business. Disabled criteria will not produce proposed actions. |
| `--auto-execute` | bool | When enabled, proposed actions from this criteria skip the operator inbox and execute immediately if confidence meets the minimum threshold. |
| `--auto-execute-min-confidence` | decimal | Minimum AI confidence score (0.0–1.0) required for auto-execution. Actions below this threshold still require operator approval. |
| `--max-actions-per-day` | int | Maximum number of actions this criteria can produce per day for the business. Null means no limit. |
| `--cooldown-hours` | int | Minimum hours between actions targeting the same customer for this criteria type. Prevents excessive outreach. |
| `--channel-preference` | enum | Preferred outbound channel for actions from this criteria (Email, Voice, CoworkerMessage, HelpDesk, WhatsApp). Null lets the AI choose. |
| `--custom-prompt-override` | string | Business-specific prompt customization for message composition. If it starts with 'OVERRIDE:' (case-insensitive), it replaces the entire criteria template; otherwise it appends as additional instructions. |
| `--first-message` | string | Custom first message template used when initiating outbound conversations for this criteria type. |
| `--system-prompt` | string | Custom system prompt for the AI agent during outbound conversations initiated by this criteria. |
| `--criteria-configuration` | string | JSON-serialized configuration specific to this criteria type (e.g. threshold values, tier definitions, day counts). |

<!-- END:GENERATED entity=ProactiveActionConfigs -->
