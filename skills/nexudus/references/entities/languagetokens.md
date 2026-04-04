# LanguageTokens

<!-- BEGIN:GENERATED entity=LanguageTokens -->

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

`--language-id`, `--name`, `--value`

#### LanguageToken create options

`--language-id` (required), `--name` (required), `--value`

#### LanguageToken update options

`--language-id`, `--name`, `--value`

<!-- END:GENERATED entity=LanguageTokens -->
