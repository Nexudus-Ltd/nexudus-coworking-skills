# NewsLetters

<!-- BEGIN:GENERATED entity=NewsLetters -->

A newsletter is a location-scoped email campaign with a subject and HTML body, sent through a separate command to active subscribers in the selected language.

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
| `--business-id` | long | ID of the location that owns this newsletter. |
| `--name` | string | Email subject line shown to newsletter recipients. |
| `--last-sent` | DateTime | UTC date and time when a newsletter send was last initiated; set by the send command. |
| `--from-last-sent` | range | |
| `--to-last-sent` | range | |
| `--language` | enum | Language edition and recipient-language filter: EnglishUS, Spanish, or EnglishUK. |
| `--news-letter-contents` | string | HTML email body; sending adds unsubscribe and engagement-tracking links and replaces supported recipient tokens. |
| `--news-letter-design` | string | Optional newsletter design data; current send processing uses NewsLetterContents as the email body. |
| `--clicks` | int | Read-only count of tracked recipient link-click activities for this newsletter. |
| `--from-clicks` | range | |
| `--to-clicks` | range | |
| `--opens` | int | Read-only count of tracked recipient open activities for this newsletter. |
| `--from-opens` | range | |
| `--to-opens` | range | |
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
| `--business-id` | long, required | ID of the location that owns this newsletter. |
| `--name` | string, required | Email subject line shown to newsletter recipients. |
| `--language` | enum, required | Language edition and recipient-language filter: EnglishUS, Spanish, or EnglishUK. |
| `--news-letter-contents` | string | HTML email body; sending adds unsubscribe and engagement-tracking links and replaces supported recipient tokens. |
| `--news-letter-design` | string | Optional newsletter design data; current send processing uses NewsLetterContents as the email body. |

#### NewsLetter update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this newsletter. |
| `--name` | string | Email subject line shown to newsletter recipients. |
| `--language` | enum | Language edition and recipient-language filter: EnglishUS, Spanish, or EnglishUK. |
| `--news-letter-contents` | string | HTML email body; sending adds unsubscribe and engagement-tracking links and replaces supported recipient tokens. |
| `--news-letter-design` | string | Optional newsletter design data; current send processing uses NewsLetterContents as the email body. |

#### NewsLetter enum values

| Option | Valid values |
| ------ | ------------ |
| `--language` | `1` EnglishUS, `2` Spanish, `3` EnglishUK |

<!-- END:GENERATED entity=NewsLetters -->
