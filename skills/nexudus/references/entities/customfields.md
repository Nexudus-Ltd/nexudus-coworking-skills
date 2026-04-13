# CustomFields

<!-- BEGIN:GENERATED entity=CustomFields -->

CustomFields support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus customfields list --agent` | List all customfields |
| `nexudus customfields list --id <id> --agent` | Filter by single ID |
| `nexudus customfields list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus customfields list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus customfields list --business-id <value> --name <value> --agent` | Filter customfields by properties |
| `nexudus customfields list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus customfields get <id> --agent` | Get single customfield |
| `nexudus customfields create --business-id <value> --name <value> --display-order <value> --record-type <value> --field-type <value> --coworker-field-position <value> --custom-field-index <value> --visibility <value> --agent` | Create customfield |
| `nexudus customfields update <id> --name "New Name" --agent` | Update customfield |
| `nexudus customfields delete <id> --yes --agent` | Delete customfield (no prompt) |

#### CustomField list filter options

`--business-id` (long), `--name`, `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--record-type` (enum), `--field-type` (enum), `--coworker-field-position` (enum), `--available-options`, `--allow-multiple-options` (bool), `--custom-field-index` (int), `--from-custom-field-index` (range), `--to-custom-field-index` (range), `--required` (bool), `--group-name`, `--display-in-public-profile` (bool), `--display-in-directory-search` (bool), `--name-in-search`, `--visibility` (enum), `--display-in-sign-up-form` (bool), `--display-in-profile-form` (bool), `--display-in-tour-form` (bool), `--display-in-event-sign-up-form` (bool), `--show-in-booking-form` (bool), `--display-in-product-sign-up-form` (bool), `--display-in-team-sign-up-form` (bool), `--display-in-course-sign-up-form` (bool), `--display-in-tariff-sign-up-form` (bool), `--display-in-booking-sign-up-form` (bool), `--display-in-resource-search` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CustomField create options

`--business-id` (long, required), `--name` (required), `--display-order` (int, required), `--record-type` (enum, required), `--field-type` (enum, required), `--coworker-field-position` (enum, required), `--available-options`, `--allow-multiple-options` (bool), `--custom-field-index` (int, required), `--required` (bool), `--group-name`, `--display-in-public-profile` (bool), `--display-in-directory-search` (bool), `--name-in-search`, `--visibility` (enum, required), `--display-in-sign-up-form` (bool), `--display-in-profile-form` (bool), `--display-in-tour-form` (bool), `--display-in-event-sign-up-form` (bool), `--show-in-booking-form` (bool), `--display-in-product-sign-up-form` (bool), `--display-in-team-sign-up-form` (bool), `--display-in-course-sign-up-form` (bool), `--display-in-tariff-sign-up-form` (bool), `--display-in-booking-sign-up-form` (bool), `--display-in-resource-search` (bool), `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag)

#### CustomField update options

`--business-id` (long), `--name`, `--display-order` (int), `--record-type` (enum), `--field-type` (enum), `--coworker-field-position` (enum), `--available-options`, `--allow-multiple-options` (bool), `--custom-field-index` (int), `--required` (bool), `--group-name`, `--display-in-public-profile` (bool), `--display-in-directory-search` (bool), `--name-in-search`, `--visibility` (enum), `--display-in-sign-up-form` (bool), `--display-in-profile-form` (bool), `--display-in-tour-form` (bool), `--display-in-event-sign-up-form` (bool), `--show-in-booking-form` (bool), `--display-in-product-sign-up-form` (bool), `--display-in-team-sign-up-form` (bool), `--display-in-course-sign-up-form` (bool), `--display-in-tariff-sign-up-form` (bool), `--display-in-booking-sign-up-form` (bool), `--display-in-resource-search` (bool), `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=CustomFields -->
