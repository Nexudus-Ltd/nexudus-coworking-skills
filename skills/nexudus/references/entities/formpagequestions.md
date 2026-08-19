# FormPageQuestions

<!-- BEGIN:GENERATED entity=FormPageQuestions -->

A form question (FormPageQuestion) is an ordered question within a location's customer form. It defines the customer-facing label, explanation, input type, optional choices, and whether the question is shown or required.

FormPageQuestions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus formpagequestions list --agent` | List all formpagequestions |
| `nexudus formpagequestions list --id <id> --agent` | Filter by single ID |
| `nexudus formpagequestions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus formpagequestions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus formpagequestions list --form-page-id <value> --form-page-name <value> --agent` | Filter formpagequestions by properties |
| `nexudus formpagequestions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus formpagequestions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus formpagequestions get <id> --agent` | Get single formpagequestion |
| `nexudus formpagequestions create --form-page-id <value> --text <value> --description <value> --display-order <value> --question-type <value> --agent` | Create formpagequestion |
| `nexudus formpagequestions update <id> --name "New Name" --agent` | Update formpagequestion |
| `nexudus formpagequestions delete <id> --yes --agent` | Delete formpagequestion (no prompt) |

#### FormPageQuestion list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-id` | long | ID of the form that contains this question; the form's location determines access to the question |
| `--form-page-name` | string | Display name of the linked form page (read-only) |
| `--text` | string | Required question label shown to customers |
| `--description` | string | Required explanatory text shown below the question to customers |
| `--available-options` | string | Comma-separated choices for a Dropdown question; leave empty for other question types |
| `--active` | bool | Whether this question appears in the customer-facing form |
| `--display-order` | int | Integer position for displaying this question; lower values appear first and the system renumbers questions after create or update |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--allow-multiple-options` | bool | Whether customers can select more than one choice for a Dropdown question |
| `--is-required` | bool | Whether the customer-facing form marks an answer to this question as required |
| `--question-type` | enum | Controls the customer input: Text, Boolean (Yes/No), LongText, Date, Dropdown, or Binary file upload; defaults to Text |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FormPageQuestion sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FormPageQuestion create options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-id` | long, required | ID of the form that contains this question; the form's location determines access to the question |
| `--text` | string, required | Required question label shown to customers |
| `--description` | string, required | Required explanatory text shown below the question to customers |
| `--available-options` | string | Comma-separated choices for a Dropdown question; leave empty for other question types |
| `--active` | bool | Whether this question appears in the customer-facing form |
| `--display-order` | int, required | Integer position for displaying this question; lower values appear first and the system renumbers questions after create or update |
| `--allow-multiple-options` | bool | Whether customers can select more than one choice for a Dropdown question |
| `--is-required` | bool | Whether the customer-facing form marks an answer to this question as required |
| `--question-type` | enum, required | Controls the customer input: Text, Boolean (Yes/No), LongText, Date, Dropdown, or Binary file upload; defaults to Text |

#### FormPageQuestion update options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-id` | long | ID of the form that contains this question; the form's location determines access to the question |
| `--text` | string | Required question label shown to customers |
| `--description` | string | Required explanatory text shown below the question to customers |
| `--available-options` | string | Comma-separated choices for a Dropdown question; leave empty for other question types |
| `--active` | bool | Whether this question appears in the customer-facing form |
| `--display-order` | int | Integer position for displaying this question; lower values appear first and the system renumbers questions after create or update |
| `--allow-multiple-options` | bool | Whether customers can select more than one choice for a Dropdown question |
| `--is-required` | bool | Whether the customer-facing form marks an answer to this question as required |
| `--question-type` | enum | Controls the customer input: Text, Boolean (Yes/No), LongText, Date, Dropdown, or Binary file upload; defaults to Text |

#### FormPageQuestion enum values

| Option | Valid values |
| ------ | ------------ |
| `--question-type` | `1` Text, `2` Boolean, `3` LongText, `4` Date, `5` Dropdown, `6` Binary |

<!-- END:GENERATED entity=FormPageQuestions -->
