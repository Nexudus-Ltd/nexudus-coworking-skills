# EmailTemplateFiles

<!-- BEGIN:GENERATED entity=EmailTemplateFiles -->

An email template override defines the subject, body, and optional sender or copy recipients for an automated message at one location in one configured language; built-in files are used when no override is saved.

EmailTemplateFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus emailtemplatefiles list --agent` | List all emailtemplatefiles |
| `nexudus emailtemplatefiles list --id <id> --agent` | Filter by single ID |
| `nexudus emailtemplatefiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus emailtemplatefiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus emailtemplatefiles list --business-id <value> --file-language-id <value> --agent` | Filter emailtemplatefiles by properties |
| `nexudus emailtemplatefiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus emailtemplatefiles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus emailtemplatefiles get <id> --agent` | Get single emailtemplatefile |
| `nexudus emailtemplatefiles create --business-id <value> --name <value> --subject <value> --agent` | Create emailtemplatefile |
| `nexudus emailtemplatefiles update <id> --name "New Name" --agent` | Update emailtemplatefile |
| `nexudus emailtemplatefiles delete <id> --yes --agent` | Delete emailtemplatefile (no prompt) |

#### EmailTemplateFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location whose automated email template this record overrides. |
| `--file-language-id` | long | ID of the configured location language for this template override; together with Name and Business it identifies the saved template. |
| `--name` | string | Built-in email message identifier this record overrides, such as the identifier for a welcome, invoice, booking confirmation, or reminder email; required and limited to 254 characters. |
| `--subject` | string | Required email subject line, up to 254 characters; supported message tokens are replaced before the email is queued. |
| `--file-contents` | string | Email body content for this location and language; supported message tokens are replaced before the email is queued. |
| `--editor-design` | string | Optional Unlayer design JSON used to continue visual editing; FileContents remains the exported HTML used for delivery. |
| `--is-text-only` | bool | Whether this template is marked as text-only; the current message dispatch path stores and transfers this flag without using it to transform the body. |
| `--from-name` | string | Optional sender display name passed to email delivery, limited to 254 characters. |
| `--from-email` | string | Optional sender email address passed to email delivery, limited to 254 characters. |
| `--c-c-email` | string | Optional carbon-copy recipient email address passed to email delivery, limited to 254 characters. |
| `--c-c-o-email` | string | Optional blind-carbon-copy recipient email address passed to email delivery, limited to 254 characters. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EmailTemplateFile sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### EmailTemplateFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location whose automated email template this record overrides. |
| `--file-language-id` | long | ID of the configured location language for this template override; together with Name and Business it identifies the saved template. |
| `--name` | string, required | Built-in email message identifier this record overrides, such as the identifier for a welcome, invoice, booking confirmation, or reminder email; required and limited to 254 characters. |
| `--subject` | string, required | Required email subject line, up to 254 characters; supported message tokens are replaced before the email is queued. |
| `--file-contents` | string | Email body content for this location and language; supported message tokens are replaced before the email is queued. |
| `--editor-design` | string | Optional Unlayer design JSON used to continue visual editing; FileContents remains the exported HTML used for delivery. |
| `--is-text-only` | bool | Whether this template is marked as text-only; the current message dispatch path stores and transfers this flag without using it to transform the body. |
| `--from-name` | string | Optional sender display name passed to email delivery, limited to 254 characters. |
| `--from-email` | string | Optional sender email address passed to email delivery, limited to 254 characters. |
| `--c-c-email` | string | Optional carbon-copy recipient email address passed to email delivery, limited to 254 characters. |
| `--c-c-o-email` | string | Optional blind-carbon-copy recipient email address passed to email delivery, limited to 254 characters. |

#### EmailTemplateFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location whose automated email template this record overrides. |
| `--file-language-id` | long | ID of the configured location language for this template override; together with Name and Business it identifies the saved template. |
| `--name` | string | Built-in email message identifier this record overrides, such as the identifier for a welcome, invoice, booking confirmation, or reminder email; required and limited to 254 characters. |
| `--subject` | string | Required email subject line, up to 254 characters; supported message tokens are replaced before the email is queued. |
| `--file-contents` | string | Email body content for this location and language; supported message tokens are replaced before the email is queued. |
| `--editor-design` | string | Optional Unlayer design JSON used to continue visual editing; FileContents remains the exported HTML used for delivery. |
| `--is-text-only` | bool | Whether this template is marked as text-only; the current message dispatch path stores and transfers this flag without using it to transform the body. |
| `--from-name` | string | Optional sender display name passed to email delivery, limited to 254 characters. |
| `--from-email` | string | Optional sender email address passed to email delivery, limited to 254 characters. |
| `--c-c-email` | string | Optional carbon-copy recipient email address passed to email delivery, limited to 254 characters. |
| `--c-c-o-email` | string | Optional blind-carbon-copy recipient email address passed to email delivery, limited to 254 characters. |

#### EmailTemplateFile PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--from-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--c-c-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--c-c-o-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus emailtemplatefiles update <id> --from-email "«PII:EMAIL:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=EmailTemplateFiles -->
