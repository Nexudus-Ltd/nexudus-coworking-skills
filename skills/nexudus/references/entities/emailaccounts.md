# EmailAccounts

<!-- BEGIN:GENERATED entity=EmailAccounts -->

An email account (EmailAccount) connects a location to an external mailbox: Nexudus reads it over IMAP about every 15 minutes and files inbound email against the matching customer as customer messages, and sends outgoing customer messages through its SMTP settings. Saving an account re-tests both connections, and the outgoing test sends a message to the account's own address.

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
| `nexudus emailaccounts create --business-id <value> --display-name <value> --email-address <value> --incoming-server <value> --incoming-server-type <value> --incoming-server-port <value> --incoming-server-username <value> --delete-message-settings <value> --outgoing-server <value> --outgoing-server-port <value> --outgoing-server-username <value> --error-count <value> --agent` | Create emailaccount |
| `nexudus emailaccounts update <id> --name "New Name" --agent` | Update emailaccount |
| `nexudus emailaccounts delete <id> --yes --agent` | Delete emailaccount (no prompt) |

#### EmailAccount list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this email account; it is supplied from the agent context. |
| `--display-name` | string | Account name shown to operators, and the sender display name on email sent through this account; required. |
| `--email-address` | string | Mailbox address this account connects to; it is the From and Reply-To address of email sent through the account, and it must be unique within the location. Required. |
| `--active` | bool | Whether the mailbox is polled for new messages; the background check runs about every 15 minutes and skips accounts in a suspended location, and the system switches this off by itself after repeated connection failures. |
| `--send-notification-on-new-messages` | bool | Whether a notification email is sent each time an inbound message is attached to a customer record through this account. |
| `--notification-email-address` | string | Address that receives those new-message notifications; it only applies while SendNotificationOnNewMessages is on, and when it is left empty the notifications go to EmailAddress instead. |
| `--incoming-server` | string | Host name of the IMAP server messages are read from, for example imap.gmail.com; required, and ignored on accounts connected through Google or Microsoft OAuth. |
| `--incoming-server-type` | enum | Protocol used to read the mailbox; Imap is the only supported value. |
| `--incoming-server-port` | int | TCP port of the IMAP server, normally 993 with SSL and 143 without; ignored on accounts connected through Google or Microsoft OAuth. |
| `--from-incoming-server-port` | range | |
| `--to-incoming-server-port` | range | |
| `--incoming-server-s-s-l` | bool | Whether the IMAP connection is made over SSL/TLS; ignored on accounts connected through Google or Microsoft OAuth. |
| `--incoming-server-username` | string | User name used to sign in to the IMAP server, usually the full mailbox address; required, stored encrypted, and ignored on accounts connected through Google or Microsoft OAuth. |
| `--delete-message-settings` | enum | What happens to a message left in the mailbox after Nexudus imports it: DontDelete leaves it in place, DeleteOnReceive removes it as soon as it is imported, and DeleteWhenDeleting removes it only when the matching customer message is deleted in Nexudus. |
| `--outgoing-server` | string | Host name of the SMTP server used to send email from this account, for example smtp.gmail.com; required. |
| `--outgoing-server-port` | int | TCP port of the SMTP server, normally 587 or 465. |
| `--from-outgoing-server-port` | range | |
| `--to-outgoing-server-port` | range | |
| `--outgoing-server-s-s-l` | bool | Whether the SMTP connection is made over SSL/TLS. |
| `--outgoing-server-username` | string | User name used to sign in to the SMTP server, usually the full mailbox address; required and stored encrypted. |
| `--last-check-time` | DateTime | UTC timestamp of the last time the background task polled this mailbox; the task maintains it, and an account becomes due for another poll once it is more than 15 minutes old. |
| `--from-last-check-time` | range | |
| `--to-last-check-time` | range | |
| `--error-count` | int | Number of failed mailbox connection attempts since the last scheduled check; the check resets it to zero, and once it passes the EmailAccounts.MaxRetries limit the account is deactivated and a warning email is queued to the account address. |
| `--from-error-count` | range | |
| `--to-error-count` | range | |
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
| `--business-id` | long, required | ID of the location that owns this email account; it is supplied from the agent context. |
| `--display-name` | string, required | Account name shown to operators, and the sender display name on email sent through this account; required. |
| `--email-address` | string, required | Mailbox address this account connects to; it is the From and Reply-To address of email sent through the account, and it must be unique within the location. Required. |
| `--active` | bool | Whether the mailbox is polled for new messages; the background check runs about every 15 minutes and skips accounts in a suspended location, and the system switches this off by itself after repeated connection failures. |
| `--send-notification-on-new-messages` | bool | Whether a notification email is sent each time an inbound message is attached to a customer record through this account. |
| `--notification-email-address` | string | Address that receives those new-message notifications; it only applies while SendNotificationOnNewMessages is on, and when it is left empty the notifications go to EmailAddress instead. |
| `--incoming-server` | string, required | Host name of the IMAP server messages are read from, for example imap.gmail.com; required, and ignored on accounts connected through Google or Microsoft OAuth. |
| `--incoming-server-type` | enum, required | Protocol used to read the mailbox; Imap is the only supported value. |
| `--incoming-server-port` | int, required | TCP port of the IMAP server, normally 993 with SSL and 143 without; ignored on accounts connected through Google or Microsoft OAuth. |
| `--incoming-server-s-s-l` | bool | Whether the IMAP connection is made over SSL/TLS; ignored on accounts connected through Google or Microsoft OAuth. |
| `--incoming-server-username` | string, required | User name used to sign in to the IMAP server, usually the full mailbox address; required, stored encrypted, and ignored on accounts connected through Google or Microsoft OAuth. |
| `--delete-message-settings` | enum, required | What happens to a message left in the mailbox after Nexudus imports it: DontDelete leaves it in place, DeleteOnReceive removes it as soon as it is imported, and DeleteWhenDeleting removes it only when the matching customer message is deleted in Nexudus. |
| `--outgoing-server` | string, required | Host name of the SMTP server used to send email from this account, for example smtp.gmail.com; required. |
| `--outgoing-server-port` | int, required | TCP port of the SMTP server, normally 587 or 465. |
| `--outgoing-server-s-s-l` | bool | Whether the SMTP connection is made over SSL/TLS. |
| `--outgoing-server-username` | string, required | User name used to sign in to the SMTP server, usually the full mailbox address; required and stored encrypted. |
| `--last-check-time` | DateTime | UTC timestamp of the last time the background task polled this mailbox; the task maintains it, and an account becomes due for another poll once it is more than 15 minutes old. |
| `--error-count` | int, required | Number of failed mailbox connection attempts since the last scheduled check; the check resets it to zero, and once it passes the EmailAccounts.MaxRetries limit the account is deactivated and a warning email is queued to the account address. |

#### EmailAccount update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this email account; it is supplied from the agent context. |
| `--display-name` | string | Account name shown to operators, and the sender display name on email sent through this account; required. |
| `--email-address` | string | Mailbox address this account connects to; it is the From and Reply-To address of email sent through the account, and it must be unique within the location. Required. |
| `--active` | bool | Whether the mailbox is polled for new messages; the background check runs about every 15 minutes and skips accounts in a suspended location, and the system switches this off by itself after repeated connection failures. |
| `--send-notification-on-new-messages` | bool | Whether a notification email is sent each time an inbound message is attached to a customer record through this account. |
| `--notification-email-address` | string | Address that receives those new-message notifications; it only applies while SendNotificationOnNewMessages is on, and when it is left empty the notifications go to EmailAddress instead. |
| `--incoming-server` | string | Host name of the IMAP server messages are read from, for example imap.gmail.com; required, and ignored on accounts connected through Google or Microsoft OAuth. |
| `--incoming-server-type` | enum | Protocol used to read the mailbox; Imap is the only supported value. |
| `--incoming-server-port` | int | TCP port of the IMAP server, normally 993 with SSL and 143 without; ignored on accounts connected through Google or Microsoft OAuth. |
| `--incoming-server-s-s-l` | bool | Whether the IMAP connection is made over SSL/TLS; ignored on accounts connected through Google or Microsoft OAuth. |
| `--incoming-server-username` | string | User name used to sign in to the IMAP server, usually the full mailbox address; required, stored encrypted, and ignored on accounts connected through Google or Microsoft OAuth. |
| `--delete-message-settings` | enum | What happens to a message left in the mailbox after Nexudus imports it: DontDelete leaves it in place, DeleteOnReceive removes it as soon as it is imported, and DeleteWhenDeleting removes it only when the matching customer message is deleted in Nexudus. |
| `--outgoing-server` | string | Host name of the SMTP server used to send email from this account, for example smtp.gmail.com; required. |
| `--outgoing-server-port` | int | TCP port of the SMTP server, normally 587 or 465. |
| `--outgoing-server-s-s-l` | bool | Whether the SMTP connection is made over SSL/TLS. |
| `--outgoing-server-username` | string | User name used to sign in to the SMTP server, usually the full mailbox address; required and stored encrypted. |
| `--last-check-time` | DateTime | UTC timestamp of the last time the background task polled this mailbox; the task maintains it, and an account becomes due for another poll once it is more than 15 minutes old. |
| `--error-count` | int | Number of failed mailbox connection attempts since the last scheduled check; the check resets it to zero, and once it passes the EmailAccounts.MaxRetries limit the account is deactivated and a warning email is queued to the account address. |

#### EmailAccount enum values

| Option | Valid values |
| ------ | ------------ |
| `--incoming-server-type` | `1` Imap |
| `--delete-message-settings` | `1` DontDelete, `2` DeleteOnReceive, `3` DeleteWhenDeleting |

<!-- END:GENERATED entity=EmailAccounts -->
