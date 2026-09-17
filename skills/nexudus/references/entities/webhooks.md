# WebHooks

<!-- BEGIN:GENERATED entity=WebHooks -->

A webhook makes Nexudus send an HTTP POST with a JSON payload to an external URL whenever one chosen event happens in a location, so other systems can react in real time without polling the API. Each record has exactly one Action, so a separate webhook is needed per event, and a webhook registered on a network parent location also receives events from that parent's child locations. Delivery is signed with the location's Webhooks.SharedSecret setting when one is configured, retried with an increasing delay after each failure, and skipped when the same record would be sent with an identical payload twice. Delivery health is visible in LastTrigger, LastError and ErrorCount; the webhook is deactivated automatically once ErrorCount passes 10 or the URL does not start with http, and it is deleted automatically if the endpoint answers 410 Gone. Set Active to false to pause delivery without deleting the record.

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
| `--business-id` | long | ID of the location that owns this webhook. Events raised in this location trigger it, and a webhook registered on a network parent location also receives events from that parent's child locations. |
| `--name` | string | Display name used to identify this webhook in the location's webhook list; it is not sent to the endpoint. |
| `--action` | enum | The single event that triggers this webhook, such as CoworkerCreate, BookingCreate or CoworkerInvoicePaid. Only one action per webhook, so create a separate record for each event you need. Defaults to None, which never fires, so always set this explicitly. |
| `--description` | string | Optional free-text note describing the webhook's purpose. It is not shown in the admin form and is not sent to the endpoint. |
| `--u-r-l` | string | Endpoint that receives the HTTP POST JSON payload when the webhook fires, up to 1024 characters. It must start with http or https; any other value records an error and deactivates the webhook on the first delivery attempt. |
| `--active` | bool | Whether the webhook is enabled and will fire when its action occurs. Set false to pause delivery without deleting the record. Nexudus sets it to false automatically once ErrorCount passes 10, or when the URL does not start with http. |
| `--last-error` | string | Message from the most recent failed delivery attempt, cleared at the start of each new attempt. Read-only diagnostic written by the delivery service; fix the endpoint rather than trying to change this value. |
| `--error-count` | int | Consecutive failed delivery attempts. Reset to 0 after a successful call, incremented on each failure, and the webhook is deactivated once it passes 10. Read-only diagnostic written by the delivery service. |
| `--from-error-count` | range | |
| `--to-error-count` | range | |
| `--last-trigger` | DateTime | UTC date and time of the most recent delivery attempt, recorded when the attempt starts rather than when it succeeds; check LastError and ErrorCount to tell whether that attempt succeeded. Read-only diagnostic written by the delivery service. |
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
| `--business-id` | long, required | ID of the location that owns this webhook. Events raised in this location trigger it, and a webhook registered on a network parent location also receives events from that parent's child locations. |
| `--name` | string, required | Display name used to identify this webhook in the location's webhook list; it is not sent to the endpoint. |
| `--action` | enum, required | The single event that triggers this webhook, such as CoworkerCreate, BookingCreate or CoworkerInvoicePaid. Only one action per webhook, so create a separate record for each event you need. Defaults to None, which never fires, so always set this explicitly. |
| `--description` | string | Optional free-text note describing the webhook's purpose. It is not shown in the admin form and is not sent to the endpoint. |
| `--u-r-l` | string, required | Endpoint that receives the HTTP POST JSON payload when the webhook fires, up to 1024 characters. It must start with http or https; any other value records an error and deactivates the webhook on the first delivery attempt. |
| `--active` | bool | Whether the webhook is enabled and will fire when its action occurs. Set false to pause delivery without deleting the record. Nexudus sets it to false automatically once ErrorCount passes 10, or when the URL does not start with http. |

#### WebHook update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this webhook. Events raised in this location trigger it, and a webhook registered on a network parent location also receives events from that parent's child locations. |
| `--name` | string | Display name used to identify this webhook in the location's webhook list; it is not sent to the endpoint. |
| `--action` | enum | The single event that triggers this webhook, such as CoworkerCreate, BookingCreate or CoworkerInvoicePaid. Only one action per webhook, so create a separate record for each event you need. Defaults to None, which never fires, so always set this explicitly. |
| `--description` | string | Optional free-text note describing the webhook's purpose. It is not shown in the admin form and is not sent to the endpoint. |
| `--u-r-l` | string | Endpoint that receives the HTTP POST JSON payload when the webhook fires, up to 1024 characters. It must start with http or https; any other value records an error and deactivates the webhook on the first delivery attempt. |
| `--active` | bool | Whether the webhook is enabled and will fire when its action occurs. Set false to pause delivery without deleting the record. Nexudus sets it to false automatically once ErrorCount passes 10, or when the URL does not start with http. |

### WebHook (key fields)

`Id`, `Name`, `URL`

#### WebHook enum values

| Option | Valid values |
| ------ | ------------ |
| `--action` | `1` None, `2` CoworkerUpdate, `3` CoworkerCreate, `4` BlogPostCreate, `5` BlogPostUpdate, `6` BookingCreate, `7` BookingUpdate, `8` BookingDelete, `9` SendWelcomeEmail, `10` CoworkerContractActivate, `11` CoworkerContractCancel, `12` CoworkerContractRenew, `13` CoworkerContractUpgradeDowngrade, `14` CoworkerContractActivateFirst, `15` CoworkerInvoiceCreateFirst, `16` CoworkerInvoiceCreate, `17` CoworkerInvoiceDelete, `18` CoworkerInvoiceUpdate, `19` CoworkerInvoiceRefund, `20` CoworkerInvoiceCreditNote, `21` CoworkerInvoicePaid, `22` CoworkerInvoiceFailedPayment, `23` CoworkerInvoiceReceivedPayment, `24` CoworkerInvoiceAwaitingPayment, `25` CalendarEventCreate, `26` CalendarEventUpdate, `27` CalendarEventAttendeeDelete, `28` CalendarEventAttendeeCreate, `29` CalendarEventAttendeeUpdate, `30` GlobalChatMessageCreate, `31` NewsLetterSubscriberCreate, `32` NewsLetterSubscriberSubscribed, `33` NewsLetterSubscriberUnSubscribed, `34` NewsLetterSubscriberRemovedFromGroup, `35` CoworkerCheckout, `36` CoworkerCheckin, `37` CoworkerCheckinFailed, `38` VisitorNotification, `39` CommunityBoardNewThread, `40` CommunityBoardNewReply, `41` VisitorCheckedin, `42` VisitorRegistered, `43` BlogPostDelete, `44` CalendarEventDelete, `45` HelDeskMessageCreated, `46` HelpDeskCommentCreated, `47` CheckinCreated, `48` CheckinUpdated, `49` CheckinDeleted, `50` CoworkerDelete, `51` CoworkerMessageCreate, `52` DeliveryCreated, `53` DeliveryAssigned, `54` ProposalCreated, `55` ProposalUpdated, `56` ProposalDeleted, `57` TeamCreated, `58` TeamUpdated, `59` TeamDeleted, `60` CoworkerContractUpdate, `61` AccessControlUpdate, `62` CoworkerContractCreate, `63` FailedCheckin, `64` VisitorDeleted, `65` CoworkerInvoiceLedgerEntryCreate, `66` CoworkerInvoiceLedgerEntryDelete, `67` CoworkerInvoiceLedgerEntryUpdate, `68` CoworkerProductCreate, `69` CoworkerProductUpdate, `70` CoworkerProductDelete, `71` FloorPlanDeskCreate, `72` FloorPlanDeskDelete, `73` FloorPlanDeskUpdate, `74` TariffCreate, `75` TariffDelete, `76` TariffUpdate, `77` CoworkerContractDelete, `78` FloorPlanCreate, `79` FloorPlanDelete, `80` FloorPlanUpdate, `81` ProductCreate, `82` ProductDelete, `83` ProductUpdate, `84` BusinessUpdate, `85` CommunityGroupCreate, `86` CommunityGroupDelete, `87` CommunityGroupUpdate, `88` CoworkerPaymentMethodCreate, `89` CoworkerPaymentMethodDelete, `90` CoworkerPaymentMethodUpdate |

<!-- END:GENERATED entity=WebHooks -->
