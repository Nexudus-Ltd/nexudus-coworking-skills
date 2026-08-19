# WebHooks

<!-- BEGIN:GENERATED entity=WebHooks -->

A **WebHook** sends an HTTP POST request to a specified URL whenever a particular event occurs within a location. Webhooks let external systems react to changes in real time without polling the API.

Each webhook is scoped to a single location (`BusinessId`) and is configured with an `Action` that identifies the triggering event (e.g. `CoworkerCreate`, `BookingCreate`, `CoworkerInvoicePaid`). Only one action can be assigned per webhook record — create separate webhook records if you need to react to multiple events.

Nexudus will POST a JSON payload to the configured `URL` every time the selected action fires. If the endpoint returns a non-2xx response, the error is recorded in `LastError` and `ErrorCount` is incremented. A webhook is automatically disabled after repeated failures.

Set `Active` to `false` to pause delivery without deleting the webhook. Use `LastTrigger` and `LastError` to monitor delivery health.

WebHooks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus webhooks list --agent` | List all webhooks |
| `nexudus webhooks list --id <id> --agent` | Filter by single ID |
| `nexudus webhooks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus webhooks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus webhooks list --name <value> --u-r-l <value> --agent` | Filter webhooks by properties |
| `nexudus webhooks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus webhooks list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus webhooks get <id> --agent` | Get single webhook |
| `nexudus webhooks create --business-id <value> --name <value> --action <value> --u-r-l <value> --agent` | Create webhook |
| `nexudus webhooks update <id> --name "New Name" --agent` | Update webhook |
| `nexudus webhooks delete <id> --yes --agent` | Delete webhook (no prompt) |

#### WebHook list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this webhook belongs to |
| `--name` | string | Display name for the webhook |
| `--action` | enum | The event that triggers this webhook (e.g. CoworkerCreate, BookingCreate, CoworkerInvoicePaid) |
| `--description` | string | Optional description of the webhook's purpose |
| `--u-r-l` | string | The endpoint URL that receives the HTTP POST payload when the webhook fires |
| `--active` | bool | Whether the webhook is enabled and will fire when the configured action occurs |
| `--last-error` | string | Error message from the most recent failed delivery attempt |
| `--error-count` | int | Number of consecutive delivery failures since the last successful call |
| `--from-error-count` | range | |
| `--to-error-count` | range | |
| `--last-trigger` | DateTime | Date and time the webhook last fired successfully |
| `--from-last-trigger` | range | |
| `--to-last-trigger` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### WebHook sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### WebHook create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this webhook belongs to |
| `--name` | string, required | Display name for the webhook |
| `--action` | enum, required | The event that triggers this webhook (e.g. CoworkerCreate, BookingCreate, CoworkerInvoicePaid) |
| `--description` | string | Optional description of the webhook's purpose |
| `--u-r-l` | string, required | The endpoint URL that receives the HTTP POST payload when the webhook fires |
| `--active` | bool | Whether the webhook is enabled and will fire when the configured action occurs |

#### WebHook update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this webhook belongs to |
| `--name` | string | Display name for the webhook |
| `--action` | enum | The event that triggers this webhook (e.g. CoworkerCreate, BookingCreate, CoworkerInvoicePaid) |
| `--description` | string | Optional description of the webhook's purpose |
| `--u-r-l` | string | The endpoint URL that receives the HTTP POST payload when the webhook fires |
| `--active` | bool | Whether the webhook is enabled and will fire when the configured action occurs |

### WebHook (key fields)

`Id`, `Name`, `URL`

#### WebHook enum values

| Option | Valid values |
| ------ | ------------ |
| `--action` | `1` None, `2` CoworkerUpdate, `3` CoworkerCreate, `4` BlogPostCreate, `5` BlogPostUpdate, `6` BookingCreate, `7` BookingUpdate, `8` BookingDelete, `9` SendWelcomeEmail, `10` CoworkerContractActivate, `11` CoworkerContractCancel, `12` CoworkerContractRenew, `13` CoworkerContractUpgradeDowngrade, `14` CoworkerContractActivateFirst, `15` CoworkerInvoiceCreateFirst, `16` CoworkerInvoiceCreate, `17` CoworkerInvoiceDelete, `18` CoworkerInvoiceUpdate, `19` CoworkerInvoiceRefund, `20` CoworkerInvoiceCreditNote, `21` CoworkerInvoicePaid, `22` CoworkerInvoiceFailedPayment, `23` CoworkerInvoiceReceivedPayment, `24` CoworkerInvoiceAwaitingPayment, `25` CalendarEventCreate, `26` CalendarEventUpdate, `27` CalendarEventAttendeeDelete, `28` CalendarEventAttendeeCreate, `29` CalendarEventAttendeeUpdate, `30` GlobalChatMessageCreate, `31` NewsLetterSubscriberCreate, `32` NewsLetterSubscriberSubscribed, `33` NewsLetterSubscriberUnSubscribed, `34` NewsLetterSubscriberRemovedFromGroup, `35` CoworkerCheckout, `36` CoworkerCheckin, `37` CoworkerCheckinFailed, `38` VisitorNotification, `39` CommunityBoardNewThread, `40` CommunityBoardNewReply, `41` VisitorCheckedin, `42` VisitorRegistered, `43` BlogPostDelete, `44` CalendarEventDelete, `45` HelDeskMessageCreated, `46` HelpDeskCommentCreated, `47` CheckinCreated, `48` CheckinUpdated, `49` CheckinDeleted, `50` CoworkerDelete, `51` CoworkerMessageCreate, `52` DeliveryCreated, `53` DeliveryAssigned, `54` ProposalCreated, `55` ProposalUpdated, `56` ProposalDeleted, `57` TeamCreated, `58` TeamUpdated, `59` TeamDeleted, `60` CoworkerContractUpdate, `61` AccessControlUpdate, `62` CoworkerContractCreate, `63` FailedCheckin, `64` VisitorDeleted, `65` CoworkerInvoiceLedgerEntryCreate, `66` CoworkerInvoiceLedgerEntryDelete, `67` CoworkerInvoiceLedgerEntryUpdate, `68` CoworkerProductCreate, `69` CoworkerProductUpdate, `70` CoworkerProductDelete, `71` FloorPlanDeskCreate, `72` FloorPlanDeskDelete, `73` FloorPlanDeskUpdate, `74` TariffCreate, `75` TariffDelete, `76` TariffUpdate, `77` CoworkerContractDelete, `78` FloorPlanCreate, `79` FloorPlanDelete, `80` FloorPlanUpdate, `81` ProductCreate, `82` ProductDelete, `83` ProductUpdate, `84` BusinessUpdate, `85` CommunityGroupCreate, `86` CommunityGroupDelete, `87` CommunityGroupUpdate, `88` CoworkerPaymentMethodCreate, `89` CoworkerPaymentMethodDelete, `90` CoworkerPaymentMethodUpdate |

<!-- END:GENERATED entity=WebHooks -->
