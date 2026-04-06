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

`--business-id`, `--display-name`, `--email-address`, `--active`, `--send-notification-on-new-messages`, `--notification-email-address`, `--incoming-server`, `--incoming-server-type`, `--incoming-server-port`, `--from-incoming-server-port` (range), `--to-incoming-server-port` (range), `--incoming-server-s-s-l`, `--incoming-server-username`, `--delete-message-settings`, `--outgoing-server`, `--outgoing-server-port`, `--from-outgoing-server-port` (range), `--to-outgoing-server-port` (range), `--outgoing-server-s-s-l`, `--outgoing-server-username`, `--reply-to-email`, `--last-check-time`, `--from-last-check-time` (range), `--to-last-check-time` (range), `--last-message-id`, `--from-last-message-id` (range), `--to-last-message-id` (range), `--error-count`, `--from-error-count` (range), `--to-error-count` (range), `--google-access-token`, `--office365-access-token`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### EmailAccount create options

`--business-id` (required), `--display-name` (required), `--email-address` (required), `--active`, `--send-notification-on-new-messages`, `--notification-email-address`, `--incoming-server` (required), `--incoming-server-type` (required), `--incoming-server-port` (required), `--incoming-server-s-s-l`, `--incoming-server-username` (required), `--delete-message-settings` (required), `--outgoing-server` (required), `--outgoing-server-port` (required), `--outgoing-server-s-s-l`, `--outgoing-server-username` (required), `--reply-to-email`, `--last-check-time`, `--last-message-id` (required), `--error-count` (required), `--google-access-token`, `--office365-access-token`

#### EmailAccount update options

`--business-id`, `--display-name`, `--email-address`, `--active`, `--send-notification-on-new-messages`, `--notification-email-address`, `--incoming-server`, `--incoming-server-type`, `--incoming-server-port`, `--incoming-server-s-s-l`, `--incoming-server-username`, `--delete-message-settings`, `--outgoing-server`, `--outgoing-server-port`, `--outgoing-server-s-s-l`, `--outgoing-server-username`, `--reply-to-email`, `--last-check-time`, `--last-message-id`, `--error-count`, `--google-access-token`, `--office365-access-token`

<!-- END:GENERATED entity=EmailAccounts -->
