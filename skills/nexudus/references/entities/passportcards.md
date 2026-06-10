# PassportCards

<!-- BEGIN:GENERATED entity=PassportCards -->

A **PassportCard** represents a customer's public profile card displayed on the Nexudus Passport network. Passport cards show member information across participating locations to foster community and networking.

PassportCards support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus passportcards list --agent` | List all passportcards |
| `nexudus passportcards list --id <id> --agent` | Filter by single ID |
| `nexudus passportcards list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus passportcards list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus passportcards list --code <value> --active <value> --agent` | Filter passportcards by properties |
| `nexudus passportcards list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus passportcards list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus passportcards get <id> --agent` | Get single passportcard |
| `nexudus passportcards create --code <value> --agent` | Create passportcard |
| `nexudus passportcards update <id> --name "New Name" --agent` | Update passportcard |
| `nexudus passportcards delete <id> --yes --agent` | Delete passportcard (no prompt) |

#### PassportCard list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--code` | string | The code value for this passport card |
| `--active` | bool | Whether this passport card is currently active |
| `--notes` | string | Optional notes or comments about this passport card |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### PassportCard sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### PassportCard create options

| Option | Type | Description |
| --- | --- | --- |
| `--code` | string, required | The code value for this passport card |
| `--active` | bool | Whether this passport card is currently active |
| `--notes` | string | Optional notes or comments about this passport card |

#### PassportCard update options

| Option | Type | Description |
| --- | --- | --- |
| `--code` | string | The code value for this passport card |
| `--active` | bool | Whether this passport card is currently active |
| `--notes` | string | Optional notes or comments about this passport card |

#### PassportCard PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus passportcards update <id> --notes "«PII:BIO:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=PassportCards -->
