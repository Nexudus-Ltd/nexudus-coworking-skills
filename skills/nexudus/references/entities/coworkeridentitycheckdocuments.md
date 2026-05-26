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
| `nexudus coworkeridentitycheckdocuments list --id <id> --agent` | Filter by single ID |
| `nexudus coworkeridentitycheckdocuments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkeridentitycheckdocuments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkeridentitycheckdocuments list --name <value> --agent` | Filter coworkeridentitycheckdocuments by properties |
| `nexudus coworkeridentitycheckdocuments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkeridentitycheckdocuments get <id> --agent` | Get single coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments create --coworker-id <value> --coworker-identity-check-id <value> --name <value> --agent` | Create coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments update <id> --name "New Name" --agent` | Update coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments delete <id> --yes --agent` | Delete coworkeridentitycheckdocument (no prompt) |
| `nexudus coworkeridentitycheckdocuments run-command <key> <ids> --agent` | Run entity command |

#### CoworkerIdentityCheckDocument list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long |  |
| `--coworker-identity-check-id` | long |  |
| `--name` | string | Display name for this document record |
| `--new-photo-url` | string |  |
| `--clear-photo-file` | bool |  |
| `--new-document-url` | string |  |
| `--clear-document-file` | bool |  |
| `--new-additional-document-url` | string |  |
| `--clear-additional-document-file` | bool |  |
| `--notes` | string | Free-text notes or reviewer comments about this document |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerIdentityCheckDocument create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required |  |
| `--coworker-identity-check-id` | long, required |  |
| `--name` | string, required | Display name for this document record |
| `--new-photo-url` | string |  |
| `--clear-photo-file` | bool |  |
| `--new-document-url` | string |  |
| `--clear-document-file` | bool |  |
| `--new-additional-document-url` | string |  |
| `--clear-additional-document-file` | bool |  |
| `--notes` | string | Free-text notes or reviewer comments about this document |

#### CoworkerIdentityCheckDocument update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long |  |
| `--coworker-identity-check-id` | long |  |
| `--name` | string | Display name for this document record |
| `--new-photo-url` | string |  |
| `--clear-photo-file` | bool |  |
| `--new-document-url` | string |  |
| `--clear-document-file` | bool |  |
| `--new-additional-document-url` | string |  |
| `--clear-additional-document-file` | bool |  |
| `--notes` | string | Free-text notes or reviewer comments about this document |

#### CoworkerIdentityCheckDocument PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkeridentitycheckdocuments update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerIdentityCheckDocument (key fields)

`Id`, `CoworkerFullName`, `CoworkerIdentityCheckName`, `Name`, `VerificationStatus`

<!-- END:GENERATED entity=CoworkerIdentityCheckDocuments -->
