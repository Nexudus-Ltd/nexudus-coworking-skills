# CoworkerMessages

<!-- BEGIN:GENERATED entity=CoworkerMessages -->

CoworkerMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkermessages list --agent` | List all coworkermessages |
| `nexudus coworkermessages list --query "search" --agent` | Search coworkermessages by name |
| `nexudus coworkermessages list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkermessages get <id> --agent` | Get single coworkermessage |
| `nexudus coworkermessages create --coworker-id <value> --email-account-id <value> --subject <value> --agent` | Create coworkermessage |
| `nexudus coworkermessages update <id> --name "New Name" --agent` | Update coworkermessage |
| `nexudus coworkermessages delete <id> --yes --agent` | Delete coworkermessage (no prompt) |

#### CoworkerMessage create options

`--coworker-id` (required), `--email-account-id` (required), `--subject` (required), `--body`, `--is-new-message`, `--incoming`

#### CoworkerMessage update options

`--coworker-id`, `--email-account-id`, `--subject`, `--body`, `--is-new-message`, `--incoming`

### CoworkerMessage (key fields)

`Id`, `CoworkerId`, `CoworkerFullName`, `Subject`

<!-- END:GENERATED entity=CoworkerMessages -->
