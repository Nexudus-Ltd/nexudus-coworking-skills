# CoworkerMessages

<!-- BEGIN:GENERATED entity=CoworkerMessages -->

A message sent to or received from a customer. These can be sent using the default email settings associated with the location or via any of the connected email accounts.

Messages can be composed directly from a customer's record in the Admin Panel. Use `Incoming` to distinguish messages received from a customer from messages sent to them.

CoworkerMessages support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus coworkermessages list --agent` | List all coworkermessages |
| `nexudus coworkermessages list --id <id> --agent` | Filter by single ID |
| `nexudus coworkermessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkermessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkermessages list --coworker-id <value> --email-account-id <value> --agent` | Filter coworkermessages by properties |
| `nexudus coworkermessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkermessages get <id> --agent` | Get single coworkermessage |

#### CoworkerMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | Customer sending or receiving the message |
| `--email-account-id` | long | Email account used to send or receive the message. If not set, the default email settings configured for the location are used |
| `--subject` | string | Message subject |
| `--body` | string | Message body |
| `--message-id` | int | Automated message template that triggered this message, if sent by the system |
| `--from-message-id` | range | |
| `--to-message-id` | range | |
| `--reminder-unique-id` | string | Unique identifier of the reminder that triggered this message, if any |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerMessage PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:


### CoworkerMessage (key fields)

`Id`, `CoworkerFullName`, `EmailAccountDisplayName`

<!-- END:GENERATED entity=CoworkerMessages -->
