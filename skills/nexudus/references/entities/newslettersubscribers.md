# NewsLetterSubscribers

<!-- BEGIN:GENERATED entity=NewsLetterSubscribers -->

A **NewsLetterSubscriber** represents a person subscribed to receive newsletters. Subscribers can be customers, leads, or external contacts and have a preferred language for communications.

NewsLetterSubscribers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus newslettersubscribers list --agent` | List all newslettersubscribers |
| `nexudus newslettersubscribers list --id <id> --agent` | Filter by single ID |
| `nexudus newslettersubscribers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus newslettersubscribers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus newslettersubscribers list --business-id <value> --name <value> --agent` | Filter newslettersubscribers by properties |
| `nexudus newslettersubscribers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus newslettersubscribers list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus newslettersubscribers get <id> --agent` | Get single newslettersubscriber |
| `nexudus newslettersubscribers create --business-id <value> --name <value> --language <value> --email <value> --agent` | Create newslettersubscriber |
| `nexudus newslettersubscribers update <id> --name "New Name" --agent` | Update newslettersubscriber |
| `nexudus newslettersubscribers delete <id> --yes --agent` | Delete newslettersubscriber (no prompt) |

#### NewsLetterSubscriber list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this news letter subscriber |
| `--company-name` | string | The company name value for this news letter subscriber |
| `--language` | enum | The language value for this news letter subscriber |
| `--email` | string | The email value for this news letter subscriber |
| `--visit-reason` | string | The visit reason value for this news letter subscriber |
| `--active` | bool | Whether this news letter subscriber is currently active |
| `--viewed` | bool | Whether viewed is enabled |
| `--clicked` | bool | Whether clicked is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### NewsLetterSubscriber sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### NewsLetterSubscriber create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this news letter subscriber |
| `--company-name` | string | The company name value for this news letter subscriber |
| `--language` | enum, required | The language value for this news letter subscriber |
| `--email` | string, required | The email value for this news letter subscriber |
| `--visit-reason` | string | The visit reason value for this news letter subscriber |
| `--active` | bool | Whether this news letter subscriber is currently active |
| `--groups` | list, repeat flag | List of groups linked to this record |
| `--added-groups` | list, repeat flag | The added groups value for this news letter subscriber |
| `--removed-groups` | list, repeat flag | The removed groups value for this news letter subscriber |

#### NewsLetterSubscriber update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this news letter subscriber |
| `--company-name` | string | The company name value for this news letter subscriber |
| `--language` | enum | The language value for this news letter subscriber |
| `--email` | string | The email value for this news letter subscriber |
| `--visit-reason` | string | The visit reason value for this news letter subscriber |
| `--active` | bool | Whether this news letter subscriber is currently active |
| `--groups` | list, repeat flag | List of groups linked to this record |
| `--added-groups` | list, repeat flag | The added groups value for this news letter subscriber |
| `--removed-groups` | list, repeat flag | The removed groups value for this news letter subscriber |

#### NewsLetterSubscriber PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus newslettersubscribers update <id> --company-name "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `Groups`, `AddedGroups`, `RemovedGroups`

#### NewsLetterSubscriber enum values

| Option | Valid values |
| ------ | ------------ |
| `--language` | `1` EnglishUS, `2` Spanish, `3` EnglishUK |

<!-- END:GENERATED entity=NewsLetterSubscribers -->
