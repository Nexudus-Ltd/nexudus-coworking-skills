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

`--business-id`, `--coworker-id`, `--name`, `--description`, `--available-to-user`, `--request-digital-signature`, `--new-file-data-url`, `--clear-file-data-file`, `--new-signed-file-data-url`, `--clear-signed-file-data-file`, `--extension`, `--billed`, `--signed`, `--esign-identifier`, `--document-template-guid`, `--notify-when-signed-email`, `--proposal-guid`, `--coworker-contract-guid`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerDataFile create options

`--business-id` (required), `--coworker-id` (required), `--name` (required), `--description`, `--available-to-user`, `--request-digital-signature`, `--new-file-data-url`, `--clear-file-data-file`, `--new-signed-file-data-url`, `--clear-signed-file-data-file`, `--extension`, `--billed`, `--signed`, `--esign-identifier`, `--document-template-guid`, `--notify-when-signed-email`, `--proposal-guid`, `--coworker-contract-guid`

#### CoworkerDataFile update options

`--business-id`, `--coworker-id`, `--name`, `--description`, `--available-to-user`, `--request-digital-signature`, `--new-file-data-url`, `--clear-file-data-file`, `--new-signed-file-data-url`, `--clear-signed-file-data-file`, `--extension`, `--billed`, `--signed`, `--esign-identifier`, `--document-template-guid`, `--notify-when-signed-email`, `--proposal-guid`, `--coworker-contract-guid`

### CoworkerDataFile (key fields)

`Id`, `BusinessName`, `CoworkerFullName`, `Name`

<!-- END:GENERATED entity=CoworkerDataFiles -->
