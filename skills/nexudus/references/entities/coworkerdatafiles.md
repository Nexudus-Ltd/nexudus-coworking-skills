# CoworkerDataFiles

<!-- BEGIN:GENERATED entity=CoworkerDataFiles -->

CoworkerDataFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerdatafiles list --agent` | List all coworkerdatafiles |
| `nexudus coworkerdatafiles list --query "search" --agent` | Search coworkerdatafiles by name |
| `nexudus coworkerdatafiles list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkerdatafiles get <id> --agent` | Get single coworkerdatafile |
| `nexudus coworkerdatafiles create --business <value> --coworker-id <value> --name <value> --agent` | Create coworkerdatafile |
| `nexudus coworkerdatafiles update <id> --name "New Name" --agent` | Update coworkerdatafile |
| `nexudus coworkerdatafiles delete <id> --yes --agent` | Delete coworkerdatafile (no prompt) |

#### CoworkerDataFile create options

`--business` (required), `--coworker-id` (required), `--name` (required), `--description`, `--available-to-user`, `--request-digital-signature`, `--notify-when-signed-email`, `--file-url`, `--clear-file`, `--signed-file-url`, `--clear-signed-file`

#### CoworkerDataFile update options

`--coworker-id`, `--name`, `--description`, `--available-to-user`, `--request-digital-signature`, `--notify-when-signed-email`, `--file-url`, `--clear-file`, `--signed-file-url`, `--clear-signed-file`

### CoworkerDataFile (key fields)

`Id`, `BusinessId`, `BusinessName`, `CoworkerId`, `CoworkerFullName`, `Name`, `Signed`

<!-- END:GENERATED entity=CoworkerDataFiles -->
