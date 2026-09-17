# CoworkerDataFiles

<!-- BEGIN:GENERATED entity=CoworkerDataFiles -->

A customer file is a document attached to a customer's record that can remain internal, be shared through the Members Portal, or be sent for digital signature.

CoworkerDataFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerdatafiles list --agent` | List all coworkerdatafiles |
| `nexudus coworkerdatafiles list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerdatafiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerdatafiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerdatafiles list --business-name <value> --coworker-full-name <value> --agent` | Filter coworkerdatafiles by properties |
| `nexudus coworkerdatafiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerdatafiles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerdatafiles get <id> --agent` | Get single coworkerdatafile |
| `nexudus coworkerdatafiles create --business-id <value> --coworker-id <value> --name <value> --agent` | Create coworkerdatafile |
| `nexudus coworkerdatafiles update <id> --name "New Name" --agent` | Update coworkerdatafile |
| `nexudus coworkerdatafiles delete <id> --yes --agent` | Delete coworkerdatafile (no prompt) |

#### CoworkerDataFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this customer file belongs to; it is supplied from the admin context when creating the record. |
| `--business-name` | string | Display value for Business.Name. |
| `--coworker-id` | long | ID of the customer this file belongs to. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--name` | string | Required name displayed for the customer file or document. |
| `--description` | string | Optional notes for the customer file; included in the notification sent when a new file is shared or sent for signature. |
| `--available-to-user` | bool | Whether the customer can view and download the file in the Members Portal; creating a shared file sends the new-file notification. |
| `--request-digital-signature` | bool | Whether to request a digital signature from the customer; requires a portal-enabled customer, enabled Dropbox Sign integration, and valid signatories. |
| `--file-data-file-name` | string | Name of the uploaded file |
| `--new-file-data-url` | string | URL of a new file to upload (replaces the existing file) |
| `--clear-file-data-file` | bool | Set to true to remove the existing uploaded file |
| `--signed-file-data-file-name` | string | Name of the signed copy of the document, created automatically after the customer signs it |
| `--new-signed-file-data-url` | string | URL of a new signed file to upload (replaces the existing signed copy) |
| `--clear-signed-file-data-file` | bool | Set to true to remove the existing signed copy |
| `--extension` | string | File extension for the stored document, such as .pdf, .docx, or .jpg. |
| `--billed` | bool | Whether the location has billed for this file's digital signature request. |
| `--signed` | bool | Whether the customer has signed the document; this status is updated by the digital signature provider. |
| `--document-template-guid` | string | Unique ID of the document template used to generate the file; required when CoworkerContractGuid is set. |
| `--notify-when-signed-email` | string | Email address to notify after the customer signs; when omitted for a signature request, it defaults to the creating user's email when available. |
| `--proposal-guid` | string | Unique ID of the proposal this file supports; proposal workflows use it to locate their generated documents. |
| `--coworker-contract-guid` | string | Unique ID of the customer's contract used to generate a contract document; requires DocumentTemplateGuid. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerDataFile sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerDataFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this customer file belongs to; it is supplied from the admin context when creating the record. |
| `--coworker-id` | long, required | ID of the customer this file belongs to. |
| `--name` | string, required | Required name displayed for the customer file or document. |
| `--description` | string | Optional notes for the customer file; included in the notification sent when a new file is shared or sent for signature. |
| `--available-to-user` | bool | Whether the customer can view and download the file in the Members Portal; creating a shared file sends the new-file notification. |
| `--request-digital-signature` | bool | Whether to request a digital signature from the customer; requires a portal-enabled customer, enabled Dropbox Sign integration, and valid signatories. |
| `--new-file-data-url` | string | URL of a new file to upload (replaces the existing file) |
| `--clear-file-data-file` | bool | Set to true to remove the existing uploaded file |
| `--new-signed-file-data-url` | string | URL of a new signed file to upload (replaces the existing signed copy) |
| `--clear-signed-file-data-file` | bool | Set to true to remove the existing signed copy |
| `--extension` | string | File extension for the stored document, such as .pdf, .docx, or .jpg. |
| `--billed` | bool | Whether the location has billed for this file's digital signature request. |
| `--document-template-guid` | string | Unique ID of the document template used to generate the file; required when CoworkerContractGuid is set. |
| `--notify-when-signed-email` | string | Email address to notify after the customer signs; when omitted for a signature request, it defaults to the creating user's email when available. |
| `--proposal-guid` | string | Unique ID of the proposal this file supports; proposal workflows use it to locate their generated documents. |
| `--coworker-contract-guid` | string | Unique ID of the customer's contract used to generate a contract document; requires DocumentTemplateGuid. |

#### CoworkerDataFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this customer file belongs to; it is supplied from the admin context when creating the record. |
| `--coworker-id` | long | ID of the customer this file belongs to. |
| `--name` | string | Required name displayed for the customer file or document. |
| `--description` | string | Optional notes for the customer file; included in the notification sent when a new file is shared or sent for signature. |
| `--available-to-user` | bool | Whether the customer can view and download the file in the Members Portal; creating a shared file sends the new-file notification. |
| `--request-digital-signature` | bool | Whether to request a digital signature from the customer; requires a portal-enabled customer, enabled Dropbox Sign integration, and valid signatories. |
| `--new-file-data-url` | string | URL of a new file to upload (replaces the existing file) |
| `--clear-file-data-file` | bool | Set to true to remove the existing uploaded file |
| `--new-signed-file-data-url` | string | URL of a new signed file to upload (replaces the existing signed copy) |
| `--clear-signed-file-data-file` | bool | Set to true to remove the existing signed copy |
| `--extension` | string | File extension for the stored document, such as .pdf, .docx, or .jpg. |
| `--billed` | bool | Whether the location has billed for this file's digital signature request. |
| `--document-template-guid` | string | Unique ID of the document template used to generate the file; required when CoworkerContractGuid is set. |
| `--notify-when-signed-email` | string | Email address to notify after the customer signs; when omitted for a signature request, it defaults to the creating user's email when available. |
| `--proposal-guid` | string | Unique ID of the proposal this file supports; proposal workflows use it to locate their generated documents. |
| `--coworker-contract-guid` | string | Unique ID of the customer's contract used to generate a contract document; requires DocumentTemplateGuid. |

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
