# CannedResponses

<!-- BEGIN:GENERATED entity=CannedResponses -->

A **CannedResponse** is a reusable message template, known as a **Message Macro** in the Nexudus UI (Admin Panel > CRM > Message Macros).

Message macros can be sent directly to customers or used alongside reminders to automate communication. They support dynamic tokens — placeholders such as `{salutation}` — that Nexudus automatically replaces with live data from your account when the message is delivered.

Message macros are available across all locations in a network, regardless of which location created them.

### Supported tokens

**Location tokens** (always available):

| Token | Description |
| ----- | ----------- |
| `{businessname}` / `{locationName}` | Location name |
| `{businessphone}` | Location phone |
| `{businesscontactphone}` | Location phone or contact phone |
| `{businesscontactweb}` | Location web contact |
| `{businessaddress}` | Location address |
| `{businessemail}` | Location email contact |
| `{businessid}` | Location ID |
| `{businessurl}` | Location public URL |
| `{businessavatar}` | Location logo URL |
| `{businessbanner}` | Location banner URL |
| `{logoImage}` | Location logo as an HTML `<img>` tag |
| `{timezone}` | Location timezone |
| `{date}` | Current date in location timezone |
| `{time}` | Current time in location timezone |
| `{yesterday}` | Yesterday's date |
| `{tomorrow}` | Tomorrow's date |
| `{terms}` | Terms & conditions (rendered from Markdown) |
| `{iosurl}` | iOS app URL |
| `{androidurl}` | Android app URL |
| `{serviceurl}` | Dashboard URL |
| `{unsubscribeurl}` | Unsubscribe URL |
| _(custom fields)_ | Any Business custom fields |

**Customer tokens** (always available):

| Token | Description |
| ----- | ----------- |
| `{firstname}` | Customer first name |
| `{fullname}` | Customer full name |
| `{salutation}` | Customer salutation |
| `{email}` / `{username}` | Customer email |
| `{coworkerid}` | Customer ID |
| `{coworkerguid}` | Customer GUID |
| `{homebusiness}` | Customer's home location name |
| `{companyname}` / `{companyName}` | Company name |
| `{phone}` | Mobile phone or landline |
| `{address}` | Address |
| `{postcode}` | Post code |
| `{cityname}` | City |
| `{state}` | State |
| `{billingname}` / `{billingName}` | Billing name |
| `{billingadress}` | Billing address |
| `{billingcityname}` | Billing city |
| `{billingpostcode}` | Billing post code |
| `{billingstate}` | Billing state |
| `{accesscardid}` / `{accessCardId}` | Access card ID / pincode |
| `{accesscardtag}` | Access card tag |
| `{accesspincode}` | Access PIN code |
| `{cardNumber}` | Card number |
| `{keyFobNumber}` | Key fob number |
| `{tariffname}` | Current pricing plan name |
| `{tariffprice}` | Current pricing plan price |
| `{nexttariffname}` | Next pricing plan name |
| `{nexttariffprice}` | Next pricing plan price |
| `{contractnotes}` | Contract notes |
| `{cancellationdate}` | Contract cancellation date |
| `{nextinvoicedate}` | Next invoice date |
| `{invoicedperiod}` | Invoiced period date |
| `{contracterm}` | Contract term end date |
| `{desks}` | Assigned desks (comma-separated) |
| `{generalterms}` | General terms & conditions |
| `{contracterms}` | Contract terms & conditions |
| `{teamNames}` | Team names (comma-separated) |
| `{custom1}` – `{custom30}` | Legacy custom fields 1–30 |
| `{coworkerurl}` | Admin URL for the customer |
| `{coworkerpublicurl}` | Public profile URL |
| `{coworkerprofileurl}` | Customer profile admin URL |
| `{coworkercontractsurl}` | Customer contracts admin URL |
| `{coworkermessagesurl}` | Customer messages admin URL |
| `{coworkerproductssurl}` | Customer products admin URL |
| `{coworkerproposalsurl}` | Customer proposals admin URL |
| `{gocardlesssignupurl}` | Direct debit signup URL |
| `{teamsignuplink}` | Team signup link |
| _(custom fields)_ | Any Coworker custom fields |

**User / account tokens** (always available when the customer has a portal access / user account):

| Token | Description |
| ----- | ----------- |
| `{userid}` | User ID |
| `{passportnumber}` | Passport number |
| `{password}` | Temporary password (only during password reset) |
| `{useraccesstoken}` | User access token |
| `{activateurl}` | Account activation URL |
| `{loginurl}` | Login URL |
| `{magiclink}` | Magic link for passwordless login |
| `{resetpasswordurl}` | Reset password URL |
| `{unpaidinvoicescount}` | Number of unpaid invoices |
| `{unpaidinvoicenumbers}` | Unpaid invoice numbers (comma-separated) |
| `{unpaidinvoicestotal}` | Unpaid invoices total amount |
| `{dueinvoicescount}` | Number of overdue invoices |
| `{dueinvoicenumbers}` | Overdue invoice numbers (comma-separated) |
| `{dueinvoicestotal}` | Overdue invoices total amount |
| `{earliestduedate}` | Earliest due date across unpaid invoices |

**Message-macro-specific tokens**:

| Token | Description |
| ----- | ----------- |
| `{nextbillingdate}` | Next tariff billing date |
| `{priceplan}` | Active pricing plan names (comma-separated, all contracts) |
| `{nextpriceplan}` | Next pricing plan names (comma-separated) |
| `{priceplanprice}` | Total cost of active pricing plans (formatted in location currency) |
| `{nextpriceplanprice}` | Total cost of next pricing plans |
| `{maincontractpriceplan}` | Main contract pricing plan name |
| `{maincontractprice}` | Main contract price |
| `{maincontractbillingdate}` | Main contract renewal / billing date |
| `{maincontractstartdate}` | Main contract start date |
| `{deliverytable}` | HTML table of uncollected deliveries (location, name, date, notes) |

**Delivery tokens** (resolved from the customer's oldest uncollected delivery, if any):

| Token | Description |
| ----- | ----------- |
| `{deliveryreference}` / `{deliveryname}` | Delivery name |
| `{deliverycreatedon}` | Delivery creation date (full format) |
| `{deliverylocation}` | Delivery location |
| `{deliverynotes}` | Delivery notes |
| `{deliveryfileurl}` | Delivery label image URL |
| `{deliveryqrcode}` | Delivery QR code URL |
| `{deliverycode128}` | Delivery barcode (Code 128) URL |

**Product tokens** (available when the macro is sent alongside a product purchase — `CoworkerProduct` or `BookingProduct`):

| Token | Description |
| ----- | ----------- |
| `{productname}` | Product name |
| `{productid}` | Product ID |
| `{productstocklevel}` | Current stock level |
| `{productstockalertlevel}` | Stock alert level |
| `{product}` | "Qty x Product Name" |
| `{price}` | Product price (formatted in location currency) |
| `{notes}` | Purchase notes |
| _(custom fields)_ | Any Product custom fields |

**Booking tokens** (available when the product purchase is linked to a booking):

| Token | Description |
| ----- | ----------- |
| `{bookingId}` | Booking ID |
| `{bookingNumber}` | Booking number (zero-padded) |
| `{bookingUniqueId}` | Booking GUID |
| `{bookingDurationInMinutes}` | Booking duration in minutes |
| `{resourceId}` | Resource ID |
| `{resourceName}` | Resource name |
| `{resourceDescription}` | Resource description |
| `{resourcetype}` | Resource type name |
| `{fromTime}` | Booking start date/time |
| `{toTime}` | Booking end date/time |
| `{desk}` | Desk name (or location name if none) |
| `{desknotes}` | Desk notes |
| `{confirmationContent}` | Resource email confirmation content |
| `{bookingTerminateUrl}` | Booking cancellation URL |
| `{accesstoken}` | Booking access code |
| `{price}` | Estimated booking cost (overrides product price) |
| `{pricewithcredits}` | Estimated cost after credits |
| `{additionals}` | Booking add-on products |
| `{additionals_with_description}` | Add-on products with descriptions |
| `{products}` | Product list (HTML formatted) |
| `{notes}` | Booking notes |
| _(custom fields)_ | Any Booking custom fields |

CannedResponses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus cannedresponses list --agent` | List all cannedresponses |
| `nexudus cannedresponses list --id <id> --agent` | Filter by single ID |
| `nexudus cannedresponses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus cannedresponses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus cannedresponses list --name <value> --agent` | Filter cannedresponses by properties |
| `nexudus cannedresponses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus cannedresponses get <id> --agent` | Get single cannedresponse |
| `nexudus cannedresponses create --business-id <value> --name <value> --agent` | Create cannedresponse |
| `nexudus cannedresponses update <id> --name "New Name" --agent` | Update cannedresponse |
| `nexudus cannedresponses delete <id> --yes --agent` | Delete cannedresponse (no prompt) |

#### CannedResponse list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Name of the message macro |
| `--subject` | string | Subject line shown in the customer's inbox when the message macro is delivered |
| `--message-text` | string | Body of the message macro; supports dynamic tokens (e.g. {salutations}) that Nexudus replaces with live data when the message is sent |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CannedResponse create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Name of the message macro |
| `--subject` | string | Subject line shown in the customer's inbox when the message macro is delivered |
| `--message-text` | string | Body of the message macro; supports dynamic tokens (e.g. {salutations}) that Nexudus replaces with live data when the message is sent |

#### CannedResponse update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Name of the message macro |
| `--subject` | string | Subject line shown in the customer's inbox when the message macro is delivered |
| `--message-text` | string | Body of the message macro; supports dynamic tokens (e.g. {salutations}) that Nexudus replaces with live data when the message is sent |

### CannedResponse (key fields)

`Id`, `BusinessName`, `Name`

<!-- END:GENERATED entity=CannedResponses -->
