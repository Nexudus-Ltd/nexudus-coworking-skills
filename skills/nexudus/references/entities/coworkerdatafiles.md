# CoworkerDataFiles

<!-- BEGIN:GENERATED entity=CoworkerDataFiles -->

CoworkerDataFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerdatafiles list --agent` | List all coworkerdatafiles |
| `nexudus coworkerdatafiles list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerdatafiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerdatafiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerdatafiles list --business-id <value> --coworker-id <value> --agent` | Filter coworkerdatafiles by properties |
| `nexudus coworkerdatafiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerdatafiles get <id> --agent` | Get single coworkerdatafile |
| `nexudus coworkerdatafiles create --business-id <value> --coworker-id <value> --name <value> --agent` | Create coworkerdatafile |
| `nexudus coworkerdatafiles update <id> --name "New Name" --agent` | Update coworkerdatafile |
| `nexudus coworkerdatafiles delete <id> --yes --agent` | Delete coworkerdatafile (no prompt) |

#### CoworkerDataFile list filter options

`--business-id`, `--coworker-id`, `--name`, `--description`, `--available-to-user`, `--request-digital-signature`, `--new-file-data-url`, `--clear-file-data-file`, `--new-signed-file-data-url`, `--clear-signed-file-data-file`, `--extension`, `--billed`, `--signed`, `--esign-identifier`, `--document-template-guid`, `--notify-when-signed-email`, `--proposal-guid`, `--coworker-contract-guid`

#### CoworkerDataFile create options

`--business-id` (required), `--coworker-id` (required), `--name` (required), `--description`, `--available-to-user`, `--request-digital-signature`, `--new-file-data-url`, `--clear-file-data-file`, `--new-signed-file-data-url`, `--clear-signed-file-data-file`, `--extension`, `--billed`, `--signed`, `--esign-identifier`, `--document-template-guid`, `--notify-when-signed-email`, `--proposal-guid`, `--coworker-contract-guid`

#### CoworkerDataFile update options

`--business-id`, `--coworker-id`, `--name`, `--description`, `--available-to-user`, `--request-digital-signature`, `--new-file-data-url`, `--clear-file-data-file`, `--new-signed-file-data-url`, `--clear-signed-file-data-file`, `--extension`, `--billed`, `--signed`, `--esign-identifier`, `--document-template-guid`, `--notify-when-signed-email`, `--proposal-guid`, `--coworker-contract-guid`

<!-- END:GENERATED entity=CoworkerDataFiles -->
