# RecordCreationWorkflowVersions

<!-- BEGIN:GENERATED entity=RecordCreationWorkflowVersions -->

A mutable draft or immutable published version of a record creation workflow.

RecordCreationWorkflowVersions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus recordcreationworkflowversions list --agent` | List all recordcreationworkflowversions |
| `nexudus recordcreationworkflowversions list --id <id> --agent` | Filter by single ID |
| `nexudus recordcreationworkflowversions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus recordcreationworkflowversions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus recordcreationworkflowversions list --workflow-id <value> --version-number <value> --agent` | Filter recordcreationworkflowversions by properties |
| `nexudus recordcreationworkflowversions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus recordcreationworkflowversions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus recordcreationworkflowversions get <id> --agent` | Get single recordcreationworkflowversion |
| `nexudus recordcreationworkflowversions create --workflow-id <value> --version-number <value> --schema-version <value> --definition-json <value> --definition-hash <value> --agent` | Create recordcreationworkflowversion |
| `nexudus recordcreationworkflowversions update <id> --name "New Name" --agent` | Update recordcreationworkflowversion |
| `nexudus recordcreationworkflowversions delete <id> --yes --agent` | Delete recordcreationworkflowversion (no prompt) |

#### RecordCreationWorkflowVersion list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--workflow-id` | long | Workflow that owns this version |
| `--version-number` | int | Monotonic version number within the workflow |
| `--from-version-number` | range | |
| `--to-version-number` | range | |
| `--schema-version` | int | Version of the persisted workflow document contract |
| `--from-schema-version` | range | |
| `--to-schema-version` | range | |
| `--definition-json` | string | Full JSON workflow document |
| `--definition-hash` | string | Deterministic hash of the workflow document |
| `--is-draft` | bool | Whether this version remains mutable |
| `--validation-json` | string | Last validation result for diagnostics |
| `--published-on` | DateTime | Date and time this immutable version was published |
| `--from-published-on` | range | |
| `--to-published-on` | range | |
| `--published-by-user-id` | long | User who published this version |
| `--concurrency-token` | string | Optimistic concurrency token changed on every draft save |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### RecordCreationWorkflowVersion sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### RecordCreationWorkflowVersion create options

| Option | Type | Description |
| --- | --- | --- |
| `--workflow-id` | long, required | Workflow that owns this version |
| `--version-number` | int, required | Monotonic version number within the workflow |
| `--schema-version` | int, required | Version of the persisted workflow document contract |
| `--definition-json` | string, required | Full JSON workflow document |
| `--definition-hash` | string, required | Deterministic hash of the workflow document |
| `--is-draft` | bool | Whether this version remains mutable |
| `--validation-json` | string | Last validation result for diagnostics |
| `--published-on` | DateTime | Date and time this immutable version was published |
| `--published-by-user-id` | long | User who published this version |
| `--concurrency-token` | string | Optimistic concurrency token changed on every draft save |

#### RecordCreationWorkflowVersion update options

| Option | Type | Description |
| --- | --- | --- |
| `--workflow-id` | long | Workflow that owns this version |
| `--version-number` | int | Monotonic version number within the workflow |
| `--schema-version` | int | Version of the persisted workflow document contract |
| `--definition-json` | string | Full JSON workflow document |
| `--definition-hash` | string | Deterministic hash of the workflow document |
| `--is-draft` | bool | Whether this version remains mutable |
| `--validation-json` | string | Last validation result for diagnostics |
| `--published-on` | DateTime | Date and time this immutable version was published |
| `--published-by-user-id` | long | User who published this version |
| `--concurrency-token` | string | Optimistic concurrency token changed on every draft save |

#### RecordCreationWorkflowVersion PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--published-by-user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--published-by-user-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus recordcreationworkflowversions update <id> --published-by-user-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=RecordCreationWorkflowVersions -->
