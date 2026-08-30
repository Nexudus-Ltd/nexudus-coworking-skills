# CustomFields

<!-- BEGIN:GENERATED entity=CustomFields -->

A custom field defines an additional data field for a selected Nexudus record type, including customers, plans, bookings, products, and resources. It controls the input type, validation, visibility, placement, and supported public forms for values stored with those records.

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
| `nexudus customfields create --business-id <value> --name <value> --display-order <value> --record-type <value> --field-type <value> --coworker-field-position <value> --visibility <value> --agent` | Create customfield |
| `nexudus customfields update <id> --name "New Name" --agent` | Update customfield |
| `nexudus customfields delete <id> --yes --agent` | Delete customfield (no prompt) |

#### CustomField list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this custom field. Customer fields must belong to the top-level location; other record types are available across the location network. |
| `--name` | string | Required label shown for this custom field. It must be unique across the location network unless it is the linked resource/booking counterpart. |
| `--display-order` | int | Numeric display order for this field among the location's custom fields; lower values appear first and the server normalizes the ordering after changes. |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--record-type` | enum | Record type this field collects data for: Coworker, Team, FloorPlanDesk, CrmOpportunity, Visitor, Proposal, CoworkerInternal, HelpDeskMessage, HelpDeskDepartment, Product, Booking, CoworkerInvoice, Business, CoworkerContract, Tariff, Resource, FloorPlan, InventoryAsset, or Events. A Coworker field cannot later be changed to another type. |
| `--field-type` | enum | Input type and validation for captured values: Text, LongText, Boolean, Dropdown, Date, Integer, or Decimal. AvailableOptions is retained only for Dropdown. |
| `--coworker-field-position` | enum | Customer-record tab where the field is placed: General, Contact, Profile, Billing, Access, or Notes. This applies when RecordType is Coworker. |
| `--available-options` | string | Comma-separated permitted choices for a Dropdown field; submitted values must exactly match these trimmed options. The server clears this value for every other FieldType. |
| `--allow-multiple-options` | bool | Whether a Dropdown field accepts more than one comma-separated choice. This setting is meaningful only when FieldType is Dropdown. |
| `--custom-field-index` | int | Server-assigned identifier used to map a customer field to its CustomFields array value. The server assigns it for Coworker fields; do not set it manually. |
| `--from-custom-field-index` | range | |
| `--to-custom-field-index` | range | |
| `--required` | bool | Whether a non-empty value is required when this field is submitted on its parent record. ReadOnly fields are automatically made not required. |
| `--group-name` | string | Optional label used to group related custom fields in supported forms. |
| `--display-in-public-profile` | bool | Whether this customer field is shown on the customer's public profile. |
| `--display-in-directory-search` | bool | Whether this customer field is offered as a filter in the public customer directory search. |
| `--name-in-search` | string | Optional label shown for this field in customer-directory search; use it when the normal field label needs different search wording. |
| `--visibility` | enum | Audience and editability: Visible allows customer editing, ReadOnly shows the field without customer editing, and Internal excludes it from public-facing field lists. ReadOnly cannot be Required. |
| `--display-in-sign-up-form` | bool | Whether this custom field is shown on the customer sign-up form. |
| `--display-in-profile-form` | bool | Whether this custom field is shown on the customer profile-edit form. |
| `--display-in-tour-form` | bool | Whether this custom field is shown on the tour request form. |
| `--display-in-event-sign-up-form` | bool | Whether this custom field is shown when a customer registers for an event. |
| `--show-in-booking-form` | bool | Whether this field is shown on a resource booking form. For Resource record types, enabling this creates or synchronizes a linked Booking custom field. |
| `--display-in-product-sign-up-form` | bool | Whether this custom field is shown when a customer buys a product. |
| `--display-in-team-sign-up-form` | bool | Whether this custom field is shown on the team sign-up form. |
| `--display-in-course-sign-up-form` | bool | Whether this custom field is shown on the course sign-up form. |
| `--display-in-tariff-sign-up-form` | bool | Whether this custom field is shown when a customer signs up for a plan (Tariff). |
| `--display-in-booking-sign-up-form` | bool | Whether this custom field is shown on the booking sign-up form. |
| `--display-in-resource-search` | bool | Whether this custom field is offered as a filter in resource search. |
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
| `--business-id` | long, required | ID of the location that owns this custom field. Customer fields must belong to the top-level location; other record types are available across the location network. |
| `--name` | string, required | Required label shown for this custom field. It must be unique across the location network unless it is the linked resource/booking counterpart. |
| `--display-order` | int, required | Numeric display order for this field among the location's custom fields; lower values appear first and the server normalizes the ordering after changes. |
| `--record-type` | enum, required | Record type this field collects data for: Coworker, Team, FloorPlanDesk, CrmOpportunity, Visitor, Proposal, CoworkerInternal, HelpDeskMessage, HelpDeskDepartment, Product, Booking, CoworkerInvoice, Business, CoworkerContract, Tariff, Resource, FloorPlan, InventoryAsset, or Events. A Coworker field cannot later be changed to another type. |
| `--field-type` | enum, required | Input type and validation for captured values: Text, LongText, Boolean, Dropdown, Date, Integer, or Decimal. AvailableOptions is retained only for Dropdown. |
| `--coworker-field-position` | enum, required | Customer-record tab where the field is placed: General, Contact, Profile, Billing, Access, or Notes. This applies when RecordType is Coworker. |
| `--available-options` | string | Comma-separated permitted choices for a Dropdown field; submitted values must exactly match these trimmed options. The server clears this value for every other FieldType. |
| `--allow-multiple-options` | bool | Whether a Dropdown field accepts more than one comma-separated choice. This setting is meaningful only when FieldType is Dropdown. |
| `--required` | bool | Whether a non-empty value is required when this field is submitted on its parent record. ReadOnly fields are automatically made not required. |
| `--group-name` | string | Optional label used to group related custom fields in supported forms. |
| `--display-in-public-profile` | bool | Whether this customer field is shown on the customer's public profile. |
| `--display-in-directory-search` | bool | Whether this customer field is offered as a filter in the public customer directory search. |
| `--name-in-search` | string | Optional label shown for this field in customer-directory search; use it when the normal field label needs different search wording. |
| `--visibility` | enum, required | Audience and editability: Visible allows customer editing, ReadOnly shows the field without customer editing, and Internal excludes it from public-facing field lists. ReadOnly cannot be Required. |
| `--display-in-sign-up-form` | bool | Whether this custom field is shown on the customer sign-up form. |
| `--display-in-profile-form` | bool | Whether this custom field is shown on the customer profile-edit form. |
| `--display-in-tour-form` | bool | Whether this custom field is shown on the tour request form. |
| `--display-in-event-sign-up-form` | bool | Whether this custom field is shown when a customer registers for an event. |
| `--show-in-booking-form` | bool | Whether this field is shown on a resource booking form. For Resource record types, enabling this creates or synchronizes a linked Booking custom field. |
| `--display-in-product-sign-up-form` | bool | Whether this custom field is shown when a customer buys a product. |
| `--display-in-team-sign-up-form` | bool | Whether this custom field is shown on the team sign-up form. |
| `--display-in-course-sign-up-form` | bool | Whether this custom field is shown on the course sign-up form. |
| `--display-in-tariff-sign-up-form` | bool | Whether this custom field is shown when a customer signs up for a plan (Tariff). |
| `--display-in-booking-sign-up-form` | bool | Whether this custom field is shown on the booking sign-up form. |
| `--display-in-resource-search` | bool | Whether this custom field is offered as a filter in resource search. |
| `--resources` | list, repeat flag | List of resources this Resource-record custom field applies to when it is shown in booking. An empty list means it applies to every resource; setting resources restricts it to those resources. |
| `--added-resources` | list, repeat flag | The added resources value for this custom field |
| `--removed-resources` | list, repeat flag | The removed resources value for this custom field |

#### CustomField update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this custom field. Customer fields must belong to the top-level location; other record types are available across the location network. |
| `--name` | string | Required label shown for this custom field. It must be unique across the location network unless it is the linked resource/booking counterpart. |
| `--display-order` | int | Numeric display order for this field among the location's custom fields; lower values appear first and the server normalizes the ordering after changes. |
| `--record-type` | enum | Record type this field collects data for: Coworker, Team, FloorPlanDesk, CrmOpportunity, Visitor, Proposal, CoworkerInternal, HelpDeskMessage, HelpDeskDepartment, Product, Booking, CoworkerInvoice, Business, CoworkerContract, Tariff, Resource, FloorPlan, InventoryAsset, or Events. A Coworker field cannot later be changed to another type. |
| `--field-type` | enum | Input type and validation for captured values: Text, LongText, Boolean, Dropdown, Date, Integer, or Decimal. AvailableOptions is retained only for Dropdown. |
| `--coworker-field-position` | enum | Customer-record tab where the field is placed: General, Contact, Profile, Billing, Access, or Notes. This applies when RecordType is Coworker. |
| `--available-options` | string | Comma-separated permitted choices for a Dropdown field; submitted values must exactly match these trimmed options. The server clears this value for every other FieldType. |
| `--allow-multiple-options` | bool | Whether a Dropdown field accepts more than one comma-separated choice. This setting is meaningful only when FieldType is Dropdown. |
| `--required` | bool | Whether a non-empty value is required when this field is submitted on its parent record. ReadOnly fields are automatically made not required. |
| `--group-name` | string | Optional label used to group related custom fields in supported forms. |
| `--display-in-public-profile` | bool | Whether this customer field is shown on the customer's public profile. |
| `--display-in-directory-search` | bool | Whether this customer field is offered as a filter in the public customer directory search. |
| `--name-in-search` | string | Optional label shown for this field in customer-directory search; use it when the normal field label needs different search wording. |
| `--visibility` | enum | Audience and editability: Visible allows customer editing, ReadOnly shows the field without customer editing, and Internal excludes it from public-facing field lists. ReadOnly cannot be Required. |
| `--display-in-sign-up-form` | bool | Whether this custom field is shown on the customer sign-up form. |
| `--display-in-profile-form` | bool | Whether this custom field is shown on the customer profile-edit form. |
| `--display-in-tour-form` | bool | Whether this custom field is shown on the tour request form. |
| `--display-in-event-sign-up-form` | bool | Whether this custom field is shown when a customer registers for an event. |
| `--show-in-booking-form` | bool | Whether this field is shown on a resource booking form. For Resource record types, enabling this creates or synchronizes a linked Booking custom field. |
| `--display-in-product-sign-up-form` | bool | Whether this custom field is shown when a customer buys a product. |
| `--display-in-team-sign-up-form` | bool | Whether this custom field is shown on the team sign-up form. |
| `--display-in-course-sign-up-form` | bool | Whether this custom field is shown on the course sign-up form. |
| `--display-in-tariff-sign-up-form` | bool | Whether this custom field is shown when a customer signs up for a plan (Tariff). |
| `--display-in-booking-sign-up-form` | bool | Whether this custom field is shown on the booking sign-up form. |
| `--display-in-resource-search` | bool | Whether this custom field is offered as a filter in resource search. |
| `--resources` | list, repeat flag | List of resources this Resource-record custom field applies to when it is shown in booking. An empty list means it applies to every resource; setting resources restricts it to those resources. |
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
