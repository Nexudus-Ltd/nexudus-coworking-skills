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
| `nexudus newslettersubscribers create --business-id <value> --name <value> --language <value> --email <value> --agent` | Create newslettersubscriber |
| `nexudus newslettersubscribers update <id> --name "New Name" --agent` | Update newslettersubscriber |
| `nexudus newslettersubscribers delete <id> --yes --agent` | Delete newslettersubscriber (no prompt) |

#### NewsLetterSubscriber list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--company-name` | string |  |
| `--language` | enum |  |
| `--email` | string |  |
| `--visit-reason` | string |  |
| `--active` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### NewsLetterSubscriber create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required |  |
| `--company-name` | string |  |
| `--language` | enum, required |  |
| `--email` | string, required |  |
| `--visit-reason` | string |  |
| `--active` | bool |  |
| `--groups` | list, repeat flag |  |
| `--added-groups` | list, repeat flag |  |
| `--removed-groups` | list, repeat flag |  |

#### NewsLetterSubscriber update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--company-name` | string |  |
| `--language` | enum |  |
| `--email` | string |  |
| `--visit-reason` | string |  |
| `--active` | bool |  |
| `--groups` | list, repeat flag |  |
| `--added-groups` | list, repeat flag |  |
| `--removed-groups` | list, repeat flag |  |

#### NewsLetterSubscriber PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus newslettersubscribers update <id> --company-name "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `Groups`, `AddedGroups`, `RemovedGroups`

<!-- END:GENERATED entity=NewsLetterSubscribers -->
