# EmailAccounts

<!-- BEGIN:GENERATED entity=EmailAccounts -->

EmailAccounts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus emailaccounts list --agent` | List all emailaccounts |
| `nexudus emailaccounts list --id <id> --agent` | Filter by single ID |
| `nexudus emailaccounts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus emailaccounts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus emailaccounts list --business-id <value> --display-name <value> --agent` | Filter emailaccounts by properties |
| `nexudus emailaccounts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus emailaccounts get <id> --agent` | Get single emailaccount |
| `nexudus emailaccounts create --business-id <value> --display-name <value> --email-address <value> --incoming-server <value> --incoming-server-type <value> --incoming-server-port <value> --incoming-server-username <value> --delete-message-settings <value> --outgoing-server <value> --outgoing-server-port <value> --outgoing-server-username <value> --last-message-id <value> --error-count <value> --agent` | Create emailaccount |
| `nexudus emailaccounts update <id> --name "New Name" --agent` | Update emailaccount |
| `nexudus emailaccounts delete <id> --yes --agent` | Delete emailaccount (no prompt) |

#### EmailAccount list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--display-name` | string |  |
| `--email-address` | string |  |
| `--active` | bool |  |
| `--send-notification-on-new-messages` | bool |  |
| `--notification-email-address` | string |  |
| `--incoming-server` | string |  |
| `--incoming-server-type` | enum |  |
| `--incoming-server-port` | int |  |
| `--from-incoming-server-port` | range | |
| `--to-incoming-server-port` | range | |
| `--incoming-server-s-s-l` | bool |  |
| `--incoming-server-username` | string |  |
| `--delete-message-settings` | enum |  |
| `--outgoing-server` | string |  |
| `--outgoing-server-port` | int |  |
| `--from-outgoing-server-port` | range | |
| `--to-outgoing-server-port` | range | |
| `--outgoing-server-s-s-l` | bool |  |
| `--outgoing-server-username` | string |  |
| `--reply-to-email` | string |  |
| `--last-check-time` | DateTime |  |
| `--from-last-check-time` | range | |
| `--to-last-check-time` | range | |
| `--last-message-id` | int |  |
| `--from-last-message-id` | range | |
| `--to-last-message-id` | range | |
| `--error-count` | int |  |
| `--from-error-count` | range | |
| `--to-error-count` | range | |
| `--google-access-token` | string |  |
| `--office365-access-token` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EmailAccount create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--display-name` | string, required |  |
| `--email-address` | string, required |  |
| `--active` | bool |  |
| `--send-notification-on-new-messages` | bool |  |
| `--notification-email-address` | string |  |
| `--incoming-server` | string, required |  |
| `--incoming-server-type` | enum, required |  |
| `--incoming-server-port` | int, required |  |
| `--incoming-server-s-s-l` | bool |  |
| `--incoming-server-username` | string, required |  |
| `--delete-message-settings` | enum, required |  |
| `--outgoing-server` | string, required |  |
| `--outgoing-server-port` | int, required |  |
| `--outgoing-server-s-s-l` | bool |  |
| `--outgoing-server-username` | string, required |  |
| `--reply-to-email` | string |  |
| `--last-check-time` | DateTime |  |
| `--last-message-id` | int, required |  |
| `--error-count` | int, required |  |
| `--google-access-token` | string |  |
| `--office365-access-token` | string |  |

#### EmailAccount update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--display-name` | string |  |
| `--email-address` | string |  |
| `--active` | bool |  |
| `--send-notification-on-new-messages` | bool |  |
| `--notification-email-address` | string |  |
| `--incoming-server` | string |  |
| `--incoming-server-type` | enum |  |
| `--incoming-server-port` | int |  |
| `--incoming-server-s-s-l` | bool |  |
| `--incoming-server-username` | string |  |
| `--delete-message-settings` | enum |  |
| `--outgoing-server` | string |  |
| `--outgoing-server-port` | int |  |
| `--outgoing-server-s-s-l` | bool |  |
| `--outgoing-server-username` | string |  |
| `--reply-to-email` | string |  |
| `--last-check-time` | DateTime |  |
| `--last-message-id` | int |  |
| `--error-count` | int |  |
| `--google-access-token` | string |  |
| `--office365-access-token` | string |  |

#### EmailAccount PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--reply-to-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus emailaccounts update <id> --reply-to-email "«PII:EMAIL:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=EmailAccounts -->
