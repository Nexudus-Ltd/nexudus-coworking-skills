# CoworkerDataFiles

<!-- BEGIN:GENERATED entity=CoworkerDataFiles -->

A **CoworkerDataFile** represents a file attached to a customer (coworker) record. Files can be shared with the customer via the portal and mobile app, and optionally require an e-signature.

Use `--available-to-user` to make the file visible to the customer in their portal and app. Use `--request-digital-signature` to send a notification asking the customer to electronically sign the document. When `Signed` is `true`, the signed copy is available via `SignedFileDataFileName`.

You can optionally set `--notify-when-signed-email` to receive an email notification once the customer signs the document.

CoworkerDataFiles support Search, Get, Create, Update, Delete.
CoworkerDataFiles also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkerdatafiles list --agent` | List all coworkerdatafiles |
| `nexudus coworkerdatafiles list --query "search" --agent` | Search coworkerdatafiles by name |
| `nexudus coworkerdatafiles list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkerdatafiles get <id> --agent` | Get single coworkerdatafile |
| `nexudus coworkerdatafiles create --business <value> --coworker-id <value> --name <value> --agent` | Create coworkerdatafile |
| `nexudus coworkerdatafiles update <id> --name "New Name" --agent` | Update coworkerdatafile |
| `nexudus coworkerdatafiles delete <id> --yes --agent` | Delete coworkerdatafile (no prompt) |
| `nexudus coworkerdatafiles run-command <key> <ids> --agent` | Run entity command |

#### CoworkerDataFile create options

`--business` (required), `--coworker-id` (required), `--name` (required), `--description`, `--available-to-user`, `--request-digital-signature`, `--notify-when-signed-email`, `--file-url`, `--clear-file`, `--signed-file-url`, `--clear-signed-file`

#### CoworkerDataFile update options

`--coworker-id`, `--name`, `--description`, `--available-to-user`, `--request-digital-signature`, `--notify-when-signed-email`, `--file-url`, `--clear-file`, `--signed-file-url`, `--clear-signed-file`

### CoworkerDataFile (key fields)

`Id`, `BusinessId`, `BusinessName`, `CoworkerId`, `CoworkerFullName`, `Name`, `Signed`

<!-- END:GENERATED entity=CoworkerDataFiles -->
