# NewsLetters

<!-- BEGIN:GENERATED entity=NewsLetters -->

NewsLetters support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus newsletters list --agent` | List all newsletters |
| `nexudus newsletters list --id <id> --agent` | Filter by single ID |
| `nexudus newsletters list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus newsletters list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus newsletters list --business-id <value> --name <value> --agent` | Filter newsletters by properties |
| `nexudus newsletters list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus newsletters get <id> --agent` | Get single newsletter |
| `nexudus newsletters create --business-id <value> --name <value> --agent` | Create newsletter |
| `nexudus newsletters update <id> --name "New Name" --agent` | Update newsletter |
| `nexudus newsletters delete <id> --yes --agent` | Delete newsletter (no prompt) |

#### NewsLetter list filter options

`--business-id`, `--name`, `--last-sent`, `--from-last-sent` (range), `--to-last-sent` (range), `--language`, `--news-letter-contents`, `--news-letter-design`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### NewsLetter create options

`--business-id` (required), `--name` (required), `--last-sent`, `--language`, `--news-letter-contents`, `--news-letter-design`

#### NewsLetter update options

`--business-id`, `--name`, `--last-sent`, `--language`, `--news-letter-contents`, `--news-letter-design`

<!-- END:GENERATED entity=NewsLetters -->
