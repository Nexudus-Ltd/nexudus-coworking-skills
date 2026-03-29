# CoworkerNotes

<!-- BEGIN:GENERATED entity=CoworkerNotes -->

CoworkerNotes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkernotes list --agent` | List all coworkernotes |
| `nexudus coworkernotes list --query "search" --agent` | Search coworkernotes by name |
| `nexudus coworkernotes list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkernotes get <id> --agent` | Get single coworkernote |
| `nexudus coworkernotes create --coworker-id <value> --notes <value> --agent` | Create coworkernote |
| `nexudus coworkernotes update <id> --name "New Name" --agent` | Update coworkernote |
| `nexudus coworkernotes delete <id> --yes --agent` | Delete coworkernote (no prompt) |

#### CoworkerNote create options

`--coworker-id` (required), `--notes` (required), `--added-by`

#### CoworkerNote update options

`--coworker-id`, `--notes`, `--added-by`

### CoworkerNote (key fields)

`Id`, `CoworkerId`, `Notes`

<!-- END:GENERATED entity=CoworkerNotes -->
