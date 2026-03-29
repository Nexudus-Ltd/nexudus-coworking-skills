# CoworkerNotes

<!-- BEGIN:GENERATED entity=CoworkerNotes -->

A **CoworkerNote** stores an internal note associated with a Customer. These notes are only visible to administrators and are not shown to the customer.

Use coworker notes to record private observations, follow-ups, or any internal context relevant to a customer's account.

CoworkerNotes support Search, Get, Create, Update, Delete.
CoworkerNotes also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkernotes list --agent` | List all coworkernotes |
| `nexudus coworkernotes list --query "search" --agent` | Search coworkernotes by name |
| `nexudus coworkernotes list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkernotes get <id> --agent` | Get single coworkernote |
| `nexudus coworkernotes create --coworker-id <value> --notes <value> --agent` | Create coworkernote |
| `nexudus coworkernotes update <id> --name "New Name" --agent` | Update coworkernote |
| `nexudus coworkernotes delete <id> --yes --agent` | Delete coworkernote (no prompt) |
| `nexudus coworkernotes run-command <key> <ids> --agent` | Run entity command |

#### CoworkerNote create options

`--coworker-id` (required), `--notes` (required), `--added-by`

#### CoworkerNote update options

`--coworker-id`, `--notes`, `--added-by`

### CoworkerNote (key fields)

`Id`, `CoworkerId`, `Notes`

<!-- END:GENERATED entity=CoworkerNotes -->
