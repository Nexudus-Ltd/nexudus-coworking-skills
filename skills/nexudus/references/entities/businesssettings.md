# BusinessSettings

<!-- BEGIN:GENERATED entity=BusinessSettings -->

A **BusinessSetting** represents a single name/value configuration entry for a location. Each setting is identified by a dotted key (`Name`) and holds its value as a string (`Value`). Together, the collection of BusinessSetting records for a location forms the full configuration surface — covering billing, portal features, check-in behaviour, mobile apps, communications, security and more.

Boolean settings store `"True"` or `"False"` as the value string. Numeric settings store the number as a string. Date settings store the date in ISO 8601 format. All other settings store plain text, HTML or Markdown as appropriate.

To read a setting, list BusinessSettings filtered by location and `Name`. To change a setting, update the matching record's `Value`.

---

## Complete setting reference

### Billing — Invoice details

| Key | Type | Description |
| --- | ---- | ----------- |
| `Billing.BillToName` | text | Company / trading name shown on invoices |
| `Billing.BillToAddress` | text | Billing address shown on invoices |
| `Billing.BillToCity` | text | City shown on invoices |
| `Billing.BillToPostCode` | text | Zip / post code shown on invoices |
| `Billing.BillToState` | text | State / Province shown on invoices |
| `Billing.BillToCountry` | text | Country (entity ID) shown on invoices |
| `General.BusinessTaxIDNumber` | text | VAT / Tax ID number |

### Billing — Bank details

| Key | Type | Description |
| --- | ---- | ----------- |
| `Billing.BankName` | text | Bank name included at text of invoices |
| `Billing.BankCode` | text | Bank code |
| `Billing.SortCode` | text | Sort code / routing number |
| `Billing.AccountNumber` | text | Account number |

### Billing — Payment notifications

| Key | Type | Description |
| --- | ---- | ----------- |
| `Payments.NotifyOnInvoiceDefault` | bool | Enable notifications about new invoices for customers registered from now on |
| `Payments.NotifyOnNewPaymentDefault` | bool | Enable notifications about successful payments for customers registered from now on |
| `Payments.NotifyOnFailedPaymentDefault` | bool | Enable notifications about failed payments for customers registered from now on |
| `Payments.SuccessNotificationsEmail` | text | Email address to send a copy of every successful payment notification to |
| `Payments.FailureNotificationsEmail` | text | Email address to send a copy of every failed payment notification to |

### Billing — Invoice contents

| Key | Type | Description |
| --- | ---- | ----------- |
| `Billing.CreateZeroValueInvoices` | bool | Create invoices even when total is zero |
| `Billing.UsePeriodAsInvoiceDate` | bool | Use the contract billing period start date as the invoice issue date |
| `Billing.InvoicesIncludeProductNotes` | bool | Include product sale notes in invoice lines |
| `Billing.InvoicesIncludeExtraServiceNotes` | bool | Include time-credit sale notes in invoice lines |
| `Billing.InvoicesIncludeBookingNotes` | bool | Include booking notes in invoice lines |
| `Billing.InvoicesIncludeTimePassNotes` | bool | Include pass sale notes in invoice lines |
| `Billing.InvoicesIncludeFullyCreditedBookings` | bool | Include lines for bookings fully paid by credit |

### Billing — Invoice split

| Key | Type | Description |
| --- | ---- | ----------- |
| `Payments.CreateAnInvoicePerSpace` | bool | Create an invoice per location based on transactions |
| `Billing.SegregateContracts` | bool | Create an invoice per contract if a customer renews more than one |
| `Payments.CreateAnInvoicePerPurchaseOrder` | bool | Create an invoice per purchase order reference |
| `Billing.InvoiceSegregation.UsePreviousDay` | bool | Set secondary invoice date to one day earlier than primary |
| `Billing.SegregateBookings` | bool | Move bookings to secondary invoice |
| `Billing.SegregateProducts` | bool | Move products to secondary invoice |
| `Billing.SegregateTimePasses` | bool | Move passes to secondary invoice |
| `Billing.SegregateTickets` | bool | Move event tickets to secondary invoice |
| `Billing.SegregateCharges` | bool | Move charges to secondary invoice |

### Billing — Invoice formatting

| Key | Type | Description |
| --- | ---- | ----------- |
| `Billing.InvoiceFormat.Sales` | text | Invoice reference format pattern. Use {1:0000} for sequential number, {0} for location reference, {year}/{month}/{day} for date parts |
| `Billing.InvoiceFormat.Draft` | text | Invoice draft reference format pattern |
| `Billing.InvoiceFormat.SeparateCreditNotes` | bool | Use a different number sequence for credit notes |
| `Billing.InvoiceFormat.CreditNote` | text | Credit note reference format pattern |
| `Payments.PaymentReferenceGenerator` | text | Payment reference format (ePaymentReferenceGeneratorType enum value) |

### Billing — Amount rounding

| Key | Type | Description |
| --- | ---- | ----------- |
| `Billing.Rounding.Enable` | bool | Enable amount rounding |
| `Billing.Rounding.Line.DecimalPoints` | number | Decimal places for rounding each invoice line |
| `Billing.Rounding.DecimalPoints` | number | Decimal places for rounding invoice totals |

### Billing — Locked period

| Key | Type | Description |
| --- | ---- | ----------- |
| `Billing.LockDates` | date | Lock invoices and payments made before this date |

### Billing — Tax

| Key | Type | Description |
| --- | ---- | ----------- |
| `Billing.AddTaxToInvoices` | bool | Add tax to invoices |
| `Billing.RequireTaxRate` | bool | Require all sales to have a defined tax rate |
| `Billing.PricesIncludeTax` | bool | Prices typed in the back-end include tax |
| `Billing.DisplayTaxOnWebsite` | bool | Display prices including tax on website, app and emails |
| `Billing.TaxValue` | text | Default tax rate (entity ID of the tax rate record) |

### Billing — Financial accounts

| Key | Type | Description |
| --- | ---- | ----------- |
| `Billing.RequireFinancialAccount` | bool | Require all sales to have a financial account |

### Billing — Proposals

| Key | Type | Description |
| --- | ---- | ----------- |
| `Billing.DoNotIssueInvoice` | bool | Leave contracts issued by proposals as paused — do not issue invoices |

### Payments & Currency

| Key | Type | Description |
| --- | ---- | ----------- |
| `Payments.Currency` | text | Secondary currency (entity ID) — payments processed in this currency |
| `Payments.ExchangeRate` | number | Exchange rate from primary to secondary currency |
| `Payments.RemindToPayEvery` | number | Number of days between payment reminders |

### Checkout — Plans

| Key | Type | Description |
| --- | ---- | ----------- |
| `Forms.Enquiries.Enabled` | bool | Allow customers to enquire about plans |
| `Forms.Enquiries.Tour.Enabled` | bool | Include a tour as part of the enquiry |
| `Forms.Enquiries.TariffIds.OnlyEnquire` | bool | Prevent selected plans from being purchased directly |

### Checkout — Products

| Key | Type | Description |
| --- | ---- | ----------- |
| `Store.AlwaysInvoice` | bool | Always invoice products immediately when purchased |

### Checkout — Bookings

| Key | Type | Description |
| --- | ---- | ----------- |
| `Bookings.CancelUnPaidBookingsForNonSubscribers` | bool | Require up-front payment for bookings made by contacts |
| `Bookings.CancelUnPaidBookingsForSubscribers` | bool | Require up-front payment for bookings made by members |
| `Bookings.AutoPayContactBookings` | bool | Invoice and collect payment for contact bookings as they end |
| `Bookings.AutoPayMemberBookings` | bool | Invoice and collect payment for member bookings as they end |
| `Bookings.ChargeBookingsImmediately` | bool | Calculate price and use credit immediately when booking is requested |
| `Bookings.RequestDrafts` | bool | Allow customers to request a quote instead of confirming |

### Checkout — Event tickets

| Key | Type | Description |
| --- | ---- | ----------- |
| `Events.CanCancelTickets` | bool | Allow customers to cancel event tickets |
| `Events.CancelUnpaidTickets` | bool | Automatically cancel unpaid tickets purchased by contacts |
| `Events.InvoiceAttendee` | bool | Invoice the event buyer instead of their team paying customer |

### Bookings — General

| Key | Type | Description |
| --- | ---- | ----------- |
| `Bookings.EnableGuestBookings` | bool | Allow new customers to register and book from calendar |
| `Bookings.DoNotCreateGuestAccount` | bool | Do not create account for guest bookers (reversed: False = create account) |
| `Bookings.RegisterConactBookersAsVisitors` | bool | Register all contacts as visitors when they book |
| `Bookings.DoNotRegisterKnownCustomersAsVisitors` | bool | Do not register known customers as visitors when added as attendees (reversed) |
| `Bookings.CancelIfNotChekedIn` | bool | Require attendees to check in using NexBoard and cancel no-shows |
| `Bookings.RequireConfirmation.Members` | bool | Bookings made by members must be confirmed first |
| `Bookings.RequireConfirmation.Contacts` | bool | Bookings made by contacts must be confirmed first |

### Bookings — Notifications

| Key | Type | Description |
| --- | ---- | ----------- |
| `Bookings.SendConfirmationEmail` | bool | Send booking confirmation email to customer |
| `Bookings.SendConfirmationToVisitors` | bool | Send booking confirmation to every guest added to a booking |
| `Bookings.SendReminderEmail` | bool | Send booking reminder email before booking begins |
| `Bookings.ReminderEmailMinutes` | number | Minutes before each booking to send reminder |
| `Bookings.SendAccessCode` | bool | Include Internet Access Token in booking emails |

### Bookings — Charges & payments

| Key | Type | Description |
| --- | ---- | ----------- |
| `Bookings.PaidBookingsCancellationPolicy` | text | Cancellation policy for invoiced bookings (ePaidBookingsCancellationPolicy enum value) |
| `Bookings.UseCreditToPayBookingProducts` | bool | Use available credit to pay for products added to bookings |
| `Bookings.RejectIfNoCreditIsAvailable` | bool | Reject bookings if customers do not have enough credit |
| `Bookings.DueDateIgnoreProducts` | bool | Ignore recurrent products when calculating booking due dates |

### Bookings — Calendar

| Key | Type | Description |
| --- | ---- | ----------- |
| `Calendars.ShowMemberDetailsInFeed` | bool | Show customer names and company in calendar |
| `Calendars.IncludeEventsInCalendar` | bool | Include events connected to a resource in calendar |
| `Calendars.IncludeEventsInFeed` | bool | Include events in calendar iCal feed |
| `PublicWebSite.ShowAllBookings` | bool | Show bookings from all users in calendar |
| `Members.ViewTeamBookings` | bool | Show bookings made by team members on home page |
| `Calendars.IncludeLinkedResources` | bool | Show combined resources as booked in calendar |
| `Bookings.ShowEndDate` | bool | Let users book across different days |
| `Bookings.AcceptPastBookings` | bool | Accept bookings in the past |
| `Bookings.IncludeBookingCreditInPrice` | bool | Consider money credit when showing booking prices |
| `Calendars.DefaultView` | text | Default calendar view (eCalendarDefaultView enum value) |
| `Bookings.DefaultBookingLength` | text | Default booking length |
| `Bookings.IntervalLimit` | text | Time picker interval |

### Bookings — Dynamic pricing

| Key | Type | Description |
| --- | ---- | ----------- |
| `Nexudus.ML.ApplyFrom` | date | Apply dynamic pricing only to bookings made from this date |

### Bookings — Teams & attendance

| Key | Type | Description |
| --- | ---- | ----------- |
| `Bookings.AttendanceBookingReminders.Enabled` | bool | Send office attendance reminders |
| `Bookings.AttendanceReport.Enabled` | bool | Send weekly attendance report to team administrators |
| `Members.AllowRemoveTeamMembers` | bool | Team administrators can remove members from teams |
| `Forms.TeamAdminsCanUpdateCards` | bool | Team administrators can update access card details |

### Check-in — General

| Key | Type | Description |
| --- | ---- | ----------- |
| `Members.NotifyOnLowCredit` | bool | Notify users when running low on access time |
| `Members.NotifyOnLowCreditHours` | number | Notify when less than this many hours of credit remain |
| `Members.NotifyOnAutoCheckout` | bool | Notify users when they are automatically checked out |
| `Checkin.AlwaysRecordByMinute` | bool | Record multiple check-ins on the same calendar day |
| `Checkin.DailyCutOffTime` | text | Daily cut-off time for check-in |
| `MobileApp.NexClicker.MaxCapacity` | number | Building capacity (people) |

### Check-in — Pay as you go

| Key | Type | Description |
| --- | ---- | ----------- |
| `Checkin.PayAsYouGo` | bool | Enable pay-as-you-go access |
| `Checkin.DiscountBookings` | bool | Exclude time used in bookings from check-in duration |
| `Checkin.PayAsYouGoMembersPayWithContract` | bool | Members pay pay-as-you-go charges via their contract |
| `Checkin.PayAsYouGoMinPrice` | number | Minimum daily price |
| `Checkin.PayAsYouGoMaxPrice` | number | Maximum daily price |

### Check-in — Network & devices

| Key | Type | Description |
| --- | ---- | ----------- |
| `Security.DisableAutoChecking` | bool | Disable auto check-in via MAC address (reversed: False = auto check-in enabled) |
| `PublicWebSite.Visitors.CreateAccessTokns` | bool | Generate an access token for every pre-registered visitor |
| `PublicWebSite.Visitors.CreateAccessTokns.DefaultDuration` | number | Default duration in minutes for visitor access tokens |
| `Checkin.DeviceCountLimit` | number | Maximum number of devices per user |
| `PublicWebSite.Visitors.CreateAccessTokns.MaximumDevicesVisitor` | number | Maximum number of devices per visitor |

### Sign-up & registration

| Key | Type | Description |
| --- | ---- | ----------- |
| `Members.CanSignup` | bool | Allow customers to sign up online |
| `Members.SendWelcomeEmail` | bool | Send welcome email with access details to new users |
| `Members.UseInvitationLink` | bool | Restrict sign-ups to invite only |
| `Signup.UseCaptcha` | bool | Protect sign-up with Google Captcha |
| `Signup.AskForPassword` | bool | Let customers create their own password at sign-up |
| `Signup.ShowStoreOnSignUp` | bool | Offer additional products during sign-up |
| `Signup.KeepNewAccountsOnHold` | bool | Keep new customer accounts suspended by default |
| `Signup.MemberMustChooseAPricePlan` | bool | Suspend new accounts that do not complete payment |
| `Signup.GooglePlusSignUp` | bool | Allow sign-up with Google |
| `Signup.GooglePlusSignIn` | bool | Allow sign-in with Google |
| `Security.AutoRegister` | bool | Automatically register existing customers at new locations |
| `Security.AllowPasswordReset` | bool | Let users change their password |
| `Security.AutoGeneratePincode` | bool | Auto-generate 5-digit access pin-codes |
| `Security.GenerateUniquePincode` | bool | Require pin-codes to be unique across all customers |

### New customer access defaults

| Key | Type | Description |
| --- | ---- | ----------- |
| `Access.Defaults.Network` | bool | New customers have access to IT network by default |
| `Access.Defaults.Bookings` | bool | New customers can make bookings by default |
| `Access.Defaults.Products` | bool | New customers can purchase products by default |
| `Access.Defaults.Events` | bool | New customers can purchase events by default |
| `Access.Defaults.Community` | bool | New customers can use discussion boards by default |

### Forms — Sign-up personal details

| Key | Type | Description |
| --- | ---- | ----------- |
| `SignupForm.LandLine` | text | Phone field requirement (eFormFieldStatus value) |
| `SignupForm.MobilePhone` | text | Mobile / Cell field requirement (eFormFieldStatus value) |
| `SignupForm.Gender` | text | Gender field requirement (eFormFieldStatus value) |
| `SignupForm.DateOfBirth` | text | Date of birth field requirement (eFormFieldStatus value) |
| `SignupForm.ShowContactSection` | bool | Show contact details section in sign-up and profile forms |
| `SignupForm.ShowBillingSection` | bool | Show billing details section in sign-up and profile forms |
| `SignupForm.ShowProfileSection` | bool | Show profile details section in sign-up form |
| `SignupForm.Avatar` | text | Photo profile field requirement (eFormFieldStatus value) |

### Forms — Contact details fields

| Key | Type | Description |
| --- | ---- | ----------- |
| `Forms.Address` | text | Address form field requirement (eFormFieldStatus value) |
| `Forms.CityName` | text | City form field requirement (eFormFieldStatus value) |
| `Forms.State` | text | State form field requirement (eFormFieldStatus value) |
| `Forms.PostCode` | text | Postcode / zip form field requirement (eFormFieldStatus value) |
| `Forms.Country` | text | Country form field requirement (eFormFieldStatus value) |

### Forms — Billing details fields

| Key | Type | Description |
| --- | ---- | ----------- |
| `Forms.BillingName` | text | Company name billing field requirement (eFormFieldStatus value) |
| `Forms.TaxIDNumber` | text | Tax / Company ID billing field requirement (eFormFieldStatus value) |
| `Forms.BillingAddress` | text | Address billing field requirement (eFormFieldStatus value) |
| `Forms.BillingCityName` | text | City billing field requirement (eFormFieldStatus value) |
| `Forms.BillingState` | text | State billing field requirement (eFormFieldStatus value) |
| `Forms.BillingPostCode` | text | Postcode / zip billing field requirement (eFormFieldStatus value) |
| `Forms.BillingEmail` | text | Billing email field requirement (eFormFieldStatus value) |
| `Forms.BillingCountry` | text | Billing country field requirement (eFormFieldStatus value) |

### Forms — Profile fields

| Key | Type | Description |
| --- | ---- | ----------- |
| `Forms.CompanyName` | text | Company name profile field requirement (eFormFieldStatus value) |
| `Forms.BusinessArea` | text | Industry profile field requirement (eFormFieldStatus value) |
| `Forms.Position` | text | Position profile field requirement (eFormFieldStatus value) |
| `Forms.ProfileSummary` | text | Profile bio field requirement (eFormFieldStatus value) |
| `Forms.PorfileTags` | text | Skills profile field requirement (eFormFieldStatus value) |
| `Forms.ProfileWebiste` | text | Website profile field requirement (eFormFieldStatus value) |

### Legal terms & policies

| Key | Type | Description |
| --- | ---- | ----------- |
| `Legal.VisitorTermsAndConditions` | markdown | Visitor terms and conditions shown during NexIO registration |
| `Legal.CheckoutTermsAndConditions` | markdown | Checkout terms shown before booking or payment |
| `Legal.Privacy` | markdown | Privacy policy linked in portal footer |
| `Legal.Cookies` | markdown | Cookies policy linked in portal footer and login page |

### Portal — Appearance & version

| Key | Type | Description |
| --- | ---- | ----------- |
| `Nexudus.NextJS.Version` | text | Members Portal version |
| `PublicWebSite.IncludeInLocationSelector` | bool | Display this location in website and app location selector |
| `PublicWebSite.ShowOnlyRegisteredWithLocations` | bool | List only locations customers are registered with |

### Portal — Features

| Key | Type | Description |
| --- | ---- | ----------- |
| `PublicWebSite.MyAccount` | bool | Enable My Account section |
| `PublicWebSite.Help` | bool | Enable help-desk section |
| `PublicWebSite.Deliveries` | bool | Enable deliveries section |
| `PublicWebSite.Contact` | bool | Enable contact form |
| `PublicWebSite.CommunityBoard` | bool | Enable discussion boards section |
| `PublicWebSite.Events` | bool | Enable events and tickets section |
| `Members.PublicDirectory` | bool | Enable directory section |
| `Blog.Enabled` | bool | Enable articles section |
| `PublicWebSite.Attendance` | bool | Enable team attendance section |
| `PublicWebSite.Visitors` | bool | Enable visitor registration section |
| `PublicWebSite.Tour` | bool | Enable tour request form |
| `PublicWebSite.Metrics` | bool | Enable metrics section |
| `PublicWebSite.Notifications` | bool | Enable notifications section |

### Portal — Home page

| Key | Type | Description |
| --- | ---- | ----------- |
| `PublicWebSite.Home.UseCommunityDashboard` | bool | Show community feed when customers log in |
| `HomePage.Banner` | bool | Show rotating banner on home page |
| `HomePage.ShowIconBar` | bool | Show shortcuts to commonly used sections |
| `HomePage.ShowClaimBar` | bool | Show primary claim text |
| `HomePage.ShowServicesBar` | bool | Show offered services section |
| `HomePage.ShowFooterClaimBar` | bool | Show secondary claim text |
| `HomePage.ShowCheckedInMembers` | bool | Show list of checked-in customers |
| `HomePage.NewsletterSignUp` | bool | Show newsletter sign-up section |

### Portal — Banner

| Key | Type | Description |
| --- | ---- | ----------- |
| `HomePage.BannerText` | text | Banner main text |
| `HomePage.BannerSmallText` | text | Banner secondary text |

### Portal — Shortcuts

| Key | Type | Description |
| --- | ---- | ----------- |
| `HomePage.AboutUsIcon` | bool | Show shortcut to about us |
| `HomePage.EventsIcon` | bool | Show shortcut to events |
| `HomePage.DirectoryIcon` | bool | Show shortcut to directory |
| `HomePage.BookingsIcon` | bool | Show shortcut to bookings calendar |
| `HomePage.MyAccountIcon` | bool | Show shortcut to my account or sign-up |

### Portal — Primary claim

| Key | Type | Description |
| --- | ---- | ----------- |
| `HomePage.ClaimText` | text | Primary claim main text |
| `HomePage.ClaimSmallTextLogout` | text | Primary claim secondary text for logged-out users |
| `HomePage.ClaimSmallTextLogin` | text | Primary claim secondary text for logged-in users |

### Portal — Service tiles

| Key | Type | Description |
| --- | ---- | ----------- |
| `HomePage.ShowWorkspaceService` | bool | Show workspace tile |
| `HomePage.WorkSpaceShortText` | text | Workspace tile heading |
| `HomePage.WorkSpaceLongText` | text | Workspace tile description |
| `HomePage.ShowBookingsService` | bool | Show bookings tile |
| `HomePage.BookingsShortText` | text | Bookings tile heading |
| `HomePage.BookingsLongText` | text | Bookings tile description |
| `HomePage.ShowCommunityService` | bool | Show community tile |
| `HomePage.CommunityShortText` | text | Community tile heading |
| `HomePage.CommunityLongText` | text | Community tile description |
| `HomePage.ShowChildCareService` | bool | Show child care tile |
| `HomePage.ChildCareShortText` | text | Child care tile heading |
| `HomePage.ChildCareLongText` | text | Child care tile description |
| `HomePage.ShowBenefitsService` | bool | Show benefits tile |
| `HomePage.BenefitsShortText` | text | Benefits tile heading |
| `HomePage.BenefitsLongText` | text | Benefits tile description |
| `HomePage.ShowEventsService` | bool | Show events tile |
| `HomePage.EventsShortText` | text | Events tile heading |
| `HomePage.EventsLongText` | text | Events tile description |

### Portal — Secondary claim & footer

| Key | Type | Description |
| --- | ---- | ----------- |
| `HomePage.FooterClaimText` | text | Secondary claim main text |
| `Footer.SayingText` | text | Footer saying text |
| `Footer.SayingAuthor` | text | Footer saying author |

### Portal — Social networks

| Key | Type | Description |
| --- | ---- | ----------- |
| `Social.Twitter` | text | X (Twitter) handle |
| `Social.Flickr` | text | Flickr URL |
| `Social.Facebook` | text | Facebook URL |
| `Social.Instagram` | text | Instagram handle |

### Portal — Access to sections

These settings control who can see each section of the members portal. Values are integers from the `ePublicWebsiteAccess` enum: `1` = Everyone, `2` = Logged-in users, `3` = Only members, `4` = Only contacts.

| Key | Type | Description |
| --- | ---- | ----------- |
| `Access.Global` | int (1–4) | Access level for entire portal |
| `Access.HomePage` | int (1–4) | Access level for home page |
| `Access.AboutUs` | int (1–4) | Access level for about us page |
| `Access.Help` | int (1–4) | Access level for help-desk module |
| `Access.Events` | int (1–4) | Access level for events list and calendar |
| `Access.Bookings` | int (1–4) | Access level for booking pages |
| `Access.Directory` | int (1–4) | Access level for directory pages |
| `Access.CommunityBoard` | int (1–4) | Access level for discussion board pages |
| `Access.Blog` | int (1–4) | Access level for blog and article pages |
| `Access.Contact` | int (1–4) | Access level for contact pages |
| `Access.Account.Payments` | int (1–4) | Access level for payments page |
| `Access.Account.PricePlans` | int (1–4) | Access level for plan selection page |
| `Access.Account.Allowances` | int (1–4) | Access level for benefits page |
| `Access.Account.Store` | int (1–4) | Access level for products store page |
| `Access.Discounts` | int (1–4) | Access level for perks and benefits page |
| `Access.FAQs` | int (1–4) | Access level for FAQ pages |

### Portal — Data visibility

| Key | Type | Description |
| --- | ---- | ----------- |
| `Access.Data.Events` | text | Events visibility scope (eDataVisibilityCriteria enum value) |
| `Access.Data.Blog` | text | Articles visibility scope |
| `Access.Data.Perks` | text | Perks and discounts visibility scope |
| `Access.Data.FAQs` | text | FAQ articles visibility scope |
| `Access.Data.Resources` | text | Bookable resources visibility scope |
| `Access.Data.Products` | text | Products visibility scope |

### My Account features

| Key | Type | Description |
| --- | ---- | ----------- |
| `Members.AllowTariffChange` | bool | Users can change or cancel their plan |
| `Members.AllowBookings` | bool | Users can request new bookings |
| `Members.AllowChangeBookings` | bool | Users can change existing bookings |
| `Members.AllowHelpMessages` | bool | Users can submit help-desk requests |
| `Members.ViewInvoices` | bool | Users can view and pay invoices |
| `Members.PrintInvoices` | bool | Users can print invoices |

### Discussion boards

| Key | Type | Description |
| --- | ---- | ----------- |
| `PublicWebSite.CommunityBoard.GroupsOnly` | bool | Customers can only post to groups they have access to |
| `Digest.AutoSignUpMembers` | bool | Sign up new users to daily digest |
| `Digest.SendToMembers` | bool | Enable digest notifications to members |
| `Digest.SendToContacts` | bool | Enable digest notifications to contacts |
| `Digest.SubjectFormat` | text | Digest email subject line format |

### Articles

| Key | Type | Description |
| --- | ---- | ----------- |
| `Blog.AllowComments` | bool | Let users post comments on articles |
| `Blog.AutoPublishComments` | bool | Automatically publish comments on articles |

### Events

| Key | Type | Description |
| --- | ---- | ----------- |
| `Events.SendAccessCode` | bool | Include internet access code in event tickets |
| `Events.SendReminders` | bool | Send 24-hour reminder before events |

### Newsletter

| Key | Type | Description |
| --- | ---- | ----------- |
| `Newsletter.AutoSignUpMembers` | bool | Add every new customer as subscriber |
| `Newsletter.DefaultOptIn` | bool | Newsletter subscribers active by default |

### Directory

| Key | Type | Description |
| --- | ---- | ----------- |
| `Directory.OnlyInvoicingSpace` | bool | List only invoicing-location customers (reversed: False = list all locations) |
| `Directory.DirectoryRecords` | text | Directory record types (eDirectoryRecordType enum value) |
| `Directory.DirectoryContents` | text | Directory contents type (eDirectoryContents enum value) |
| `Directory.ProfileTags` | text | Profile skills and industries |

### Tours

| Key | Type | Description |
| --- | ---- | ----------- |
| `PublicWebSite.Tour.RequiresConfirmation` | bool | Tour requests must be confirmed by an administrator |
| `PublicWebSite.Tour.TimeSlots.Enabled` | bool | Tours can only be booked at specific hours/days |
| `PublicWebSite.Tour.TimeSlots` | text | Tour time slots configuration |
| `PublicWebSite.Tour.Host` | text | Tour host user (entity ID) |

### About us

| Key | Type | Description |
| --- | ---- | ----------- |
| `PublicWebSite.AboutUs` | bool | Enable About Us module |

### Space dashboard

| Key | Type | Description |
| --- | ---- | ----------- |
| `Dashboard.Enabled` | bool | Enable space dashboard |

### Communications — Email

| Key | Type | Description |
| --- | ---- | ----------- |
| `Email.Disable` | bool | Disable notifications system (reversed: False = enabled) |
| `Email.FromName` | text | From name on outgoing emails |
| `Email.FromEmail` | text | Reply-to email address |
| `Email.CCEmail` | text | CC email address |
| `Email.CCOEmail` | text | BCC email address |
| `Email.CCO` | bool | BCC the reply-to email on all outgoing emails |
| `Email.UseDefaultSettings` | bool | Use Nexudus servers to deliver email |
| `Email.ServerName` | text | Custom SMTP server host |
| `Email.SMTPPort` | number | Custom SMTP server port |
| `Email.UseSSL` | bool | Connect to SMTP using SSL |
| `Email.ServerUsername` | text | SMTP username |
| `Email.ServerPassword` | text | SMTP password |

### Security & access

| Key | Type | Description |
| --- | ---- | ----------- |
| `Access.TwoFactor.Enforce` | bool | Enforce Two Factor Authentication for admin users |
| `Access.TwoFactor.EnforceFromDate` | date | Enforce 2FA from this date |
| `Security.Crm.EnforceOpportunityOwnership` | bool | Only admins or owner can change CRM opportunities |
| `Nexudus.Oauth.AccessTokenExpireTimeSpan` | text | Admin session timeout |
| `PublicWebsite.AllowedDomains` | text | Authorized redirect domains |

### Nexudus subscription

| Key | Type | Description |
| --- | ---- | ----------- |
| `Nexudus.SupportUrl` | text | Dedicated Support Agent URL |
| `Nexudus.TrialDays` | number | Trial period in days |

### Mobile app — Passport features

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.DisplayHomeVertically` | bool | Display home sections vertically |
| `MobileApp.Feed` | bool | Enable Discussion boards section |
| `MobileApp.Directory` | bool | Enable directory section |
| `MobileApp.Bookings` | bool | Enable bookings and floor plans |
| `MobileApp.Events` | bool | Enable events and tickets |
| `MobileApp.Blog` | bool | Enable articles section |
| `MobileApp.Me` | bool | Enable my account section |
| `MobileApp.LocationServices` | bool | Enable location services |
| `MobileApp.FeedPrivate` | bool | Enable private messages |
| `MobileApp.Help` | bool | Enable help-desk section |
| `Google.Analytics.v4.Mobile` | bool | Enable Google Analytics 4 |

### Mobile app — Passport home page

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.Home.CheckedInMembers` | bool | Show checked-in customer count |
| `MobileApp.Home.OngoingBookings` | bool | Show ongoing bookings |
| `MobileApp.Home.UpcomingBookings` | bool | Show upcoming bookings |
| `MobileApp.Home.Blog` | bool | Show articles |
| `MobileApp.Home.Events` | bool | Show events |
| `MobileApp.Home.Benefits` | bool | Show customer credits and benefits |
| `MobileApp.Home.Invoices` | bool | Show unpaid invoices |
| `MobileApp.Home.Deliveries` | bool | Show uncollected deliveries |
| `MobileApp.Home.Elatec` | bool | Show print release (Elatec) |
| `MobileApp.Home.CommunityBoard` | bool | Show discussion boards |
| `MobileApp.Home.Visitors` | bool | Show upcoming visitors |
| `MobileApp.Home.AccessControl` | bool | Show access control section |
| `MobileApp.Home.QRCode` | bool | Show customer QR code |

### Mobile app — Passport white-label

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.PrimaryColor` | text | Primary colour |
| `MobileApp.SecondaryColor` | text | Secondary colour |
| `MobileApp.TertiaryColor` | text | Tertiary colour |
| `MobileApp.FontFamily` | text | Font family (eAppFontName enum value) |

### Mobile app — Passport access control

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.Access.Enabled` | bool | Enable access control page in app |
| `MobileApp.Access.Url` | text | Access control page URL |

### Mobile app — Passport custom page

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.CustomPage.Enabled` | bool | Enable custom page in app |
| `MobileApp.CustomPage.Title` | text | Custom page title |
| `MobileApp.CustomPage.Url` | text | Custom page URL |
| `MobileApp.CustomPage.ShowOnHomePage` | bool | Show custom page on app home page |
| `MobileApp.CustomPage.Secret` | text | Custom page shared secret |

### Mobile app — Push notifications

| Key | Type | Description |
| --- | ---- | ----------- |
| `OneSignal.AppKey` | text | OneSignal App Id |
| `OneSignal.RestKey` | text | OneSignal REST Key |

### Mobile app — App download URLs

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.iOS.Url` | text | iOS app download URL |
| `MobileApp.Android.Url` | text | Android app download URL |

### Mobile app — Automation tiles & deep links

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.iOS.TeamId` | text | iOS team id |
| `MobileApp.iOS.BundleId` | text | iOS bundle id |
| `MobileApp.Android.PackageName` | text | Android package name |
| `MobileApp.Android.CertFingerprint` | text | Android certificate fingerprint |
| `AutomationTiles.SharedSecret` | text | Automation tiles shared secret |

### NexIO — Visitor check-in

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.FrontDesk.Version` | text | NexIO version |
| `MobileApp.FrontDesk.Checkin.Fields.Email` | bool | Ask for visitor email |
| `MobileApp.FrontDesk.Checkin.RequireEmail` | bool | Make visitor email required |
| `MobileApp.FrontDesk.Checkin.Fields.Member` | bool | Ask visitor to choose a customer as host |
| `MobileApp.FrontDesk.Checkin.RequireMember` | bool | Require visitor to choose a host |
| `MobileApp.FrontDesk.Checkin.Fields.PhoneNumber` | bool | Ask for visitor phone number |
| `MobileApp.FrontDesk.Checkin.Fields.PhoneNumber.Required` | bool | Visitor phone number is required |
| `MobileApp.FrontDesk.Checkin.Fields.CompanyName` | bool | Ask for visitor company name |
| `MobileApp.FrontDesk.Checkin.Fields.Reason` | bool | Ask for reason for visit |
| `MobileApp.FrontDesk.Checkin.ShowNewsletter` | bool | Show newsletter opt-in check-box |
| `MobileApp.FrontDesk.Checkin.CustomerFilter` | text | Customer selection menu filters |

### NexIO — Language / messages

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.FrontDesk.Checkin.WelcomeMessage` | text | Welcome message |
| `MobileApp.FrontDesk.Checkin.HomeMessage` | text | Home message |
| `MobileApp.FrontDesk.Checkin.TapToStartMessage` | text | Tap to start message |
| `MobileApp.FrontDesk.Checkin.IamVisitorMessage` | text | I am a visitor message |
| `MobileApp.FrontDesk.Checkin.IamAMemberMessage` | text | I am a member message |
| `MobileApp.FrontDesk.Checkin.DoYouHaveVisitorCodeMessage` | text | Do you have a code message |
| `MobileApp.FrontDesk.Checkin.WelcomeTitle` | text | Welcome title after check-in |
| `MobileApp.FrontDesk.Checkin.WelcomeVisitor` | text | Welcome text for visitors |
| `MobileApp.FrontDesk.Checkin.WelcomeEvent` | text | Welcome text for event attendees |
| `MobileApp.FrontDesk.Checkin.WelcomeMember` | text | Welcome text for customers |
| `MobileApp.FrontDesk.Checkin.ByeByeTitle` | text | Goodbye title after check-out |
| `MobileApp.FrontDesk.Checkin.ByeByeMessage` | text | Goodbye message after check-out |

### NexBoard

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.NexBoard.ShowLastCleaned` | bool | Show when the resource was last cleaned |

### NexEvents

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.NexBoard.Checkin.QRCodes` | bool | Include QR code in attendee confirmation email |

### NexDelivery

| Key | Type | Description |
| --- | ---- | ----------- |
| `MobileApp.FrontDesk.Delivery.HideSignatureScreen` | bool | Hide collection signature screens (reversed: False = shown) |
| `MobileApp.FrontDesk.Delivery.HidePrintButton` | bool | Hide delivery label print button (reversed: False = shown) |

### NexKIOSK

| Key | Type | Description |
| --- | ---- | ----------- |
| `NexKiosk.Enabled` | bool | Enable NexKIOSK |
| `NexKiosk.QuickSale.Enabled` | bool | Enable Quick Sale mode |
| `NexKiosk.QuickSale.CoworkerId` | text | Customer for Quick Sale invoices (entity ID) |
| `NexKiosk.ShowAllInvoices` | bool | Show all invoices, including those created outside NexKiosk |
| `NexKiosk.POS.Payments.Enabled` | bool | Show payment add/refund buttons |
| `NexKiosk.POS.CoworkerType` | text | Customer type filter for POS (eCoworkerType enum value) |
| `NexKiosk.KIOSK.Discounts.Enabled` | bool | Allow discounts in Kiosk mode |
| `NexKiosk.DisableAddToBill` | bool | Disable add-to-bill for customers (reversed: False = allowed) |
| `NexKiosk.StripeLocationId` | text | Stripe Location Id |

BusinessSettings support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus businesssettings list --agent` | List all businesssettings |
| `nexudus businesssettings list --id <id> --agent` | Filter by single ID |
| `nexudus businesssettings list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus businesssettings list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus businesssettings list --name <value> --value <value> --agent` | Filter businesssettings by properties |
| `nexudus businesssettings list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus businesssettings get <id> --agent` | Get single businesssetting |
| `nexudus businesssettings create --business-id <value> --name <value> --agent` | Create businesssetting |
| `nexudus businesssettings update <id> --name "New Name" --agent` | Update businesssetting |
| `nexudus businesssettings delete <id> --yes --agent` | Delete businesssetting (no prompt) |

#### BusinessSetting list filter options

`--business-id`, `--name`, `--value`

#### BusinessSetting create options

`--business-id` (required), `--name` (required), `--value`

#### BusinessSetting update options

`--business-id`, `--name`, `--value`

### BusinessSetting (key fields)

`Id`, `Name`, `Value`

<!-- END:GENERATED entity=BusinessSettings -->
