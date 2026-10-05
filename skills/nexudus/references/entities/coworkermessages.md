# CoworkerMessages

<!-- BEGIN:GENERATED entity=CoworkerMessages -->

A customer message (CoworkerMessage) records an incoming or outgoing email communication associated with a customer; operators can create outbound messages and inspect message history by customer or connected email account.

CoworkerMessages support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus coworkermessages list --agent` | List all coworkermessages |
| `nexudus coworkermessages list --id <id> --agent` | Filter by single ID |
| `nexudus coworkermessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkermessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkermessages list --coworker-full-name <value> --email-account-display-name <value> --agent` | Filter coworkermessages by properties |
| `nexudus coworkermessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkermessages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkermessages get <id> --agent` | Get single coworkermessage |

#### CoworkerMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer who sent or received this message; location access is determined through the customer's InvoicingBusiness. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-email` | string | Display value for Coworker.Email. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--email-account-id` | long | ID of the optional connected email account used to send or receive this message; when omitted, the customer's location default email settings are used. |
| `--email-account-display-name` | string | Display value for EmailAccount.DisplayName. |
| `--email-account-email-address` | string | Display value for EmailAccount.EmailAddress. |
| `--subject` | string | Message subject, limited to 254 characters. |
| `--body` | string | HTML message body; canned-response tokens are expanded for the customer before an outgoing email is queued. |
| `--is-new-message` | bool | Whether an inbound message is still unread; outgoing messages are never unread, and the COWORKER_MESSAGE_MARK_READ command clears the flag when a message is opened. |
| `--incoming` | bool | Whether the message was received from the customer (true) rather than sent to the customer (false); inbound messages are created by the email integration. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerMessage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerMessage PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:


### CoworkerMessage (key fields)

`Id`, `CoworkerFullName`, `EmailAccountDisplayName`

<!-- END:GENERATED entity=CoworkerMessages -->
