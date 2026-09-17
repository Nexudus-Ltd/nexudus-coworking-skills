# Reminders

<!-- BEGIN:GENERATED entity=Reminders -->

A reminder is an automated message a location sends when a trigger fires, such as a fixed date, a number of days after sign-up or a booking, a number of days before a contract renews or ends, a product purchase or a customer's birthday. Its audience is either a single customer or a combination of members, contacts and specific plans, optionally extended to the locations inside the owning one, and it is delivered as the built-in reminder email, a message macro or a survey.

Reminders support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus reminders list --agent` | List all reminders |
| `nexudus reminders list --id <id> --agent` | Filter by single ID |
| `nexudus reminders list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus reminders list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus reminders list --business-id <value> --business-name <value> --agent` | Filter reminders by properties |
| `nexudus reminders list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reminders list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus reminders get <id> --agent` | Get single reminder |
| `nexudus reminders create --business-id <value> --name <value> --reminder-type <value> --reminder-action <value> --agent` | Create reminder |
| `nexudus reminders update <id> --name "New Name" --agent` | Update reminder |
| `nexudus reminders delete <id> --yes --agent` | Delete reminder (no prompt) |

#### Reminder list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this reminder; customers are matched by their home location, and only locations inside this one are also matched when ForAllChildLocations is on. |
| `--business-name` | string | Display value for Business.Name. |
| `--name` | string | Required internal name used to identify the reminder in admin lists and search; it is never shown to the customer when a message macro or a survey supplies the message content. |
| `--for-all-contacts` | bool | Whether contacts (customers with no active contract) are in the audience; set it together with ForAllMembers to target every customer. The reminder is never processed while this, ForAllMembers, OnlySendToTeamPayingMembers and Coworker are all empty. |
| `--for-all-members` | bool | Whether members (customers with an active contract) are in the audience; combine it with Tariffs to restrict delivery to specific plans, or set it together with ForAllContacts to target every customer. |
| `--for-all-child-locations` | bool | Whether customers whose home location is any location inside the owning location are also included; when off, only customers whose home location is the owning location itself receive the reminder. |
| `--coworker-id` | long | Optional ID of the single customer this reminder targets; when set it replaces the ForAllMembers, ForAllContacts and Tariffs audience filters, enables the reminder on its own and disables the BlockingPeriodMinutes throttle, while OnlySendToActiveCoworkers and OnlySendToTeamPayingMembers still apply. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--reminder-type` | enum | The event that triggers the reminder, and it decides which companion field supplies the offset: FixedDate uses ReminderDate; DaysAfterSignUp, LastActivity and DaysAfterFirstContractStartDate use DaysAfterSignup; DaysAfterRenewal, AfterABooking, DueInvoice and DaysAfterDeliveryNotCollected use DaysAfterRenewal; DaysBeforeRenewal, DaysBeforeCancellation, DaysBeforeTerm and DaysBeforeContractStarts use DaysBeforeRenewal; ProductPurchase and ProductAddedToBooking need Product; AfterABooking can be narrowed with Resources. Birthday, OnFirstCheckIn, OnSignUpFormSubmitted, InvoiceFirstPaid, RegularBooking, RegularBookerStoppedBooking, StoppedBooking and SingleBooking need no offset. Event-driven types (ProductPurchase, ProductAddedToBooking, OnFirstCheckIn, OnSignUpFormSubmitted, InvoiceFirstPaid) run right after the event; every other type is evaluated once a day at around 8am in the location's local time. |
| `--reminder-date` | DateTime | Date the reminder is sent, used only by the FixedDate type and ignored by every other type; stored in UTC and compared in the location's local time, so it fires on that local calendar day and never before its time of day. |
| `--from-reminder-date` | range | |
| `--to-reminder-date` | range | |
| `--days-after-signup` | int | Whole number of days after the trigger date, required and not negative for the DaysAfterSignUp, LastActivity and DaysAfterFirstContractStartDate types and cleared automatically for every other type. DaysAfterSignUp counts from the customer's registration date, LastActivity from their last access and DaysAfterFirstContractStartDate from their first contract start date. |
| `--from-days-after-signup` | range | |
| `--to-days-after-signup` | range | |
| `--product-id` | long | ID of the product whose purchase triggers the reminder; required by the ProductPurchase and ProductAddedToBooking types and ignored by every other type. |
| `--product-name` | string | Display value for Product.Name. |
| `--survey-id` | long | ID of the survey sent to the customer when ReminderAction is SendSurvey; nothing is sent while it is empty, and it is ignored for the other actions. |
| `--survey-name` | string | Display value for Survey.Name. |
| `--days-after-renewal` | int | Whole number of days after the trigger event, required and not negative for the DaysAfterRenewal, AfterABooking, DueInvoice and DaysAfterDeliveryNotCollected types and cleared automatically for every other type. It counts from the contract renewal date, the end of the booking, the invoice due date or the delivery reception date respectively. |
| `--from-days-after-renewal` | range | |
| `--to-days-after-renewal` | range | |
| `--days-before-renewal` | int | Whole number of days before the trigger date, required and not negative for the DaysBeforeRenewal, DaysBeforeCancellation, DaysBeforeTerm and DaysBeforeContractStarts types and cleared automatically for every other type. It counts back from the next invoice date, the contract cancellation date, the contract term end date or the contract start date respectively. |
| `--from-days-before-renewal` | range | |
| `--to-days-before-renewal` | range | |
| `--reminder-action` | enum | How the reminder is delivered: SendEmail sends the built-in reminder email, SendCannedMessage sends the message macro named in CannedResponse, and SendSurvey sends the survey named in Survey. |
| `--email` | string | Optional fixed email address notified instead of the customer, normally a staff inbox; leave it empty to send the message to the customer's own address and record it in their message history. It is rejected on save for the RegularBooking, RegularBookerStoppedBooking, StoppedBooking, SingleBooking and DaysAfterDeliveryNotCollected types, which can only be sent to the customer. |
| `--canned-response-id` | long | ID of the message macro sent when ReminderAction is SendCannedMessage; nothing is sent while it is empty, and the message subject falls back to the macro name when the macro has none. Messages for the DaysBeforeRenewal and DueInvoice types are addressed to the customer's billing email. |
| `--canned-response-name` | string | Display value for CannedResponse.Name. |
| `--next-process-time` | DateTime | Read-only scheduler state in UTC holding the next time the reminder job will evaluate this reminder; the job moves it to the next 8am in the location's local time after each run, or to ReminderDate while a fixed-date reminder is still pending. Change ReminderType or ReminderDate to alter when the reminder runs. |
| `--from-next-process-time` | range | |
| `--to-next-process-time` | range | |
| `--only-send-to-team-paying-members` | bool | Whether the audience is restricted to customers who are the designated paying member of a team invoiced as a single invoice; it enables the reminder on its own, and every other recipient is skipped while it is on. |
| `--only-send-to-active-coworkers` | bool | Whether customers whose record is not active are skipped; it applies on top of every other audience setting, including a single customer named in Coworker. |
| `--blocking-period-minutes` | int | Minimum number of minutes that must pass before the same customer can receive this reminder again, measured against the reminder's own audit records; must not be negative, empty means no throttling, and it is ignored when Coworker targets a single customer. |
| `--from-blocking-period-minutes` | range | |
| `--to-blocking-period-minutes` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Reminder sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Reminder create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this reminder; customers are matched by their home location, and only locations inside this one are also matched when ForAllChildLocations is on. |
| `--name` | string, required | Required internal name used to identify the reminder in admin lists and search; it is never shown to the customer when a message macro or a survey supplies the message content. |
| `--for-all-contacts` | bool | Whether contacts (customers with no active contract) are in the audience; set it together with ForAllMembers to target every customer. The reminder is never processed while this, ForAllMembers, OnlySendToTeamPayingMembers and Coworker are all empty. |
| `--for-all-members` | bool | Whether members (customers with an active contract) are in the audience; combine it with Tariffs to restrict delivery to specific plans, or set it together with ForAllContacts to target every customer. |
| `--for-all-child-locations` | bool | Whether customers whose home location is any location inside the owning location are also included; when off, only customers whose home location is the owning location itself receive the reminder. |
| `--coworker-id` | long | Optional ID of the single customer this reminder targets; when set it replaces the ForAllMembers, ForAllContacts and Tariffs audience filters, enables the reminder on its own and disables the BlockingPeriodMinutes throttle, while OnlySendToActiveCoworkers and OnlySendToTeamPayingMembers still apply. |
| `--tariffs` | list, repeat flag | List of plan IDs the customer must hold a contract for; an empty list means no plan restriction. It is matched against the customer's active contracts (their non-cancelled contracts for the DaysBeforeContractStarts type) and is ignored when Coworker targets a single customer. |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--reminder-type` | enum, required | The event that triggers the reminder, and it decides which companion field supplies the offset: FixedDate uses ReminderDate; DaysAfterSignUp, LastActivity and DaysAfterFirstContractStartDate use DaysAfterSignup; DaysAfterRenewal, AfterABooking, DueInvoice and DaysAfterDeliveryNotCollected use DaysAfterRenewal; DaysBeforeRenewal, DaysBeforeCancellation, DaysBeforeTerm and DaysBeforeContractStarts use DaysBeforeRenewal; ProductPurchase and ProductAddedToBooking need Product; AfterABooking can be narrowed with Resources. Birthday, OnFirstCheckIn, OnSignUpFormSubmitted, InvoiceFirstPaid, RegularBooking, RegularBookerStoppedBooking, StoppedBooking and SingleBooking need no offset. Event-driven types (ProductPurchase, ProductAddedToBooking, OnFirstCheckIn, OnSignUpFormSubmitted, InvoiceFirstPaid) run right after the event; every other type is evaluated once a day at around 8am in the location's local time. |
| `--reminder-date` | DateTime | Date the reminder is sent, used only by the FixedDate type and ignored by every other type; stored in UTC and compared in the location's local time, so it fires on that local calendar day and never before its time of day. |
| `--days-after-signup` | int | Whole number of days after the trigger date, required and not negative for the DaysAfterSignUp, LastActivity and DaysAfterFirstContractStartDate types and cleared automatically for every other type. DaysAfterSignUp counts from the customer's registration date, LastActivity from their last access and DaysAfterFirstContractStartDate from their first contract start date. |
| `--product-id` | long | ID of the product whose purchase triggers the reminder; required by the ProductPurchase and ProductAddedToBooking types and ignored by every other type. |
| `--survey-id` | long | ID of the survey sent to the customer when ReminderAction is SendSurvey; nothing is sent while it is empty, and it is ignored for the other actions. |
| `--days-after-renewal` | int | Whole number of days after the trigger event, required and not negative for the DaysAfterRenewal, AfterABooking, DueInvoice and DaysAfterDeliveryNotCollected types and cleared automatically for every other type. It counts from the contract renewal date, the end of the booking, the invoice due date or the delivery reception date respectively. |
| `--days-before-renewal` | int | Whole number of days before the trigger date, required and not negative for the DaysBeforeRenewal, DaysBeforeCancellation, DaysBeforeTerm and DaysBeforeContractStarts types and cleared automatically for every other type. It counts back from the next invoice date, the contract cancellation date, the contract term end date or the contract start date respectively. |
| `--reminder-action` | enum, required | How the reminder is delivered: SendEmail sends the built-in reminder email, SendCannedMessage sends the message macro named in CannedResponse, and SendSurvey sends the survey named in Survey. |
| `--email` | string | Optional fixed email address notified instead of the customer, normally a staff inbox; leave it empty to send the message to the customer's own address and record it in their message history. It is rejected on save for the RegularBooking, RegularBookerStoppedBooking, StoppedBooking, SingleBooking and DaysAfterDeliveryNotCollected types, which can only be sent to the customer. |
| `--canned-response-id` | long | ID of the message macro sent when ReminderAction is SendCannedMessage; nothing is sent while it is empty, and the message subject falls back to the macro name when the macro has none. Messages for the DaysBeforeRenewal and DueInvoice types are addressed to the customer's billing email. |
| `--next-process-time` | DateTime | Read-only scheduler state in UTC holding the next time the reminder job will evaluate this reminder; the job moves it to the next 8am in the location's local time after each run, or to ReminderDate while a fixed-date reminder is still pending. Change ReminderType or ReminderDate to alter when the reminder runs. |
| `--resources` | list, repeat flag | List of resource IDs the AfterABooking reminder is limited to; an empty list means a booking for any resource triggers it, and the list is ignored by every other reminder type. |
| `--added-resources` | list, repeat flag | IDs added to the Resources relationship. |
| `--removed-resources` | list, repeat flag | IDs removed from the Resources relationship. |
| `--only-send-to-team-paying-members` | bool | Whether the audience is restricted to customers who are the designated paying member of a team invoiced as a single invoice; it enables the reminder on its own, and every other recipient is skipped while it is on. |
| `--only-send-to-active-coworkers` | bool | Whether customers whose record is not active are skipped; it applies on top of every other audience setting, including a single customer named in Coworker. |
| `--blocking-period-minutes` | int | Minimum number of minutes that must pass before the same customer can receive this reminder again, measured against the reminder's own audit records; must not be negative, empty means no throttling, and it is ignored when Coworker targets a single customer. |

#### Reminder update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this reminder; customers are matched by their home location, and only locations inside this one are also matched when ForAllChildLocations is on. |
| `--name` | string | Required internal name used to identify the reminder in admin lists and search; it is never shown to the customer when a message macro or a survey supplies the message content. |
| `--for-all-contacts` | bool | Whether contacts (customers with no active contract) are in the audience; set it together with ForAllMembers to target every customer. The reminder is never processed while this, ForAllMembers, OnlySendToTeamPayingMembers and Coworker are all empty. |
| `--for-all-members` | bool | Whether members (customers with an active contract) are in the audience; combine it with Tariffs to restrict delivery to specific plans, or set it together with ForAllContacts to target every customer. |
| `--for-all-child-locations` | bool | Whether customers whose home location is any location inside the owning location are also included; when off, only customers whose home location is the owning location itself receive the reminder. |
| `--coworker-id` | long | Optional ID of the single customer this reminder targets; when set it replaces the ForAllMembers, ForAllContacts and Tariffs audience filters, enables the reminder on its own and disables the BlockingPeriodMinutes throttle, while OnlySendToActiveCoworkers and OnlySendToTeamPayingMembers still apply. |
| `--tariffs` | list, repeat flag | List of plan IDs the customer must hold a contract for; an empty list means no plan restriction. It is matched against the customer's active contracts (their non-cancelled contracts for the DaysBeforeContractStarts type) and is ignored when Coworker targets a single customer. |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--reminder-type` | enum | The event that triggers the reminder, and it decides which companion field supplies the offset: FixedDate uses ReminderDate; DaysAfterSignUp, LastActivity and DaysAfterFirstContractStartDate use DaysAfterSignup; DaysAfterRenewal, AfterABooking, DueInvoice and DaysAfterDeliveryNotCollected use DaysAfterRenewal; DaysBeforeRenewal, DaysBeforeCancellation, DaysBeforeTerm and DaysBeforeContractStarts use DaysBeforeRenewal; ProductPurchase and ProductAddedToBooking need Product; AfterABooking can be narrowed with Resources. Birthday, OnFirstCheckIn, OnSignUpFormSubmitted, InvoiceFirstPaid, RegularBooking, RegularBookerStoppedBooking, StoppedBooking and SingleBooking need no offset. Event-driven types (ProductPurchase, ProductAddedToBooking, OnFirstCheckIn, OnSignUpFormSubmitted, InvoiceFirstPaid) run right after the event; every other type is evaluated once a day at around 8am in the location's local time. |
| `--reminder-date` | DateTime | Date the reminder is sent, used only by the FixedDate type and ignored by every other type; stored in UTC and compared in the location's local time, so it fires on that local calendar day and never before its time of day. |
| `--days-after-signup` | int | Whole number of days after the trigger date, required and not negative for the DaysAfterSignUp, LastActivity and DaysAfterFirstContractStartDate types and cleared automatically for every other type. DaysAfterSignUp counts from the customer's registration date, LastActivity from their last access and DaysAfterFirstContractStartDate from their first contract start date. |
| `--product-id` | long | ID of the product whose purchase triggers the reminder; required by the ProductPurchase and ProductAddedToBooking types and ignored by every other type. |
| `--survey-id` | long | ID of the survey sent to the customer when ReminderAction is SendSurvey; nothing is sent while it is empty, and it is ignored for the other actions. |
| `--days-after-renewal` | int | Whole number of days after the trigger event, required and not negative for the DaysAfterRenewal, AfterABooking, DueInvoice and DaysAfterDeliveryNotCollected types and cleared automatically for every other type. It counts from the contract renewal date, the end of the booking, the invoice due date or the delivery reception date respectively. |
| `--days-before-renewal` | int | Whole number of days before the trigger date, required and not negative for the DaysBeforeRenewal, DaysBeforeCancellation, DaysBeforeTerm and DaysBeforeContractStarts types and cleared automatically for every other type. It counts back from the next invoice date, the contract cancellation date, the contract term end date or the contract start date respectively. |
| `--reminder-action` | enum | How the reminder is delivered: SendEmail sends the built-in reminder email, SendCannedMessage sends the message macro named in CannedResponse, and SendSurvey sends the survey named in Survey. |
| `--email` | string | Optional fixed email address notified instead of the customer, normally a staff inbox; leave it empty to send the message to the customer's own address and record it in their message history. It is rejected on save for the RegularBooking, RegularBookerStoppedBooking, StoppedBooking, SingleBooking and DaysAfterDeliveryNotCollected types, which can only be sent to the customer. |
| `--canned-response-id` | long | ID of the message macro sent when ReminderAction is SendCannedMessage; nothing is sent while it is empty, and the message subject falls back to the macro name when the macro has none. Messages for the DaysBeforeRenewal and DueInvoice types are addressed to the customer's billing email. |
| `--next-process-time` | DateTime | Read-only scheduler state in UTC holding the next time the reminder job will evaluate this reminder; the job moves it to the next 8am in the location's local time after each run, or to ReminderDate while a fixed-date reminder is still pending. Change ReminderType or ReminderDate to alter when the reminder runs. |
| `--resources` | list, repeat flag | List of resource IDs the AfterABooking reminder is limited to; an empty list means a booking for any resource triggers it, and the list is ignored by every other reminder type. |
| `--added-resources` | list, repeat flag | IDs added to the Resources relationship. |
| `--removed-resources` | list, repeat flag | IDs removed from the Resources relationship. |
| `--only-send-to-team-paying-members` | bool | Whether the audience is restricted to customers who are the designated paying member of a team invoiced as a single invoice; it enables the reminder on its own, and every other recipient is skipped while it is on. |
| `--only-send-to-active-coworkers` | bool | Whether customers whose record is not active are skipped; it applies on top of every other audience setting, including a single customer named in Coworker. |
| `--blocking-period-minutes` | int | Minimum number of minutes that must pass before the same customer can receive this reminder again, measured against the reminder's own audit records; must not be negative, empty means no throttling, and it is ignored when Coworker targets a single customer. |

#### Reminder PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus reminders update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Resources`, `AddedResources`, `RemovedResources`

#### Reminder enum values

| Option | Valid values |
| ------ | ------------ |
| `--reminder-type` | `1` FixedDate, `2` DaysAfterSignUp, `3` DaysAfterRenewal, `4` DaysBeforeRenewal, `5` Birthday, `6` DaysBeforeCancellation, `7` AfterABooking, `8` LastActivity, `9` ProductPurchase, `10` DueInvoice, `11` OnFirstCheckIn, `12` OnSignUpFormSubmitted, `13` DaysBeforeTerm, `14` RegularBookerStoppedBooking, `15` RegularBooking, `16` StoppedBooking, `17` SingleBooking, `18` InvoiceFirstPaid, `19` DaysBeforeContractStarts, `20` DaysAfterDeliveryNotCollected, `21` DaysAfterFirstContractStartDate, `22` ProductAddedToBooking |
| `--reminder-action` | `1` SendEmail, `2` SendCannedMessage, `3` SendSurvey |

<!-- END:GENERATED entity=Reminders -->
