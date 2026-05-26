# CoworkerDataFiles

<!-- BEGIN:GENERATED entity=CoworkerDataFiles -->

A **CoworkerDataFile** is a file attached to a customer's record. Files can be kept internal or shared with the customer on the Members Portal.

When a file is shared (`AvailableToUser = true`), the customer receives an email notification and can view or download the file from the Files tab under My Activity on the Members Portal.

You can request a digital signature (`RequestDigitalSignature = true`) — once the customer signs the document, a signed copy is automatically stored in `SignedFileDataFileName`. The notes in `Description` are included in the email notification sent to the customer.

Supported formats include .pdf, .docx, .xlsx, .jpg, .png, and other common types (max 10 MB). Files can be linked to a document template, a proposal, or a coworker contract via the respective GUID fields.

CoworkerDataFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerdatafiles list --agent` | List all coworkerdatafiles |
| `nexudus coworkerdatafiles list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerdatafiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerdatafiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerdatafiles list --name <value> --agent` | Filter coworkerdatafiles by properties |
| `nexudus coworkerdatafiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerdatafiles get <id> --agent` | Get single coworkerdatafile |
| `nexudus coworkerdatafiles create --business-id <value> --coworker-id <value> --name <value> --agent` | Create coworkerdatafile |
| `nexudus coworkerdatafiles update <id> --name "New Name" --agent` | Update coworkerdatafile |
| `nexudus coworkerdatafiles delete <id> --yes --agent` | Delete coworkerdatafile (no prompt) |

#### CoworkerDataFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | Location ID |
| `--coworker-id` | long | ID of the customer this file belongs to |
| `--name` | string | Name of the file or document |
| `--description` | string | Notes included in the email notification sent to the customer when the file is shared |
| `--available-to-user` | bool | Whether the file is shared with the customer and visible on the Members Portal |
| `--request-digital-signature` | bool | Whether to request a digital signature from the customer |
| `--new-file-data-url` | string | URL of a new file to upload (replaces the existing file) |
| `--clear-file-data-file` | bool | Set to true to remove the existing uploaded file |
| `--new-signed-file-data-url` | string | URL of a new signed file to upload (replaces the existing signed copy) |
| `--clear-signed-file-data-file` | bool | Set to true to remove the existing signed copy |
| `--extension` | string | File extension (e.g. pdf, docx, jpg) |
| `--billed` | bool | Whether the customer has been billed for this file |
| `--signed` | bool | Whether the customer has signed this document |
| `--esign-identifier` | string | Identifier used by the digital signature provider to track this document |
| `--document-template-guid` | string | GUID of the document template used to generate this file |
| `--notify-when-signed-email` | string | Email address to notify when the customer signs the document |
| `--proposal-guid` | string | GUID of the proposal linked to this file |
| `--coworker-contract-guid` | string | GUID of the coworker contract linked to this file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerDataFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | Location ID |
| `--coworker-id` | long, required | ID of the customer this file belongs to |
| `--name` | string, required | Name of the file or document |
| `--description` | string | Notes included in the email notification sent to the customer when the file is shared |
| `--available-to-user` | bool | Whether the file is shared with the customer and visible on the Members Portal |
| `--request-digital-signature` | bool | Whether to request a digital signature from the customer |
| `--new-file-data-url` | string | URL of a new file to upload (replaces the existing file) |
| `--clear-file-data-file` | bool | Set to true to remove the existing uploaded file |
| `--new-signed-file-data-url` | string | URL of a new signed file to upload (replaces the existing signed copy) |
| `--clear-signed-file-data-file` | bool | Set to true to remove the existing signed copy |
| `--extension` | string | File extension (e.g. pdf, docx, jpg) |
| `--billed` | bool | Whether the customer has been billed for this file |
| `--signed` | bool | Whether the customer has signed this document |
| `--esign-identifier` | string | Identifier used by the digital signature provider to track this document |
| `--document-template-guid` | string | GUID of the document template used to generate this file |
| `--notify-when-signed-email` | string | Email address to notify when the customer signs the document |
| `--proposal-guid` | string | GUID of the proposal linked to this file |
| `--coworker-contract-guid` | string | GUID of the coworker contract linked to this file |

#### CoworkerDataFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | Location ID |
| `--coworker-id` | long | ID of the customer this file belongs to |
| `--name` | string | Name of the file or document |
| `--description` | string | Notes included in the email notification sent to the customer when the file is shared |
| `--available-to-user` | bool | Whether the file is shared with the customer and visible on the Members Portal |
| `--request-digital-signature` | bool | Whether to request a digital signature from the customer |
| `--new-file-data-url` | string | URL of a new file to upload (replaces the existing file) |
| `--clear-file-data-file` | bool | Set to true to remove the existing uploaded file |
| `--new-signed-file-data-url` | string | URL of a new signed file to upload (replaces the existing signed copy) |
| `--clear-signed-file-data-file` | bool | Set to true to remove the existing signed copy |
| `--extension` | string | File extension (e.g. pdf, docx, jpg) |
| `--billed` | bool | Whether the customer has been billed for this file |
| `--signed` | bool | Whether the customer has signed this document |
| `--esign-identifier` | string | Identifier used by the digital signature provider to track this document |
| `--document-template-guid` | string | GUID of the document template used to generate this file |
| `--notify-when-signed-email` | string | Email address to notify when the customer signs the document |
| `--proposal-guid` | string | GUID of the proposal linked to this file |
| `--coworker-contract-guid` | string | GUID of the coworker contract linked to this file |

#### CoworkerDataFile PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notify-when-signed-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus coworkerdatafiles update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerDataFile (key fields)

`Id`, `BusinessName`, `CoworkerFullName`, `Name`

<!-- END:GENERATED entity=CoworkerDataFiles -->
