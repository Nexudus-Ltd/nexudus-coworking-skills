# LanguageTokens

<!-- BEGIN:GENERATED entity=LanguageTokens -->

A language token is a location-specific translation of a Members Portal text key for one language, with optional HTML formatting.

LanguageTokens support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus languagetokens list --agent` | List all languagetokens |
| `nexudus languagetokens list --id <id> --agent` | Filter by single ID |
| `nexudus languagetokens list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus languagetokens list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus languagetokens list --language-id <value> --name <value> --agent` | Filter languagetokens by properties |
| `nexudus languagetokens list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus languagetokens list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus languagetokens get <id> --agent` | Get single languagetoken |
| `nexudus languagetokens create --language-id <value> --name <value> --agent` | Create languagetoken |
| `nexudus languagetokens update <id> --name "New Name" --agent` | Update languagetoken |
| `nexudus languagetokens delete <id> --yes --agent` | Delete languagetoken (no prompt) |

#### LanguageToken list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--language-id` | long | ID of the language that owns this translation; its location determines access to the token |
| `--name` | string | Required unique token key within the selected language; this is the source text or identifier requested by the Members Portal |
| `--value` | string | Optional translated rich-text value displayed in the Members Portal; HTML markup is supported |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### LanguageToken sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### LanguageToken create options

| Option | Type | Description |
| --- | --- | --- |
| `--language-id` | long, required | ID of the language that owns this translation; its location determines access to the token |
| `--name` | string, required | Required unique token key within the selected language; this is the source text or identifier requested by the Members Portal |
| `--value` | string | Optional translated rich-text value displayed in the Members Portal; HTML markup is supported |

#### LanguageToken update options

| Option | Type | Description |
| --- | --- | --- |
| `--language-id` | long | ID of the language that owns this translation; its location determines access to the token |
| `--name` | string | Required unique token key within the selected language; this is the source text or identifier requested by the Members Portal |
| `--value` | string | Optional translated rich-text value displayed in the Members Portal; HTML markup is supported |

<!-- END:GENERATED entity=LanguageTokens -->
