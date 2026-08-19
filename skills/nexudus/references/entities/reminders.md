# Reminders

<!-- BEGIN:GENERATED entity=Reminders -->

A **Reminder** defines an automated message triggered by a specific event or schedule. Reminders can send emails, canned messages, or surveys based on triggers such as sign-up anniversaries, booking activity, invoice due dates, or contract milestones.

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
| `--business-id` | long | ID of the business linked to this record |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--name` | string | The name value for this reminder |
| `--for-all-contacts` | bool | Whether for all contacts is enabled |
| `--for-all-members` | bool | Whether for all members is enabled |
| `--for-all-child-locations` | bool | Whether for all child locations is enabled |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--reminder-type` | enum | The reminder type value for this reminder |
| `--reminder-date` | DateTime | Date/time value for reminder date |
| `--from-reminder-date` | range | |
| `--to-reminder-date` | range | |
| `--days-after-signup` | int | The days after signup value for this reminder |
| `--from-days-after-signup` | range | |
| `--to-days-after-signup` | range | |
| `--product-id` | long | ID of the product linked to this record |
| `--product-name` | string | Display name of the linked product (read-only) |
| `--survey-id` | long | ID of the survey linked to this record |
| `--survey-name` | string | Display name of the linked survey (read-only) |
| `--days-after-renewal` | int | The days after renewal value for this reminder |
| `--from-days-after-renewal` | range | |
| `--to-days-after-renewal` | range | |
| `--days-before-renewal` | int | The days before renewal value for this reminder |
| `--from-days-before-renewal` | range | |
| `--to-days-before-renewal` | range | |
| `--reminder-action` | enum | The reminder action value for this reminder |
| `--email` | string | The email value for this reminder |
| `--canned-response-id` | long | ID of the canned response linked to this record |
| `--canned-response-name` | string | Display name of the linked canned response (read-only) |
| `--next-process-time` | DateTime | Date/time value for next process time |
| `--from-next-process-time` | range | |
| `--to-next-process-time` | range | |
| `--only-send-to-team-paying-members` | bool | Whether only send to team paying members is enabled |
| `--only-send-to-active-coworkers` | bool | Whether only send to active coworkers is enabled |
| `--blocking-period-minutes` | int | The blocking period minutes value for this reminder |
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
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this reminder |
| `--for-all-contacts` | bool | Whether for all contacts is enabled |
| `--for-all-members` | bool | Whether for all members is enabled |
| `--for-all-child-locations` | bool | Whether for all child locations is enabled |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this reminder |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this reminder |
| `--reminder-type` | enum, required | The reminder type value for this reminder |
| `--reminder-date` | DateTime | Date/time value for reminder date |
| `--days-after-signup` | int | The days after signup value for this reminder |
| `--product-id` | long | ID of the product linked to this record |
| `--survey-id` | long | ID of the survey linked to this record |
| `--days-after-renewal` | int | The days after renewal value for this reminder |
| `--days-before-renewal` | int | The days before renewal value for this reminder |
| `--reminder-action` | enum, required | The reminder action value for this reminder |
| `--email` | string | The email value for this reminder |
| `--canned-response-id` | long | ID of the canned response linked to this record |
| `--next-process-time` | DateTime | Date/time value for next process time |
| `--resources` | list, repeat flag | List of resources linked to this record |
| `--added-resources` | list, repeat flag | The added resources value for this reminder |
| `--removed-resources` | list, repeat flag | The removed resources value for this reminder |
| `--only-send-to-team-paying-members` | bool | Whether only send to team paying members is enabled |
| `--only-send-to-active-coworkers` | bool | Whether only send to active coworkers is enabled |
| `--blocking-period-minutes` | int | The blocking period minutes value for this reminder |

#### Reminder update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this reminder |
| `--for-all-contacts` | bool | Whether for all contacts is enabled |
| `--for-all-members` | bool | Whether for all members is enabled |
| `--for-all-child-locations` | bool | Whether for all child locations is enabled |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this reminder |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this reminder |
| `--reminder-type` | enum | The reminder type value for this reminder |
| `--reminder-date` | DateTime | Date/time value for reminder date |
| `--days-after-signup` | int | The days after signup value for this reminder |
| `--product-id` | long | ID of the product linked to this record |
| `--survey-id` | long | ID of the survey linked to this record |
| `--days-after-renewal` | int | The days after renewal value for this reminder |
| `--days-before-renewal` | int | The days before renewal value for this reminder |
| `--reminder-action` | enum | The reminder action value for this reminder |
| `--email` | string | The email value for this reminder |
| `--canned-response-id` | long | ID of the canned response linked to this record |
| `--next-process-time` | DateTime | Date/time value for next process time |
| `--resources` | list, repeat flag | List of resources linked to this record |
| `--added-resources` | list, repeat flag | The added resources value for this reminder |
| `--removed-resources` | list, repeat flag | The removed resources value for this reminder |
| `--only-send-to-team-paying-members` | bool | Whether only send to team paying members is enabled |
| `--only-send-to-active-coworkers` | bool | Whether only send to active coworkers is enabled |
| `--blocking-period-minutes` | int | The blocking period minutes value for this reminder |

#### Reminder PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus reminders update <id> --email "«PII:EMAIL:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Resources`, `AddedResources`, `RemovedResources`

#### Reminder enum values

| Option | Valid values |
| ------ | ------------ |
| `--reminder-type` | `1` FixedDate, `2` DaysAfterSignUp, `3` DaysAfterRenewal, `4` DaysBeforeRenewal, `5` Birthday, `6` DaysBeforeCancellation, `7` AfterABooking, `8` LastActivity, `9` ProductPurchase, `10` DueInvoice, `11` OnFirstCheckIn, `12` OnSignUpFormSubmitted, `13` DaysBeforeTerm, `14` RegularBookerStoppedBooking, `15` RegularBooking, `16` StoppedBooking, `17` SingleBooking, `18` InvoiceFirstPaid, `19` DaysBeforeContractStarts, `20` DaysAfterDeliveryNotCollected, `21` DaysAfterFirstContractStartDate, `22` ProductAddedToBooking |
| `--reminder-action` | `1` SendEmail, `2` SendCannedMessage, `3` SendSurvey |

<!-- END:GENERATED entity=Reminders -->
