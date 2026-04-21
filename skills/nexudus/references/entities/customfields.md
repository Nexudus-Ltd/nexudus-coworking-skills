# CustomFields

<!-- BEGIN:GENERATED entity=CustomFields -->

A **CustomField** defines an additional field available for a specific entity type. Nexudus supports attaching arbitrary data to any entity type via the CustomFields array.

Each custom field targets a single `RecordType` (e.g. Coworker, Team, Booking, Product) and has a `FieldType` that determines how the value is captured and stored (Text, LongText, Boolean, Dropdown, Date, Integer, or Decimal).

For Dropdown fields, populate `AvailableOptions` with a comma-separated list of choices. Set `AllowMultipleOptions` to `true` to let users select more than one.

The `CustomFieldIndex` uniquely identifies the field within its record type and business, and is used to map values in the entity's `CustomFields` array.

Use the `Visibility` property to control whether the field is Visible, ReadOnly, or Internal (admin-only). The various `DisplayIn*` flags control where the field appears: sign-up forms, profile forms, tour forms, event sign-up, booking forms, directory search, and public profiles.

Custom fields targeting the Coworker record type can be placed in a specific tab using `CoworkerFieldPosition` (General, Contact, Profile, Billing, Access, or Notes).

When `RecordType` is FloorPlanDesk or Resource, link specific resources via the `Resources` many-to-many list.

CustomFields support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus customfields list --agent` | List all customfields |
| `nexudus customfields list --id <id> --agent` | Filter by single ID |
| `nexudus customfields list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus customfields list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus customfields list --name <value> --agent` | Filter customfields by properties |
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

### CustomField (key fields)

`Id`, `Name`

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`

#### CustomField enum values

| Option | Valid values |
| ------ | ------------ |
| `--record-type` | `1` Coworker, `2` Team, `3` FloorPlanDesk, `4` CrmOpportunity, `5` Visitor, `6` Proposal, `7` CoworkerInternal, `8` HelpDeskMessage, `9` HelpDeskDepartment, `10` Product, `11` Booking, `12` CoworkerInvoice, `13` Business, `14` CoworkerContract, `15` Tariff, `16` Resource, `17` FloorPlan, `18` InventoryAsset |
| `--field-type` | `1` Text, `2` LongText, `3` Boolean, `4` Dropdown, `5` Date, `6` Integer, `7` Decimal |
| `--coworker-field-position` | `1` General, `2` Contact, `3` Profile, `4` Billing, `5` Access, `6` Notes |
| `--visibility` | `1` Visible, `2` ReadOnly, `3` Internal |

<!-- END:GENERATED entity=CustomFields -->
