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

`--business-id` (long), `--display-name`, `--email-address`, `--active` (bool), `--send-notification-on-new-messages` (bool), `--notification-email-address`, `--incoming-server`, `--incoming-server-type` (enum), `--incoming-server-port` (int), `--from-incoming-server-port` (range), `--to-incoming-server-port` (range), `--incoming-server-s-s-l` (bool), `--incoming-server-username`, `--delete-message-settings` (enum), `--outgoing-server`, `--outgoing-server-port` (int), `--from-outgoing-server-port` (range), `--to-outgoing-server-port` (range), `--outgoing-server-s-s-l` (bool), `--outgoing-server-username`, `--reply-to-email`, `--last-check-time` (DateTime), `--from-last-check-time` (range), `--to-last-check-time` (range), `--last-message-id` (int), `--from-last-message-id` (range), `--to-last-message-id` (range), `--error-count` (int), `--from-error-count` (range), `--to-error-count` (range), `--google-access-token`, `--office365-access-token`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### EmailAccount create options

`--business-id` (long, required), `--display-name` (required), `--email-address` (required), `--active` (bool), `--send-notification-on-new-messages` (bool), `--notification-email-address`, `--incoming-server` (required), `--incoming-server-type` (enum, required), `--incoming-server-port` (int, required), `--incoming-server-s-s-l` (bool), `--incoming-server-username` (required), `--delete-message-settings` (enum, required), `--outgoing-server` (required), `--outgoing-server-port` (int, required), `--outgoing-server-s-s-l` (bool), `--outgoing-server-username` (required), `--reply-to-email`, `--last-check-time` (DateTime), `--last-message-id` (int, required), `--error-count` (int, required), `--google-access-token`, `--office365-access-token`

#### EmailAccount update options

`--business-id` (long), `--display-name`, `--email-address`, `--active` (bool), `--send-notification-on-new-messages` (bool), `--notification-email-address`, `--incoming-server`, `--incoming-server-type` (enum), `--incoming-server-port` (int), `--incoming-server-s-s-l` (bool), `--incoming-server-username`, `--delete-message-settings` (enum), `--outgoing-server`, `--outgoing-server-port` (int), `--outgoing-server-s-s-l` (bool), `--outgoing-server-username`, `--reply-to-email`, `--last-check-time` (DateTime), `--last-message-id` (int), `--error-count` (int), `--google-access-token`, `--office365-access-token`

<!-- END:GENERATED entity=EmailAccounts -->
