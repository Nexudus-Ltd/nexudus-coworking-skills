# RecordCreationWorkflows

<!-- BEGIN:GENERATED entity=RecordCreationWorkflows -->

A business-scoped record creation workflow with draft and published versions.

RecordCreationWorkflows support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus recordcreationworkflows list --agent` | List all recordcreationworkflows |
| `nexudus recordcreationworkflows list --id <id> --agent` | Filter by single ID |
| `nexudus recordcreationworkflows list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus recordcreationworkflows list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus recordcreationworkflows list --business-id <value> --name <value> --agent` | Filter recordcreationworkflows by properties |
| `nexudus recordcreationworkflows list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus recordcreationworkflows list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus recordcreationworkflows get <id> --agent` | Get single recordcreationworkflow |
| `nexudus recordcreationworkflows create --business-id <value> --name <value> --entity-domain <value> --entity-type <value> --status <value> --source-type <value> --created-by-user-id <value> --updated-by-user-id <value> --agent` | Create recordcreationworkflow |
| `nexudus recordcreationworkflows update <id> --name "New Name" --agent` | Update recordcreationworkflow |
| `nexudus recordcreationworkflows delete <id> --yes --agent` | Delete recordcreationworkflow (no prompt) |

#### RecordCreationWorkflow list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business that owns this workflow |
| `--name` | string | Display name of the workflow |
| `--description` | string | Optional description of the workflow |
| `--entity-domain` | string | Domain of the entity created by this workflow |
| `--entity-type` | string | Type of entity created by this workflow |
| `--status` | enum | Current lifecycle status of the workflow |
| `--source-type` | enum | How this workflow was originally created |
| `--source-key` | string | Stable key of the source template |
| `--source-revision` | string | Revision of the source template when copied |
| `--is-default` | bool | Whether this is the default published workflow for its entity |
| `--allow-form-launch` | bool | Whether users can launch this workflow from entity creation |
| `--allow-chat-launch` | bool | Whether users can launch this workflow from chat |
| `--allow-url-launch` | bool | Whether users can launch this workflow from its dedicated URL |
| `--draft-version-id` | long | Current mutable draft version |
| `--published-version-id` | long | Current immutable published version |
| `--created-by-user-id` | long | User who created the workflow |
| `--created-by-user-full-name` | string | Full name of the user who created the workflow |
| `--created-by-user-email` | string | Email address of the user who created the workflow |
| `--updated-by-user-id` | long | User who last updated the workflow |
| `--updated-by-user-full-name` | string | Full name of the user who last updated the workflow |
| `--updated-by-user-email` | string | Email address of the user who last updated the workflow |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### RecordCreationWorkflow sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### RecordCreationWorkflow create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business that owns this workflow |
| `--name` | string, required | Display name of the workflow |
| `--description` | string | Optional description of the workflow |
| `--entity-domain` | string, required | Domain of the entity created by this workflow |
| `--entity-type` | string, required | Type of entity created by this workflow |
| `--status` | enum, required | Current lifecycle status of the workflow |
| `--source-type` | enum, required | How this workflow was originally created |
| `--source-key` | string | Stable key of the source template |
| `--source-revision` | string | Revision of the source template when copied |
| `--is-default` | bool | Whether this is the default published workflow for its entity |
| `--allow-form-launch` | bool | Whether users can launch this workflow from entity creation |
| `--allow-chat-launch` | bool | Whether users can launch this workflow from chat |
| `--allow-url-launch` | bool | Whether users can launch this workflow from its dedicated URL |
| `--draft-version-id` | long | Current mutable draft version |
| `--published-version-id` | long | Current immutable published version |
| `--created-by-user-id` | long, required | User who created the workflow |
| `--updated-by-user-id` | long, required | User who last updated the workflow |

#### RecordCreationWorkflow update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business that owns this workflow |
| `--name` | string | Display name of the workflow |
| `--description` | string | Optional description of the workflow |
| `--entity-domain` | string | Domain of the entity created by this workflow |
| `--entity-type` | string | Type of entity created by this workflow |
| `--status` | enum | Current lifecycle status of the workflow |
| `--source-type` | enum | How this workflow was originally created |
| `--source-key` | string | Stable key of the source template |
| `--source-revision` | string | Revision of the source template when copied |
| `--is-default` | bool | Whether this is the default published workflow for its entity |
| `--allow-form-launch` | bool | Whether users can launch this workflow from entity creation |
| `--allow-chat-launch` | bool | Whether users can launch this workflow from chat |
| `--allow-url-launch` | bool | Whether users can launch this workflow from its dedicated URL |
| `--draft-version-id` | long | Current mutable draft version |
| `--published-version-id` | long | Current immutable published version |
| `--created-by-user-id` | long | User who created the workflow |
| `--updated-by-user-id` | long | User who last updated the workflow |

#### RecordCreationWorkflow PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--created-by-user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--created-by-user-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--updated-by-user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--updated-by-user-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus recordcreationworkflows update <id> --created-by-user-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### RecordCreationWorkflow enum values

| Option | Valid values |
| ------ | ------------ |
| `--status` | `1` Draft, `2` Published, `3` Archived |
| `--source-type` | `1` Blank, `2` BuiltIn, `3` Generated, `4` Duplicated |

<!-- END:GENERATED entity=RecordCreationWorkflows -->
