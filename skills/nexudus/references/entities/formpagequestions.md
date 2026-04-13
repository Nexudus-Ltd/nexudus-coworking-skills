# FormPageQuestions

<!-- BEGIN:GENERATED entity=FormPageQuestions -->

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

`--form-page-id` (long), `--text`, `--description`, `--available-options`, `--active` (bool), `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--allow-multiple-options` (bool), `--is-required` (bool), `--question-type` (enum), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FormPageQuestion create options

`--form-page-id` (long, required), `--text` (required), `--description` (required), `--available-options`, `--active` (bool), `--display-order` (int, required), `--allow-multiple-options` (bool), `--is-required` (bool), `--question-type` (enum, required)

#### FormPageQuestion update options

`--form-page-id` (long), `--text`, `--description`, `--available-options`, `--active` (bool), `--display-order` (int), `--allow-multiple-options` (bool), `--is-required` (bool), `--question-type` (enum)

<!-- END:GENERATED entity=FormPageQuestions -->
