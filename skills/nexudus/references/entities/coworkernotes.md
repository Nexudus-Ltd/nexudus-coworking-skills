# CoworkerNotes

<!-- BEGIN:GENERATED entity=CoworkerNotes -->

A **CoworkerNote** is an internal note attached to a customer record. Notes are only visible to location staff and administrators — they are never shown to the customer.

CoworkerNotes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkernotes list --agent` | List all coworkernotes |
| `nexudus coworkernotes list --id <id> --agent` | Filter by single ID |
| `nexudus coworkernotes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkernotes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkernotes list --coworker-id <value> --notes <value> --agent` | Filter coworkernotes by properties |
| `nexudus coworkernotes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkernotes get <id> --agent` | Get single coworkernote |
| `nexudus coworkernotes create --coworker-id <value> --notes <value> --agent` | Create coworkernote |
| `nexudus coworkernotes update <id> --name "New Name" --agent` | Update coworkernote |
| `nexudus coworkernotes delete <id> --yes --agent` | Delete coworkernote (no prompt) |

#### CoworkerNote list filter options

`--coworker-id`, `--notes`, `--added-by`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerNote create options

`--coworker-id` (required), `--notes` (required), `--added-by`

#### CoworkerNote update options

`--coworker-id`, `--notes`, `--added-by`

<!-- END:GENERATED entity=CoworkerNotes -->
