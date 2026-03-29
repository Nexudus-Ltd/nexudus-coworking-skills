# CoworkerIdentityCheckDocuments

<!-- BEGIN:GENERATED entity=CoworkerIdentityCheckDocuments -->

CoworkerIdentityCheckDocuments support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkeridentitycheckdocuments list --agent` | List all coworkeridentitycheckdocuments |
| `nexudus coworkeridentitycheckdocuments list --query "search" --agent` | Search coworkeridentitycheckdocuments by name |
| `nexudus coworkeridentitycheckdocuments list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkeridentitycheckdocuments get <id> --agent` | Get single coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments create --coworker-id <value> --coworker-identity-check-id <value> --name <value> --agent` | Create coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments update <id> --name "New Name" --agent` | Update coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments delete <id> --yes --agent` | Delete coworkeridentitycheckdocument (no prompt) |

#### CoworkerIdentityCheckDocument create options

`--coworker-id` (required), `--coworker-identity-check-id` (required), `--name` (required), `--verification-status`, `--notes`, `--new-photo-url`, `--clear-photo-file`, `--new-document-url`, `--clear-document-file`, `--new-additional-document-url`, `--clear-additional-document-file`

#### CoworkerIdentityCheckDocument update options

`--coworker-id`, `--coworker-identity-check-id`, `--name`, `--verification-status`, `--notes`, `--new-photo-url`, `--clear-photo-file`, `--new-document-url`, `--clear-document-file`, `--new-additional-document-url`, `--clear-additional-document-file`

### CoworkerIdentityCheckDocument (key fields)

`Id`, `CoworkerId`, `CoworkerFullName`, `CoworkerIdentityCheckId`, `CoworkerIdentityCheckName`, `Name`, `VerificationStatus`

<!-- END:GENERATED entity=CoworkerIdentityCheckDocuments -->
