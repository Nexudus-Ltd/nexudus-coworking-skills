# NewsLetterSubscribers

<!-- BEGIN:GENERATED entity=NewsLetterSubscribers -->

NewsLetterSubscribers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus newslettersubscribers list --agent` | List all newslettersubscribers |
| `nexudus newslettersubscribers list --id <id> --agent` | Filter by single ID |
| `nexudus newslettersubscribers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus newslettersubscribers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus newslettersubscribers list --business-id <value> --name <value> --agent` | Filter newslettersubscribers by properties |
| `nexudus newslettersubscribers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus newslettersubscribers get <id> --agent` | Get single newslettersubscriber |
| `nexudus newslettersubscribers create --business-id <value> --name <value> --email <value> --agent` | Create newslettersubscriber |
| `nexudus newslettersubscribers update <id> --name "New Name" --agent` | Update newslettersubscriber |
| `nexudus newslettersubscribers delete <id> --yes --agent` | Delete newslettersubscriber (no prompt) |

#### NewsLetterSubscriber list filter options

`--business-id`, `--name`, `--company-name`, `--language`, `--email`, `--visit-reason`, `--active`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### NewsLetterSubscriber create options

`--business-id` (required), `--name` (required), `--company-name`, `--language`, `--email` (required), `--visit-reason`, `--active`, `--groups` (list, repeat flag), `--added-groups` (list, repeat flag), `--removed-groups` (list, repeat flag)

#### NewsLetterSubscriber update options

`--business-id`, `--name`, `--company-name`, `--language`, `--email`, `--visit-reason`, `--active`, `--groups` (list, repeat flag), `--added-groups` (list, repeat flag), `--removed-groups` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Groups`, `AddedGroups`, `RemovedGroups`

<!-- END:GENERATED entity=NewsLetterSubscribers -->
