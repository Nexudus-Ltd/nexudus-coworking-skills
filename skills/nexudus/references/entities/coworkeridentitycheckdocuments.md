# CoworkerIdentityCheckDocuments

<!-- BEGIN:GENERATED entity=CoworkerIdentityCheckDocuments -->

A **CoworkerIdentityCheckDocument** represents a document submitted as part of a `CoworkerIdentityCheck` for a customer. Each document record can hold up to three files, corresponding to different sides or aspects of the verification evidence:

| File slot | Field prefix | Purpose |
| --------- | ------------ | ------- |
| Face photo | `Photo` | A photograph of the customer's face |
| Front | `Document` | The front side of the identity or address document |
| Back | `AdditionalDocument` | The back side or a supplementary page of the document |

Which slots are required depends on the `VerificationType` and document type configured on the parent `CoworkerIdentityCheck`.

The `VerificationStatus` tracks the review state of this individual document through the same lifecycle used by `CoworkerIdentityCheck`: `Pending` → `Submitted` → `Successful` or `Failed` (or `Cancelled`).

CoworkerIdentityCheckDocuments support Search, Get, Create, Update, Delete.
CoworkerIdentityCheckDocuments also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkeridentitycheckdocuments list --agent` | List all coworkeridentitycheckdocuments |
| `nexudus coworkeridentitycheckdocuments list --query "search" --agent` | Search coworkeridentitycheckdocuments by name |
| `nexudus coworkeridentitycheckdocuments list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkeridentitycheckdocuments get <id> --agent` | Get single coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments create --coworker-id <value> --coworker-identity-check-id <value> --name <value> --agent` | Create coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments update <id> --name "New Name" --agent` | Update coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments delete <id> --yes --agent` | Delete coworkeridentitycheckdocument (no prompt) |
| `nexudus coworkeridentitycheckdocuments run-command <key> <ids> --agent` | Run entity command |

#### CoworkerIdentityCheckDocument create options

`--coworker-id` (required), `--coworker-identity-check-id` (required), `--name` (required), `--verification-status`, `--notes`, `--new-photo-url`, `--clear-photo-file`, `--new-document-url`, `--clear-document-file`, `--new-additional-document-url`, `--clear-additional-document-file`

#### CoworkerIdentityCheckDocument update options

`--coworker-id`, `--coworker-identity-check-id`, `--name`, `--verification-status`, `--notes`, `--new-photo-url`, `--clear-photo-file`, `--new-document-url`, `--clear-document-file`, `--new-additional-document-url`, `--clear-additional-document-file`

### CoworkerIdentityCheckDocument (key fields)

`Id`, `CoworkerId`, `CoworkerFullName`, `CoworkerIdentityCheckId`, `CoworkerIdentityCheckName`, `Name`, `VerificationStatus`

#### CoworkerIdentityCheckDocument enum values

| Option | Valid values |
| ------ | ------------ |
| `--verification-status` | `0` None, `1` Pending, `2` Submitted, `3` Successful, `4` Failed, `5` Cancelled |

<!-- END:GENERATED entity=CoworkerIdentityCheckDocuments -->
