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
| `nexudus customfields list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus customfields get <id> --agent` | Get single customfield |
| `nexudus customfields create --business-id <value> --name <value> --display-order <value> --record-type <value> --field-type <value> --coworker-field-position <value> --custom-field-index <value> --visibility <value> --agent` | Create customfield |
| `nexudus customfields update <id> --name "New Name" --agent` | Update customfield |
| `nexudus customfields delete <id> --yes --agent` | Delete customfield (no prompt) |

#### CustomField list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | Business this custom field belongs to |
| `--name` | string | Field label displayed to users |
| `--display-order` | int | Sort order when multiple custom fields are shown together |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--record-type` | enum | Entity type this field applies to: Coworker, Team, Booking, Product, Resource, etc. |
| `--field-type` | enum | Data type of the field: Text, LongText, Boolean, Dropdown, Date, Integer, or Decimal |
| `--coworker-field-position` | enum | Tab where this field appears on the coworker record: General, Contact, Profile, Billing, Access, or Notes |
| `--available-options` | string | Comma-separated list of choices for Dropdown fields |
| `--allow-multiple-options` | bool | Whether multiple options can be selected for Dropdown fields |
| `--custom-field-index` | int | Unique index identifying this field within its record type and business |
| `--from-custom-field-index` | range | |
| `--to-custom-field-index` | range | |
| `--required` | bool | Whether a value must be provided when saving the parent entity |
| `--group-name` | string | Optional group name used to visually group related custom fields together |
| `--display-in-public-profile` | bool | Show this field on the coworker's public profile page |
| `--display-in-directory-search` | bool | Show this field as a filter in the member directory search |
| `--name-in-search` | string | Alternative label shown when this field appears in directory search filters |
| `--visibility` | enum | Visibility level: Visible (editable by customer), ReadOnly (shown but not editable), or Internal (admin only) |
| `--display-in-sign-up-form` | bool | Show this field on the member sign-up form |
| `--display-in-profile-form` | bool | Show this field on the member profile edit form |
| `--display-in-tour-form` | bool | Show this field on the tour booking form |
| `--display-in-event-sign-up-form` | bool | Show this field on the event sign-up form |
| `--show-in-booking-form` | bool | Show this field on the resource booking form |
| `--display-in-product-sign-up-form` | bool | Show this field on the product purchase form |
| `--display-in-team-sign-up-form` | bool | Show this field on the team sign-up form |
| `--display-in-course-sign-up-form` | bool | Show this field on the course sign-up form |
| `--display-in-tariff-sign-up-form` | bool | Show this field on the pricing plan (tariff) sign-up form |
| `--display-in-booking-sign-up-form` | bool | Show this field on the booking sign-up form |
| `--display-in-resource-search` | bool | Show this field as a filter in resource search |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CustomField sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CustomField create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | Business this custom field belongs to |
| `--name` | string, required | Field label displayed to users |
| `--display-order` | int, required | Sort order when multiple custom fields are shown together |
| `--record-type` | enum, required | Entity type this field applies to: Coworker, Team, Booking, Product, Resource, etc. |
| `--field-type` | enum, required | Data type of the field: Text, LongText, Boolean, Dropdown, Date, Integer, or Decimal |
| `--coworker-field-position` | enum, required | Tab where this field appears on the coworker record: General, Contact, Profile, Billing, Access, or Notes |
| `--available-options` | string | Comma-separated list of choices for Dropdown fields |
| `--allow-multiple-options` | bool | Whether multiple options can be selected for Dropdown fields |
| `--custom-field-index` | int, required | Unique index identifying this field within its record type and business |
| `--required` | bool | Whether a value must be provided when saving the parent entity |
| `--group-name` | string | Optional group name used to visually group related custom fields together |
| `--display-in-public-profile` | bool | Show this field on the coworker's public profile page |
| `--display-in-directory-search` | bool | Show this field as a filter in the member directory search |
| `--name-in-search` | string | Alternative label shown when this field appears in directory search filters |
| `--visibility` | enum, required | Visibility level: Visible (editable by customer), ReadOnly (shown but not editable), or Internal (admin only) |
| `--display-in-sign-up-form` | bool | Show this field on the member sign-up form |
| `--display-in-profile-form` | bool | Show this field on the member profile edit form |
| `--display-in-tour-form` | bool | Show this field on the tour booking form |
| `--display-in-event-sign-up-form` | bool | Show this field on the event sign-up form |
| `--show-in-booking-form` | bool | Show this field on the resource booking form |
| `--display-in-product-sign-up-form` | bool | Show this field on the product purchase form |
| `--display-in-team-sign-up-form` | bool | Show this field on the team sign-up form |
| `--display-in-course-sign-up-form` | bool | Show this field on the course sign-up form |
| `--display-in-tariff-sign-up-form` | bool | Show this field on the pricing plan (tariff) sign-up form |
| `--display-in-booking-sign-up-form` | bool | Show this field on the booking sign-up form |
| `--display-in-resource-search` | bool | Show this field as a filter in resource search |
| `--resources` | list, repeat flag | Resources this custom field is linked to (for FloorPlanDesk or Resource record types) |
| `--added-resources` | list, repeat flag | The added resources value for this custom field |
| `--removed-resources` | list, repeat flag | The removed resources value for this custom field |

#### CustomField update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | Business this custom field belongs to |
| `--name` | string | Field label displayed to users |
| `--display-order` | int | Sort order when multiple custom fields are shown together |
| `--record-type` | enum | Entity type this field applies to: Coworker, Team, Booking, Product, Resource, etc. |
| `--field-type` | enum | Data type of the field: Text, LongText, Boolean, Dropdown, Date, Integer, or Decimal |
| `--coworker-field-position` | enum | Tab where this field appears on the coworker record: General, Contact, Profile, Billing, Access, or Notes |
| `--available-options` | string | Comma-separated list of choices for Dropdown fields |
| `--allow-multiple-options` | bool | Whether multiple options can be selected for Dropdown fields |
| `--custom-field-index` | int | Unique index identifying this field within its record type and business |
| `--required` | bool | Whether a value must be provided when saving the parent entity |
| `--group-name` | string | Optional group name used to visually group related custom fields together |
| `--display-in-public-profile` | bool | Show this field on the coworker's public profile page |
| `--display-in-directory-search` | bool | Show this field as a filter in the member directory search |
| `--name-in-search` | string | Alternative label shown when this field appears in directory search filters |
| `--visibility` | enum | Visibility level: Visible (editable by customer), ReadOnly (shown but not editable), or Internal (admin only) |
| `--display-in-sign-up-form` | bool | Show this field on the member sign-up form |
| `--display-in-profile-form` | bool | Show this field on the member profile edit form |
| `--display-in-tour-form` | bool | Show this field on the tour booking form |
| `--display-in-event-sign-up-form` | bool | Show this field on the event sign-up form |
| `--show-in-booking-form` | bool | Show this field on the resource booking form |
| `--display-in-product-sign-up-form` | bool | Show this field on the product purchase form |
| `--display-in-team-sign-up-form` | bool | Show this field on the team sign-up form |
| `--display-in-course-sign-up-form` | bool | Show this field on the course sign-up form |
| `--display-in-tariff-sign-up-form` | bool | Show this field on the pricing plan (tariff) sign-up form |
| `--display-in-booking-sign-up-form` | bool | Show this field on the booking sign-up form |
| `--display-in-resource-search` | bool | Show this field as a filter in resource search |
| `--resources` | list, repeat flag | Resources this custom field is linked to (for FloorPlanDesk or Resource record types) |
| `--added-resources` | list, repeat flag | The added resources value for this custom field |
| `--removed-resources` | list, repeat flag | The removed resources value for this custom field |

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
