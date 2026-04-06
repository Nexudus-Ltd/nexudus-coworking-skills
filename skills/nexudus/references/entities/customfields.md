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

`--business-id`, `--name`, `--display-order`, `--from-display-order` (range), `--to-display-order` (range), `--record-type`, `--field-type`, `--coworker-field-position`, `--available-options`, `--allow-multiple-options`, `--custom-field-index`, `--from-custom-field-index` (range), `--to-custom-field-index` (range), `--required`, `--group-name`, `--display-in-public-profile`, `--display-in-directory-search`, `--name-in-search`, `--visibility`, `--display-in-sign-up-form`, `--display-in-profile-form`, `--display-in-tour-form`, `--display-in-event-sign-up-form`, `--show-in-booking-form`, `--display-in-product-sign-up-form`, `--display-in-team-sign-up-form`, `--display-in-course-sign-up-form`, `--display-in-tariff-sign-up-form`, `--display-in-booking-sign-up-form`, `--display-in-resource-search`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CustomField create options

`--business-id` (required), `--name` (required), `--display-order` (required), `--record-type` (required), `--field-type` (required), `--coworker-field-position` (required), `--available-options`, `--allow-multiple-options`, `--custom-field-index` (required), `--required`, `--group-name`, `--display-in-public-profile`, `--display-in-directory-search`, `--name-in-search`, `--visibility` (required), `--display-in-sign-up-form`, `--display-in-profile-form`, `--display-in-tour-form`, `--display-in-event-sign-up-form`, `--show-in-booking-form`, `--display-in-product-sign-up-form`, `--display-in-team-sign-up-form`, `--display-in-course-sign-up-form`, `--display-in-tariff-sign-up-form`, `--display-in-booking-sign-up-form`, `--display-in-resource-search`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag)

#### CustomField update options

`--business-id`, `--name`, `--display-order`, `--record-type`, `--field-type`, `--coworker-field-position`, `--available-options`, `--allow-multiple-options`, `--custom-field-index`, `--required`, `--group-name`, `--display-in-public-profile`, `--display-in-directory-search`, `--name-in-search`, `--visibility`, `--display-in-sign-up-form`, `--display-in-profile-form`, `--display-in-tour-form`, `--display-in-event-sign-up-form`, `--show-in-booking-form`, `--display-in-product-sign-up-form`, `--display-in-team-sign-up-form`, `--display-in-course-sign-up-form`, `--display-in-tariff-sign-up-form`, `--display-in-booking-sign-up-form`, `--display-in-resource-search`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=CustomFields -->
