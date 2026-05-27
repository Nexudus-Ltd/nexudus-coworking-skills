# LanguageTokens

<!-- BEGIN:GENERATED entity=LanguageTokens -->

A **LanguageToken** represents a translatable text string in the system. Each token has a key and a translated value for a specific language, enabling full localisation of the platform.

LanguageTokens support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus languagetokens list --agent` | List all languagetokens |
| `nexudus languagetokens list --id <id> --agent` | Filter by single ID |
| `nexudus languagetokens list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus languagetokens list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus languagetokens list --language-id <value> --name <value> --agent` | Filter languagetokens by properties |
| `nexudus languagetokens list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus languagetokens get <id> --agent` | Get single languagetoken |
| `nexudus languagetokens create --language-id <value> --name <value> --agent` | Create languagetoken |
| `nexudus languagetokens update <id> --name "New Name" --agent` | Update languagetoken |
| `nexudus languagetokens delete <id> --yes --agent` | Delete languagetoken (no prompt) |

#### LanguageToken list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--language-id` | long | ID of the language linked to this record |
| `--name` | string | The name value for this language token |
| `--value` | string | The value value for this language token |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### LanguageToken create options

| Option | Type | Description |
| --- | --- | --- |
| `--language-id` | long, required | ID of the language linked to this record |
| `--name` | string, required | The name value for this language token |
| `--value` | string | The value value for this language token |

#### LanguageToken update options

| Option | Type | Description |
| --- | --- | --- |
| `--language-id` | long | ID of the language linked to this record |
| `--name` | string | The name value for this language token |
| `--value` | string | The value value for this language token |

<!-- END:GENERATED entity=LanguageTokens -->
