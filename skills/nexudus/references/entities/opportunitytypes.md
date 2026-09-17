# OpportunityTypes

<!-- BEGIN:GENERATED entity=OpportunityTypes -->

An opportunity type (OpportunityType) is a location-scoped category applied to CRM opportunities, such as 'New Member', 'Event Booking' or 'Office Rental', used to classify and filter them. A type can also carry a notes template that pre-fills the notes of opportunities created with it.

OpportunityTypes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus opportunitytypes list --agent` | List all opportunitytypes |
| `nexudus opportunitytypes list --id <id> --agent` | Filter by single ID |
| `nexudus opportunitytypes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus opportunitytypes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus opportunitytypes list --business-id <value> --name <value> --agent` | Filter opportunitytypes by properties |
| `nexudus opportunitytypes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus opportunitytypes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus opportunitytypes get <id> --agent` | Get single opportunitytype |
| `nexudus opportunitytypes create --business-id <value> --name <value> --agent` | Create opportunitytype |
| `nexudus opportunitytypes update <id> --name "New Name" --agent` | Update opportunitytype |
| `nexudus opportunitytypes delete <id> --yes --agent` | Delete opportunitytype (no prompt) |

#### OpportunityType list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this opportunity type; required, supplied from the current location when creating, and only opportunity types from locations the user is linked to are returned. |
| `--name` | string | Required localized name of this opportunity category (up to 254 characters), such as 'New Member', 'Event Booking' or 'Office Rental'; it identifies the type when classifying an opportunity and is what opportunity lists show as the type name. |
| `--notes-template` | string | Optional boilerplate note text copied into the Notes of an opportunity that uses this type: the admin UI pre-fills it only when the opportunity's notes are still empty, and the opportunity CSV importer replaces the imported notes with it whenever it is not blank. Plain multi-line text copied verbatim, with no merge fields or placeholder substitution. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### OpportunityType sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### OpportunityType create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this opportunity type; required, supplied from the current location when creating, and only opportunity types from locations the user is linked to are returned. |
| `--name` | string, required | Required localized name of this opportunity category (up to 254 characters), such as 'New Member', 'Event Booking' or 'Office Rental'; it identifies the type when classifying an opportunity and is what opportunity lists show as the type name. |
| `--notes-template` | string | Optional boilerplate note text copied into the Notes of an opportunity that uses this type: the admin UI pre-fills it only when the opportunity's notes are still empty, and the opportunity CSV importer replaces the imported notes with it whenever it is not blank. Plain multi-line text copied verbatim, with no merge fields or placeholder substitution. |

#### OpportunityType update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this opportunity type; required, supplied from the current location when creating, and only opportunity types from locations the user is linked to are returned. |
| `--name` | string | Required localized name of this opportunity category (up to 254 characters), such as 'New Member', 'Event Booking' or 'Office Rental'; it identifies the type when classifying an opportunity and is what opportunity lists show as the type name. |
| `--notes-template` | string | Optional boilerplate note text copied into the Notes of an opportunity that uses this type: the admin UI pre-fills it only when the opportunity's notes are still empty, and the opportunity CSV importer replaces the imported notes with it whenever it is not blank. Plain multi-line text copied verbatim, with no merge fields or placeholder substitution. |

<!-- END:GENERATED entity=OpportunityTypes -->
