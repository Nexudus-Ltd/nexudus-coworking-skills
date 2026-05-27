# EmailTemplateFiles

<!-- BEGIN:GENERATED entity=EmailTemplateFiles -->

An **EmailTemplateFile** defines an email template used for automated communications such as welcome emails, invoices, booking confirmations, and reminders. Templates are language-specific and can be customised per location.

EmailTemplateFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus emailtemplatefiles list --agent` | List all emailtemplatefiles |
| `nexudus emailtemplatefiles list --id <id> --agent` | Filter by single ID |
| `nexudus emailtemplatefiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus emailtemplatefiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus emailtemplatefiles list --business-id <value> --language <value> --agent` | Filter emailtemplatefiles by properties |
| `nexudus emailtemplatefiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus emailtemplatefiles get <id> --agent` | Get single emailtemplatefile |
| `nexudus emailtemplatefiles create --business-id <value> --language <value> --name <value> --subject <value> --agent` | Create emailtemplatefile |
| `nexudus emailtemplatefiles update <id> --name "New Name" --agent` | Update emailtemplatefile |
| `nexudus emailtemplatefiles delete <id> --yes --agent` | Delete emailtemplatefile (no prompt) |

#### EmailTemplateFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--language` | enum | The language value for this email template file |
| `--file-language-id` | long | ID of the file language linked to this record |
| `--name` | string | The name value for this email template file |
| `--subject` | string | The subject value for this email template file |
| `--file-contents` | string | The file contents value for this email template file |
| `--is-text-only` | bool | Whether is text only is enabled |
| `--from-name` | string | The from name value for this email template file |
| `--from-email` | string | The from email value for this email template file |
| `--c-c-email` | string | The cc email value for this email template file |
| `--c-c-o-email` | string | The cco email value for this email template file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EmailTemplateFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--language` | enum, required | The language value for this email template file |
| `--file-language-id` | long | ID of the file language linked to this record |
| `--name` | string, required | The name value for this email template file |
| `--subject` | string, required | The subject value for this email template file |
| `--file-contents` | string | The file contents value for this email template file |
| `--is-text-only` | bool | Whether is text only is enabled |
| `--from-name` | string | The from name value for this email template file |
| `--from-email` | string | The from email value for this email template file |
| `--c-c-email` | string | The cc email value for this email template file |
| `--c-c-o-email` | string | The cco email value for this email template file |

#### EmailTemplateFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--language` | enum | The language value for this email template file |
| `--file-language-id` | long | ID of the file language linked to this record |
| `--name` | string | The name value for this email template file |
| `--subject` | string | The subject value for this email template file |
| `--file-contents` | string | The file contents value for this email template file |
| `--is-text-only` | bool | Whether is text only is enabled |
| `--from-name` | string | The from name value for this email template file |
| `--from-email` | string | The from email value for this email template file |
| `--c-c-email` | string | The cc email value for this email template file |
| `--c-c-o-email` | string | The cco email value for this email template file |

#### EmailTemplateFile PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--from-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--c-c-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--c-c-o-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus emailtemplatefiles update <id> --from-email "«PII:EMAIL:a3f2b1c9»" --agent`

#### EmailTemplateFile enum values

| Option | Valid values |
| ------ | ------------ |
| `--language` | `1` EnglishUS, `2` Spanish, `3` EnglishUK |

<!-- END:GENERATED entity=EmailTemplateFiles -->
