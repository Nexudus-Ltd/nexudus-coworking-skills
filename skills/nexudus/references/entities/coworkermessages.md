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

`--coworker-id`, `--email-account-id`, `--subject`, `--body`, `--message-id`, `--from-message-id` (range), `--to-message-id` (range), `--reminder-unique-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

### CoworkerMessage (key fields)

`Id`, `CoworkerFullName`, `EmailAccountDisplayName`

<!-- END:GENERATED entity=CoworkerMessages -->
