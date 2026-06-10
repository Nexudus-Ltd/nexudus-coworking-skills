# EmailAccounts

<!-- BEGIN:GENERATED entity=EmailAccounts -->

An **EmailAccount** configures an incoming email connection (IMAP) used to receive messages for the help desk or other automated workflows. Each account specifies server connection details, credentials, and message handling policies.

EmailAccounts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus emailaccounts list --agent` | List all emailaccounts |
| `nexudus emailaccounts list --id <id> --agent` | Filter by single ID |
| `nexudus emailaccounts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus emailaccounts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus emailaccounts list --business-id <value> --display-name <value> --agent` | Filter emailaccounts by properties |
| `nexudus emailaccounts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus emailaccounts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus emailaccounts get <id> --agent` | Get single emailaccount |
| `nexudus emailaccounts create --business-id <value> --display-name <value> --email-address <value> --incoming-server <value> --incoming-server-type <value> --incoming-server-port <value> --incoming-server-username <value> --delete-message-settings <value> --outgoing-server <value> --outgoing-server-port <value> --outgoing-server-username <value> --last-message-id <value> --error-count <value> --agent` | Create emailaccount |
| `nexudus emailaccounts update <id> --name "New Name" --agent` | Update emailaccount |
| `nexudus emailaccounts delete <id> --yes --agent` | Delete emailaccount (no prompt) |

#### EmailAccount list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--display-name` | string | The display name value for this email account |
| `--email-address` | string | The email address value for this email account |
| `--active` | bool | Whether this email account is currently active |
| `--send-notification-on-new-messages` | bool | Whether send notification on new messages is enabled |
| `--notification-email-address` | string | The notification email address value for this email account |
| `--incoming-server` | string | The incoming server value for this email account |
| `--incoming-server-type` | enum | The incoming server type value for this email account |
| `--incoming-server-port` | int | The incoming server port value for this email account |
| `--from-incoming-server-port` | range | |
| `--to-incoming-server-port` | range | |
| `--incoming-server-s-s-l` | bool | Whether incoming server ssl is enabled |
| `--incoming-server-username` | string | The incoming server username value for this email account |
| `--delete-message-settings` | enum | The delete message settings value for this email account |
| `--outgoing-server` | string | The outgoing server value for this email account |
| `--outgoing-server-port` | int | The outgoing server port value for this email account |
| `--from-outgoing-server-port` | range | |
| `--to-outgoing-server-port` | range | |
| `--outgoing-server-s-s-l` | bool | Whether outgoing server ssl is enabled |
| `--outgoing-server-username` | string | The outgoing server username value for this email account |
| `--reply-to-email` | string | The reply to email value for this email account |
| `--last-check-time` | DateTime | Date/time value for last check time |
| `--from-last-check-time` | range | |
| `--to-last-check-time` | range | |
| `--last-message-id` | int | ID of the last message associated with this record |
| `--from-last-message-id` | range | |
| `--to-last-message-id` | range | |
| `--error-count` | int | The error count value for this email account |
| `--from-error-count` | range | |
| `--to-error-count` | range | |
| `--google-access-token` | string | The google access token value for this email account |
| `--office365-access-token` | string | The office365 access token value for this email account |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EmailAccount sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### EmailAccount create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--display-name` | string, required | The display name value for this email account |
| `--email-address` | string, required | The email address value for this email account |
| `--active` | bool | Whether this email account is currently active |
| `--send-notification-on-new-messages` | bool | Whether send notification on new messages is enabled |
| `--notification-email-address` | string | The notification email address value for this email account |
| `--incoming-server` | string, required | The incoming server value for this email account |
| `--incoming-server-type` | enum, required | The incoming server type value for this email account |
| `--incoming-server-port` | int, required | The incoming server port value for this email account |
| `--incoming-server-s-s-l` | bool | Whether incoming server ssl is enabled |
| `--incoming-server-username` | string, required | The incoming server username value for this email account |
| `--delete-message-settings` | enum, required | The delete message settings value for this email account |
| `--outgoing-server` | string, required | The outgoing server value for this email account |
| `--outgoing-server-port` | int, required | The outgoing server port value for this email account |
| `--outgoing-server-s-s-l` | bool | Whether outgoing server ssl is enabled |
| `--outgoing-server-username` | string, required | The outgoing server username value for this email account |
| `--reply-to-email` | string | The reply to email value for this email account |
| `--last-check-time` | DateTime | Date/time value for last check time |
| `--last-message-id` | int, required | ID of the last message associated with this record |
| `--error-count` | int, required | The error count value for this email account |
| `--google-access-token` | string | The google access token value for this email account |
| `--office365-access-token` | string | The office365 access token value for this email account |

#### EmailAccount update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--display-name` | string | The display name value for this email account |
| `--email-address` | string | The email address value for this email account |
| `--active` | bool | Whether this email account is currently active |
| `--send-notification-on-new-messages` | bool | Whether send notification on new messages is enabled |
| `--notification-email-address` | string | The notification email address value for this email account |
| `--incoming-server` | string | The incoming server value for this email account |
| `--incoming-server-type` | enum | The incoming server type value for this email account |
| `--incoming-server-port` | int | The incoming server port value for this email account |
| `--incoming-server-s-s-l` | bool | Whether incoming server ssl is enabled |
| `--incoming-server-username` | string | The incoming server username value for this email account |
| `--delete-message-settings` | enum | The delete message settings value for this email account |
| `--outgoing-server` | string | The outgoing server value for this email account |
| `--outgoing-server-port` | int | The outgoing server port value for this email account |
| `--outgoing-server-s-s-l` | bool | Whether outgoing server ssl is enabled |
| `--outgoing-server-username` | string | The outgoing server username value for this email account |
| `--reply-to-email` | string | The reply to email value for this email account |
| `--last-check-time` | DateTime | Date/time value for last check time |
| `--last-message-id` | int | ID of the last message associated with this record |
| `--error-count` | int | The error count value for this email account |
| `--google-access-token` | string | The google access token value for this email account |
| `--office365-access-token` | string | The office365 access token value for this email account |

#### EmailAccount PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--reply-to-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus emailaccounts update <id> --reply-to-email "«PII:EMAIL:a3f2b1c9»" --agent`

#### EmailAccount enum values

| Option | Valid values |
| ------ | ------------ |
| `--incoming-server-type` | `1` Imap |
| `--delete-message-settings` | `1` DontDelete, `2` DeleteOnReceive, `3` DeleteWhenDeleting |

<!-- END:GENERATED entity=EmailAccounts -->
