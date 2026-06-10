# NewsLetters

<!-- BEGIN:GENERATED entity=NewsLetters -->

A **NewsLetter** represents an email newsletter that can be sent to subscribers. Each newsletter has content, a subject line, and can target specific subscriber groups or segments.

NewsLetters support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus newsletters list --agent` | List all newsletters |
| `nexudus newsletters list --id <id> --agent` | Filter by single ID |
| `nexudus newsletters list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus newsletters list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus newsletters list --business-id <value> --name <value> --agent` | Filter newsletters by properties |
| `nexudus newsletters list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus newsletters list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus newsletters get <id> --agent` | Get single newsletter |
| `nexudus newsletters create --business-id <value> --name <value> --language <value> --agent` | Create newsletter |
| `nexudus newsletters update <id> --name "New Name" --agent` | Update newsletter |
| `nexudus newsletters delete <id> --yes --agent` | Delete newsletter (no prompt) |

#### NewsLetter list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this news letter |
| `--last-sent` | DateTime | Date/time value for last sent |
| `--from-last-sent` | range | |
| `--to-last-sent` | range | |
| `--language` | enum | The language value for this news letter |
| `--news-letter-contents` | string | The news letter contents value for this news letter |
| `--news-letter-design` | string | The news letter design value for this news letter |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### NewsLetter sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### NewsLetter create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this news letter |
| `--last-sent` | DateTime | Date/time value for last sent |
| `--language` | enum, required | The language value for this news letter |
| `--news-letter-contents` | string | The news letter contents value for this news letter |
| `--news-letter-design` | string | The news letter design value for this news letter |

#### NewsLetter update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this news letter |
| `--last-sent` | DateTime | Date/time value for last sent |
| `--language` | enum | The language value for this news letter |
| `--news-letter-contents` | string | The news letter contents value for this news letter |
| `--news-letter-design` | string | The news letter design value for this news letter |

#### NewsLetter enum values

| Option | Valid values |
| ------ | ------------ |
| `--language` | `1` EnglishUS, `2` Spanish, `3` EnglishUK |

<!-- END:GENERATED entity=NewsLetters -->
