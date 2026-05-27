# FormPageQuestions

<!-- BEGIN:GENERATED entity=FormPageQuestions -->

A **FormPageQuestion** defines a single question within a form page, including its type (text, boolean, dropdown, etc.), label, validation rules, and display order.

FormPageQuestions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus formpagequestions list --agent` | List all formpagequestions |
| `nexudus formpagequestions list --id <id> --agent` | Filter by single ID |
| `nexudus formpagequestions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus formpagequestions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus formpagequestions list --form-page-id <value> --text <value> --agent` | Filter formpagequestions by properties |
| `nexudus formpagequestions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus formpagequestions get <id> --agent` | Get single formpagequestion |
| `nexudus formpagequestions create --form-page-id <value> --text <value> --description <value> --display-order <value> --question-type <value> --agent` | Create formpagequestion |
| `nexudus formpagequestions update <id> --name "New Name" --agent` | Update formpagequestion |
| `nexudus formpagequestions delete <id> --yes --agent` | Delete formpagequestion (no prompt) |

#### FormPageQuestion list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-id` | long | ID of the form page linked to this record |
| `--text` | string | The text value for this form page question |
| `--description` | string | Free-text description of this form page question |
| `--available-options` | string | The available options value for this form page question |
| `--active` | bool | Whether this form page question is currently active |
| `--display-order` | int | The display order value for this form page question |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--allow-multiple-options` | bool | Whether allow multiple options is enabled |
| `--is-required` | bool | Whether is required is enabled |
| `--question-type` | enum | The question type value for this form page question |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FormPageQuestion create options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-id` | long, required | ID of the form page linked to this record |
| `--text` | string, required | The text value for this form page question |
| `--description` | string, required | Free-text description of this form page question |
| `--available-options` | string | The available options value for this form page question |
| `--active` | bool | Whether this form page question is currently active |
| `--display-order` | int, required | The display order value for this form page question |
| `--allow-multiple-options` | bool | Whether allow multiple options is enabled |
| `--is-required` | bool | Whether is required is enabled |
| `--question-type` | enum, required | The question type value for this form page question |

#### FormPageQuestion update options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-id` | long | ID of the form page linked to this record |
| `--text` | string | The text value for this form page question |
| `--description` | string | Free-text description of this form page question |
| `--available-options` | string | The available options value for this form page question |
| `--active` | bool | Whether this form page question is currently active |
| `--display-order` | int | The display order value for this form page question |
| `--allow-multiple-options` | bool | Whether allow multiple options is enabled |
| `--is-required` | bool | Whether is required is enabled |
| `--question-type` | enum | The question type value for this form page question |

#### FormPageQuestion enum values

| Option | Valid values |
| ------ | ------------ |
| `--question-type` | `1` Text, `2` Boolean, `3` LongText, `4` Date, `5` Dropdown, `6` Binary |

<!-- END:GENERATED entity=FormPageQuestions -->
