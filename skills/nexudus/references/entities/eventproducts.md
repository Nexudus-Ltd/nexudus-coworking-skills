# EventProducts

<!-- BEGIN:GENERATED entity=EventProducts -->

An Event Product (internally EventProduct) is a purchasable ticket or RSVP option for an event, with its own price, capacity, availability window, and customer-targeting rules.

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
| `--calendar-event-id` | long | ID of the event this ticket belongs to; the event's location determines the owning location for this record. |
| `--name` | string | Required ticket name shown to customers on the Members Portal and app. |
| `--description` | string | Optional plain-text description of this ticket shown on the Members Portal and app. |
| `--ticket-notes` | string | Optional plain-text notes appended to the confirmation message sent to customers who purchase this ticket. |
| `--visible` | bool | Whether customers can see and purchase this ticket from the Members Portal and app; when false the ticket is hidden from the storefront. |
| `--display-order` | int | Display position of this ticket among the event's tickets; lower values appear first. |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--start-date` | DateTime | UTC start of the inclusive window during which this ticket can be purchased; must not be after EndDate. |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--end-date` | DateTime | UTC end of the inclusive window during which this ticket can be purchased; must not be before StartDate. |
| `--from-end-date` | range | |
| `--to-end-date` | range | |
| `--allocation` | int | Maximum number of this ticket type that can be sold; leave empty for no product-specific cap, while the event's overall capacity still applies. |
| `--from-allocation` | range | |
| `--to-allocation` | range | |
| `--max-tickets-per-attendee` | int | Maximum number of this ticket a single customer can purchase; leave empty for no per-customer limit. |
| `--from-max-tickets-per-attendee` | range | |
| `--to-max-tickets-per-attendee` | range | |
| `--sales` | int | Read-only ticket sales count maintained by event-attendee data and used when calculating remaining capacity; cannot be set directly. |
| `--from-sales` | range | |
| `--to-sales` | range | |
| `--price` | decimal | Price charged per ticket in the selected currency; zero makes the ticket free (RSVP only). |
| `--from-price` | range | |
| `--to-price` | range | |
| `--currency-id` | long | ID of the ISO 4217 currency used for the ticket price. |
| `--currency-code` | string | Display value for Currency.Code. |
| `--tax-rate-id` | long | Optional ID of the tax rate applied when this ticket is invoiced; required when the event's location requires tax rates. |
| `--tax-rate-name` | string | Display value for TaxRate.Name. |
| `--financial-account-id` | long | Optional ID of the financial account used to record ticket revenue; required when the event's location requires financial accounts. |
| `--financial-account-name` | string | Display value for FinancialAccount.Name. |
| `--only-for-contacts` | bool | Whether only contacts, meaning customers without an active contract, can purchase this ticket; this combines with every other targeting rule, so setting it with OnlyForMembers makes the ticket unavailable to all customers. |
| `--only-for-members` | bool | Whether only members, meaning customers with an active contract, can purchase this ticket; this combines with every other targeting rule, so setting it with OnlyForContacts makes the ticket unavailable to all customers. |
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
| `--calendar-event-id` | long, required | ID of the event this ticket belongs to; the event's location determines the owning location for this record. |
| `--name` | string, required | Required ticket name shown to customers on the Members Portal and app. |
| `--description` | string | Optional plain-text description of this ticket shown on the Members Portal and app. |
| `--ticket-notes` | string | Optional plain-text notes appended to the confirmation message sent to customers who purchase this ticket. |
| `--visible` | bool | Whether customers can see and purchase this ticket from the Members Portal and app; when false the ticket is hidden from the storefront. |
| `--display-order` | int, required | Display position of this ticket among the event's tickets; lower values appear first. |
| `--start-date` | DateTime, required | UTC start of the inclusive window during which this ticket can be purchased; must not be after EndDate. |
| `--end-date` | DateTime, required | UTC end of the inclusive window during which this ticket can be purchased; must not be before StartDate. |
| `--allocation` | int | Maximum number of this ticket type that can be sold; leave empty for no product-specific cap, while the event's overall capacity still applies. |
| `--max-tickets-per-attendee` | int | Maximum number of this ticket a single customer can purchase; leave empty for no per-customer limit. |
| `--price` | decimal, required | Price charged per ticket in the selected currency; zero makes the ticket free (RSVP only). |
| `--currency-id` | long, required | ID of the ISO 4217 currency used for the ticket price. |
| `--tax-rate-id` | long | Optional ID of the tax rate applied when this ticket is invoiced; required when the event's location requires tax rates. |
| `--financial-account-id` | long | Optional ID of the financial account used to record ticket revenue; required when the event's location requires financial accounts. |
| `--only-for-contacts` | bool | Whether only contacts, meaning customers without an active contract, can purchase this ticket; this combines with every other targeting rule, so setting it with OnlyForMembers makes the ticket unavailable to all customers. |
| `--only-for-members` | bool | Whether only members, meaning customers with an active contract, can purchase this ticket; this combines with every other targeting rule, so setting it with OnlyForContacts makes the ticket unavailable to all customers. |
| `--tariffs` | list, repeat flag | List of plans a customer's active contract must use to purchase this ticket; an empty list applies no plan restriction, and a non-empty list is enforced in addition to other targeting rules. |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--members` | list, repeat flag | List of specific customers who can purchase this ticket; an empty list applies no customer-specific restriction, and a non-empty list is enforced in addition to plan, team, member, and contact rules. |
| `--added-members` | list, repeat flag | IDs added to the Members relationship. |
| `--removed-members` | list, repeat flag | IDs removed from the Members relationship. |
| `--teams` | list, repeat flag | List of teams a customer must belong to to purchase this ticket; an empty list applies no team restriction, and a non-empty list is enforced in addition to other targeting rules. |
| `--added-teams` | list, repeat flag | IDs added to the Teams relationship. |
| `--removed-teams` | list, repeat flag | IDs removed from the Teams relationship. |

#### EventProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--calendar-event-id` | long | ID of the event this ticket belongs to; the event's location determines the owning location for this record. |
| `--name` | string | Required ticket name shown to customers on the Members Portal and app. |
| `--description` | string | Optional plain-text description of this ticket shown on the Members Portal and app. |
| `--ticket-notes` | string | Optional plain-text notes appended to the confirmation message sent to customers who purchase this ticket. |
| `--visible` | bool | Whether customers can see and purchase this ticket from the Members Portal and app; when false the ticket is hidden from the storefront. |
| `--display-order` | int | Display position of this ticket among the event's tickets; lower values appear first. |
| `--start-date` | DateTime | UTC start of the inclusive window during which this ticket can be purchased; must not be after EndDate. |
| `--end-date` | DateTime | UTC end of the inclusive window during which this ticket can be purchased; must not be before StartDate. |
| `--allocation` | int | Maximum number of this ticket type that can be sold; leave empty for no product-specific cap, while the event's overall capacity still applies. |
| `--max-tickets-per-attendee` | int | Maximum number of this ticket a single customer can purchase; leave empty for no per-customer limit. |
| `--price` | decimal | Price charged per ticket in the selected currency; zero makes the ticket free (RSVP only). |
| `--currency-id` | long | ID of the ISO 4217 currency used for the ticket price. |
| `--tax-rate-id` | long | Optional ID of the tax rate applied when this ticket is invoiced; required when the event's location requires tax rates. |
| `--financial-account-id` | long | Optional ID of the financial account used to record ticket revenue; required when the event's location requires financial accounts. |
| `--only-for-contacts` | bool | Whether only contacts, meaning customers without an active contract, can purchase this ticket; this combines with every other targeting rule, so setting it with OnlyForMembers makes the ticket unavailable to all customers. |
| `--only-for-members` | bool | Whether only members, meaning customers with an active contract, can purchase this ticket; this combines with every other targeting rule, so setting it with OnlyForContacts makes the ticket unavailable to all customers. |
| `--tariffs` | list, repeat flag | List of plans a customer's active contract must use to purchase this ticket; an empty list applies no plan restriction, and a non-empty list is enforced in addition to other targeting rules. |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--members` | list, repeat flag | List of specific customers who can purchase this ticket; an empty list applies no customer-specific restriction, and a non-empty list is enforced in addition to plan, team, member, and contact rules. |
| `--added-members` | list, repeat flag | IDs added to the Members relationship. |
| `--removed-members` | list, repeat flag | IDs removed from the Members relationship. |
| `--teams` | list, repeat flag | List of teams a customer must belong to to purchase this ticket; an empty list applies no team restriction, and a non-empty list is enforced in addition to other targeting rules. |
| `--added-teams` | list, repeat flag | IDs added to the Teams relationship. |
| `--removed-teams` | list, repeat flag | IDs removed from the Teams relationship. |

#### EventProduct PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-names` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus eventproducts update <id> --coworker-full-names "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Members`, `AddedMembers`, `RemovedMembers`, `Teams`, `AddedTeams`, `RemovedTeams`

<!-- END:GENERATED entity=EventProducts -->
