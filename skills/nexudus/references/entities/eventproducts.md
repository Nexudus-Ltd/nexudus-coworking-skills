# EventProducts

<!-- BEGIN:GENERATED entity=EventProducts -->

An Event Product (internally EventProduct) is a purchasable ticket or RSVP option for a calendar event, with its own price, capacity, availability window, and customer-targeting rules.

EventProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eventproducts list --agent` | List all eventproducts |
| `nexudus eventproducts list --id <id> --agent` | Filter by single ID |
| `nexudus eventproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eventproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eventproducts list --calendar-event-id <value> --name <value> --agent` | Filter eventproducts by properties |
| `nexudus eventproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eventproducts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus eventproducts get <id> --agent` | Get single eventproduct |
| `nexudus eventproducts create --calendar-event-id <value> --name <value> --display-order <value> --start-date <value> --end-date <value> --price <value> --currency-id <value> --agent` | Create eventproduct |
| `nexudus eventproducts update <id> --name "New Name" --agent` | Update eventproduct |
| `nexudus eventproducts delete <id> --yes --agent` | Delete eventproduct (no prompt) |

#### EventProduct list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--calendar-event-id` | long | ID of the calendar event this ticket belongs to; the event's location determines the owning location for this record. |
| `--name` | string | Required ticket name shown to customers on the Members Portal and app. |
| `--description` | string | Optional short description of this ticket shown on the Members Portal and app. |
| `--ticket-notes` | string | Optional HTML notes appended to the confirmation message sent to customers who purchase this ticket. |
| `--visible` | bool | Whether customers can see and purchase this ticket from the Members Portal and app; when false the ticket is hidden from the storefront. |
| `--display-order` | int | Display position of this ticket among the event's tickets; lower values appear first. |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--start-date` | DateTime | Start of the window during which this ticket is available for purchase; defaults to the event's publish date when created. |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--end-date` | DateTime | End of the window during which this ticket is available for purchase; defaults to the event's start date when created. |
| `--from-end-date` | range | |
| `--to-end-date` | range | |
| `--allocation` | int | Maximum number of tickets of this type that can be sold; null means unlimited (bounded only by the event's overall capacity). |
| `--from-allocation` | range | |
| `--to-allocation` | range | |
| `--max-tickets-per-attendee` | int | Maximum number of this ticket a single customer can purchase; null means no per-customer limit. |
| `--from-max-tickets-per-attendee` | range | |
| `--to-max-tickets-per-attendee` | range | |
| `--sales` | int | Read-only count of non-cancelled tickets sold for this product; computed from EventAttendee records and cannot be set directly. |
| `--from-sales` | range | |
| `--to-sales` | range | |
| `--price` | decimal | Price charged per ticket in the selected currency; zero makes the ticket free (RSVP only). |
| `--from-price` | range | |
| `--to-price` | range | |
| `--currency-id` | long | ID of the ISO 4217 currency used for the ticket price. |
| `--currency-code` | string | The currency code value for this event product |
| `--tax-rate-id` | long | Optional ID of the tax rate applied when this ticket is invoiced. |
| `--tax-rate-name` | string |  |
| `--financial-account-id` | long | Optional ID of the financial account used to record ticket revenue. |
| `--financial-account-name` | string |  |
| `--only-for-contacts` | bool | Whether this ticket is restricted to contacts (customers without an active contract); do not combine with OnlyForMembers. |
| `--only-for-members` | bool | Whether this ticket is restricted to members (customers with an active contract); when Tariffs is non-empty the member must hold an active contract on one of those plans, and this must not be combined with OnlyForContacts. |
| `--tariff-names` | string | Read-only comma-separated display names of the plans in the Tariffs collection; change the Tariffs collection instead. |
| `--team-names` | string | Read-only comma-separated display names of the teams in the Teams collection; change the Teams collection instead. |
| `--coworker-full-names` | string | Read-only comma-separated display names of the customers in the Members collection; change the Members collection instead. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EventProduct sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `DisplayOrder` ascending. If no `--order-by` is specified, the API returns results ordered by `DisplayOrder` (ascending).

#### EventProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--calendar-event-id` | long, required | ID of the calendar event this ticket belongs to; the event's location determines the owning location for this record. |
| `--name` | string, required | Required ticket name shown to customers on the Members Portal and app. |
| `--description` | string | Optional short description of this ticket shown on the Members Portal and app. |
| `--ticket-notes` | string | Optional HTML notes appended to the confirmation message sent to customers who purchase this ticket. |
| `--visible` | bool | Whether customers can see and purchase this ticket from the Members Portal and app; when false the ticket is hidden from the storefront. |
| `--display-order` | int, required | Display position of this ticket among the event's tickets; lower values appear first. |
| `--start-date` | DateTime, required | Start of the window during which this ticket is available for purchase; defaults to the event's publish date when created. |
| `--end-date` | DateTime, required | End of the window during which this ticket is available for purchase; defaults to the event's start date when created. |
| `--allocation` | int | Maximum number of tickets of this type that can be sold; null means unlimited (bounded only by the event's overall capacity). |
| `--max-tickets-per-attendee` | int | Maximum number of this ticket a single customer can purchase; null means no per-customer limit. |
| `--price` | decimal, required | Price charged per ticket in the selected currency; zero makes the ticket free (RSVP only). |
| `--currency-id` | long, required | ID of the ISO 4217 currency used for the ticket price. |
| `--tax-rate-id` | long | Optional ID of the tax rate applied when this ticket is invoiced. |
| `--financial-account-id` | long | Optional ID of the financial account used to record ticket revenue. |
| `--only-for-contacts` | bool | Whether this ticket is restricted to contacts (customers without an active contract); do not combine with OnlyForMembers. |
| `--only-for-members` | bool | Whether this ticket is restricted to members (customers with an active contract); when Tariffs is non-empty the member must hold an active contract on one of those plans, and this must not be combined with OnlyForContacts. |
| `--tariffs` | list, repeat flag | List of plans whose active members can purchase this ticket when OnlyForMembers is true; an empty list allows members on any plan. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this event product |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this event product |
| `--members` | list, repeat flag | List of specific customers who can purchase this ticket regardless of their plan or contact status; an empty list means no per-customer restriction. |
| `--added-members` | list, repeat flag |  |
| `--removed-members` | list, repeat flag |  |
| `--teams` | list, repeat flag | List of teams whose members can purchase this ticket; an empty list means no team restriction. |
| `--added-teams` | list, repeat flag |  |
| `--removed-teams` | list, repeat flag |  |

#### EventProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--calendar-event-id` | long | ID of the calendar event this ticket belongs to; the event's location determines the owning location for this record. |
| `--name` | string | Required ticket name shown to customers on the Members Portal and app. |
| `--description` | string | Optional short description of this ticket shown on the Members Portal and app. |
| `--ticket-notes` | string | Optional HTML notes appended to the confirmation message sent to customers who purchase this ticket. |
| `--visible` | bool | Whether customers can see and purchase this ticket from the Members Portal and app; when false the ticket is hidden from the storefront. |
| `--display-order` | int | Display position of this ticket among the event's tickets; lower values appear first. |
| `--start-date` | DateTime | Start of the window during which this ticket is available for purchase; defaults to the event's publish date when created. |
| `--end-date` | DateTime | End of the window during which this ticket is available for purchase; defaults to the event's start date when created. |
| `--allocation` | int | Maximum number of tickets of this type that can be sold; null means unlimited (bounded only by the event's overall capacity). |
| `--max-tickets-per-attendee` | int | Maximum number of this ticket a single customer can purchase; null means no per-customer limit. |
| `--price` | decimal | Price charged per ticket in the selected currency; zero makes the ticket free (RSVP only). |
| `--currency-id` | long | ID of the ISO 4217 currency used for the ticket price. |
| `--tax-rate-id` | long | Optional ID of the tax rate applied when this ticket is invoiced. |
| `--financial-account-id` | long | Optional ID of the financial account used to record ticket revenue. |
| `--only-for-contacts` | bool | Whether this ticket is restricted to contacts (customers without an active contract); do not combine with OnlyForMembers. |
| `--only-for-members` | bool | Whether this ticket is restricted to members (customers with an active contract); when Tariffs is non-empty the member must hold an active contract on one of those plans, and this must not be combined with OnlyForContacts. |
| `--tariffs` | list, repeat flag | List of plans whose active members can purchase this ticket when OnlyForMembers is true; an empty list allows members on any plan. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this event product |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this event product |
| `--members` | list, repeat flag | List of specific customers who can purchase this ticket regardless of their plan or contact status; an empty list means no per-customer restriction. |
| `--added-members` | list, repeat flag |  |
| `--removed-members` | list, repeat flag |  |
| `--teams` | list, repeat flag | List of teams whose members can purchase this ticket; an empty list means no team restriction. |
| `--added-teams` | list, repeat flag |  |
| `--removed-teams` | list, repeat flag |  |

#### EventProduct PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-names` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus eventproducts update <id> --coworker-full-names "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Members`, `AddedMembers`, `RemovedMembers`, `Teams`, `AddedTeams`, `RemovedTeams`

<!-- END:GENERATED entity=EventProducts -->
