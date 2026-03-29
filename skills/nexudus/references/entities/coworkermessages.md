# CoworkerMessages

<!-- BEGIN:GENERATED entity=CoworkerMessages -->

A **CoworkerMessage** represents a message sent to or received from a specific customer (`Coworker`).

- **Outgoing messages** are created by an admin to communicate directly with a customer. The `Body` field supports HTML content.
- **Incoming messages** are received when the location has an external IMAP email account connected (via the `EmailAccount` entity). In this case, replies from the customer appear as incoming messages linked to the same `EmailAccount`.

Use `Incoming` to distinguish the direction of a message: `false` for admin-sent, `true` for customer replies. Use `IsNewMessage` to identify unread messages.

CoworkerMessages support Search, Get, Create, Update, Delete.
CoworkerMessages also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkermessages list --agent` | List all coworkermessages |
| `nexudus coworkermessages list --query "search" --agent` | Search coworkermessages by name |
| `nexudus coworkermessages list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkermessages get <id> --agent` | Get single coworkermessage |
| `nexudus coworkermessages create --coworker-id <value> --email-account-id <value> --subject <value> --agent` | Create coworkermessage |
| `nexudus coworkermessages update <id> --name "New Name" --agent` | Update coworkermessage |
| `nexudus coworkermessages delete <id> --yes --agent` | Delete coworkermessage (no prompt) |
| `nexudus coworkermessages run-command <key> <ids> --agent` | Run entity command |

#### CoworkerMessage create options

`--coworker-id` (required), `--email-account-id` (required), `--subject` (required), `--body`, `--is-new-message`, `--incoming`

#### CoworkerMessage update options

`--coworker-id`, `--email-account-id`, `--subject`, `--body`, `--is-new-message`, `--incoming`

### CoworkerMessage (key fields)

`Id`, `CoworkerId`, `CoworkerFullName`, `Subject`

<!-- END:GENERATED entity=CoworkerMessages -->
