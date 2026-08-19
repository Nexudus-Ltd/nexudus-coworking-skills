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
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--coworker-full-name` | string | Full name of the customer this document belongs to |
| `--coworker-type` | string | Type of the customer (e.g. Member, TeamMember) |
| `--coworker-company-name` | string | Company name of the customer |
| `--coworker-billing-name` | string | Billing name of the customer |
| `--coworker-identity-check-id` | long | ID of the coworker identity check linked to this record |
| `--coworker-identity-check-name` | string | Name of the parent identity or address check |
| `--coworker-identity-check-verification-type` | string | Verification type of the parent check (IdDocument or Address) |
| `--coworker-identity-check-business-name` | string | Location (business) name from the parent check |
| `--coworker-identity-check-identity-document-type` | string | Identity document type from the parent check (e.g. Passport, DriversLicense) |
| `--coworker-identity-check-identity-document-number` | string | Document number from the parent check |
| `--coworker-identity-check-identity-document-issued-by` | string | Issuing authority from the parent check |
| `--coworker-identity-check-identity-document-expiration-date` | DateTime | Document expiration date from the parent check |
| `--from-coworker-identity-check-identity-document-expiration-date` | range | |
| `--to-coworker-identity-check-identity-document-expiration-date` | range | |
| `--coworker-identity-check-address-document-type` | string | Address document type from the parent check (e.g. LeaseRentalAgreement, VoterCard) |
| `--name` | string | Display name for this document record |
| `--photo-file-name` | string | Current file name of the photo (read-only; upload via the corresponding URL field) |
| `--new-photo-url` | string | URL of a new file to upload as the photo |
| `--clear-photo-file` | bool | Set to true to remove the current photo file |
| `--document-file-name` | string | Current file name of the document (read-only; upload via the corresponding URL field) |
| `--new-document-url` | string | URL of a new file to upload as the document |
| `--clear-document-file` | bool | Set to true to remove the current document file |
| `--additional-document-file-name` | string | Current file name of the additional document (read-only; upload via the corresponding URL field) |
| `--new-additional-document-url` | string | URL of a new file to upload as the additional document |
| `--clear-additional-document-file` | bool | Set to true to remove the current additional document file |
| `--verification-status` | enum | Current review status of this document (Pending, Submitted, Successful, Failed, or Cancelled) |
| `--notes` | string | Free-text notes or reviewer comments about this document |
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
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--coworker-identity-check-id` | long, required | ID of the coworker identity check linked to this record |
| `--name` | string, required | Display name for this document record |
| `--new-photo-url` | string | URL of a new file to upload as the photo |
| `--clear-photo-file` | bool | Set to true to remove the current photo file |
| `--new-document-url` | string | URL of a new file to upload as the document |
| `--clear-document-file` | bool | Set to true to remove the current document file |
| `--new-additional-document-url` | string | URL of a new file to upload as the additional document |
| `--clear-additional-document-file` | bool | Set to true to remove the current additional document file |
| `--notes` | string | Free-text notes or reviewer comments about this document |

#### CoworkerIdentityCheckDocument update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--coworker-identity-check-id` | long | ID of the coworker identity check linked to this record |
| `--name` | string | Display name for this document record |
| `--new-photo-url` | string | URL of a new file to upload as the photo |
| `--clear-photo-file` | bool | Set to true to remove the current photo file |
| `--new-document-url` | string | URL of a new file to upload as the document |
| `--clear-document-file` | bool | Set to true to remove the current document file |
| `--new-additional-document-url` | string | URL of a new file to upload as the additional document |
| `--clear-additional-document-file` | bool | Set to true to remove the current additional document file |
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
