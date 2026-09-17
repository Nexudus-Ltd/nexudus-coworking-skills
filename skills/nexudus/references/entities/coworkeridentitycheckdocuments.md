# CoworkerIdentityCheckDocuments

<!-- BEGIN:GENERATED entity=CoworkerIdentityCheckDocuments -->

ID check evidence holds the files submitted for a customer's identity or address check; its submission status contributes to the parent check's verification lifecycle.

CoworkerIdentityCheckDocuments support Search, Get, Create, Update, Delete.
CoworkerIdentityCheckDocuments also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkeridentitycheckdocuments list --agent` | List all coworkeridentitycheckdocuments |
| `nexudus coworkeridentitycheckdocuments list --id <id> --agent` | Filter by single ID |
| `nexudus coworkeridentitycheckdocuments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkeridentitycheckdocuments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkeridentitycheckdocuments list --coworker-full-name <value> --coworker-identity-check-name <value> --agent` | Filter coworkeridentitycheckdocuments by properties |
| `nexudus coworkeridentitycheckdocuments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkeridentitycheckdocuments list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkeridentitycheckdocuments get <id> --agent` | Get single coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments create --coworker-id <value> --coworker-identity-check-id <value> --name <value> --agent` | Create coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments update <id> --name "New Name" --agent` | Update coworkeridentitycheckdocument |
| `nexudus coworkeridentitycheckdocuments delete <id> --yes --agent` | Delete coworkeridentitycheckdocument (no prompt) |
| `nexudus coworkeridentitycheckdocuments run-command <key> <ids> --agent` | Run entity command |

#### CoworkerIdentityCheckDocument list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer whose ID check evidence this is. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--coworker-identity-check-id` | long | ID of the parent customer ID check; it determines which evidence files are required and owns the document status. |
| `--coworker-identity-check-name` | string | Display value for CoworkerIdentityCheck.Name. |
| `--coworker-identity-check-verification-type` | string | Display value for CoworkerIdentityCheck.VerificationType. |
| `--coworker-identity-check-business-name` | string | Display value for CoworkerIdentityCheck.Business.Name. |
| `--coworker-identity-check-identity-document-type` | string | Display value for CoworkerIdentityCheck.IdentityDocumentType. |
| `--coworker-identity-check-identity-document-number` | string | Display value for CoworkerIdentityCheck.IdentityDocumentNumber. |
| `--coworker-identity-check-identity-document-issued-by` | string | Display value for CoworkerIdentityCheck.IdentityDocumentIssuedBy. |
| `--coworker-identity-check-identity-document-expiration-date` | DateTime | Display value for CoworkerIdentityCheck.IdentityDocumentExpirationDate. |
| `--from-coworker-identity-check-identity-document-expiration-date` | range | |
| `--to-coworker-identity-check-identity-document-expiration-date` | range | |
| `--coworker-identity-check-address-document-type` | string | Display value for CoworkerIdentityCheck.AddressDocumentType. |
| `--name` | string | Required operator-facing label for this ID check evidence record. |
| `--photo-file-name` | string | Current file name of the photo (read-only; upload via the corresponding URL field) |
| `--new-photo-url` | string | URL of a new file to upload as the photo |
| `--clear-photo-file` | bool | Set to true to remove the current photo file |
| `--document-file-name` | string | Current file name of the document (read-only; upload via the corresponding URL field) |
| `--new-document-url` | string | URL of a new file to upload as the document |
| `--clear-document-file` | bool | Set to true to remove the current document file |
| `--additional-document-file-name` | string | Current file name of the additional document (read-only; upload via the corresponding URL field) |
| `--new-additional-document-url` | string | URL of a new file to upload as the additional document |
| `--clear-additional-document-file` | bool | Set to true to remove the current additional document file |
| `--verification-status` | enum | Read-only document status: Pending, Submitted, Successful, Failed, or Cancelled; uploading evidence sets it to Submitted. |
| `--notes` | string | Optional free-text reviewer notes about this ID check evidence. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerIdentityCheckDocument sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerIdentityCheckDocument create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer whose ID check evidence this is. |
| `--coworker-identity-check-id` | long, required | ID of the parent customer ID check; it determines which evidence files are required and owns the document status. |
| `--name` | string, required | Required operator-facing label for this ID check evidence record. |
| `--new-photo-url` | string | URL of a new file to upload as the photo |
| `--clear-photo-file` | bool | Set to true to remove the current photo file |
| `--new-document-url` | string | URL of a new file to upload as the document |
| `--clear-document-file` | bool | Set to true to remove the current document file |
| `--new-additional-document-url` | string | URL of a new file to upload as the additional document |
| `--clear-additional-document-file` | bool | Set to true to remove the current additional document file |
| `--notes` | string | Optional free-text reviewer notes about this ID check evidence. |

#### CoworkerIdentityCheckDocument update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer whose ID check evidence this is. |
| `--coworker-identity-check-id` | long | ID of the parent customer ID check; it determines which evidence files are required and owns the document status. |
| `--name` | string | Required operator-facing label for this ID check evidence record. |
| `--new-photo-url` | string | URL of a new file to upload as the photo |
| `--clear-photo-file` | bool | Set to true to remove the current photo file |
| `--new-document-url` | string | URL of a new file to upload as the document |
| `--clear-document-file` | bool | Set to true to remove the current document file |
| `--new-additional-document-url` | string | URL of a new file to upload as the additional document |
| `--clear-additional-document-file` | bool | Set to true to remove the current additional document file |
| `--notes` | string | Optional free-text reviewer notes about this ID check evidence. |

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
