# Users

<!-- BEGIN:GENERATED entity=Users -->

A User represents an administrator or staff member who can sign in to the Nexudus admin panel. Users are assigned roles that control their permissions and can be associated with one or more business locations.

Users support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus users list --agent` | List all users |
| `nexudus users list --id <id> --agent` | Filter by single ID |
| `nexudus users list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus users list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus users list --full-name <value> --email <value> --agent` | Filter users by properties |
| `nexudus users list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus users list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus users get <id> --agent` | Get single user |
| `nexudus users create --full-name <value> --email <value> --last-help-visited <value> --invalid-login-attempts <value> --agent` | Create user |
| `nexudus users update <id> --name "New Name" --agent` | Update user |
| `nexudus users delete <id> --yes --agent` | Delete user (no prompt) |

#### User list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--full-name` | string | Required full name shown for this staff account. |
| `--email` | string | Required valid email address used to identify and sign in to this staff account. |
| `--preferred-language-id` | long | ID of the optional location language used for this account's preferred interface and content language. |
| `--avatar-file-name` | string | Current file name of the avatar (read-only; upload via the corresponding URL field) |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--application-id` | long | ID of the optional marketplace application whose integration uses this account. |
| `--passport-number` | string | Read-only Nexudus Passport identifier; the platform verifies that it is unique. |
| `--passport-card-number` | string | Read-only Nexudus Passport card code; it must be a valid unused Passport card. |
| `--enable-passport-access` | bool | Whether this account is eligible for Nexudus Passport access; the platform enables it on user creation. |
| `--active` | bool | Whether this staff account is active; notification recipient queries generally require an active account. |
| `--is-admin` | bool | Whether this account has administrator access in addition to any permissions granted through UserRoles. |
| `--a-p-i-access` | bool | Whether this account may authenticate for API access. |
| `--validated` | bool | Whether the platform marks this account as validated. |
| `--must-reset-password` | bool | Whether the user must reset their sign-in password; the platform sets this when it generates a password. |
| `--last-access` | DateTime | Read-only UTC timestamp of the latest account access, rounded down to the nearest 15 minutes. |
| `--from-last-access` | range | |
| `--to-last-access` | range | |
| `--on-new-email` | bool | Whether to notify this active user about new internal messages for their locations. |
| `--on-help-desk-msg` | bool | Whether to notify this active user about new help desk messages for their locations. |
| `--on-new-wall-post` | bool | Whether to notify this active user about new community wall posts for their locations. |
| `--on-new-member` | bool | Whether to notify this active user when a new customer profile is created for their locations. |
| `--on-profile-changes` | bool | Whether to notify this user about customer profile changes. |
| `--on-new-blog-comment` | bool | Whether to notify this active user with a customer profile at the location about new blog comments. |
| `--on-new-event-comment` | bool | Whether to notify this active user with a customer profile at the location about new calendar-event comments. |
| `--on-tariff-change` | bool | Whether to notify this active user about plan changes; virtual-office plans instead use OnVirtualOfficeTariffChange. |
| `--on-booking-change` | bool | Whether to notify this active user about booking changes for their locations. |
| `--on-tentative-booking-change` | bool | Whether to notify this active user about tentative booking changes for their locations. |
| `--on-purchases` | bool | Whether to notify this active user about purchases for their locations. |
| `--on-visitor-registration` | bool | Whether to notify this user when visitors register at their locations. |
| `--on-plaform-invoices` | bool | Whether to notify this user about Nexudus platform invoices for their locations. |
| `--receive-community-digest` | bool | Whether this user is subscribed to scheduled community-board digest emails; new accounts inherit the location digest setting. |
| `--receive-every-message` | bool | Whether this user receives an email for each new community-board message instead of only digest notifications. |
| `--two-factor-enabled` | bool | Read-only indicator of whether two-factor authentication is enabled for this account. |
| `--default-business-id` | long | Read-only ID of the user's default location; the platform falls back to the first linked location when it is empty. |
| `--last-help-visited` | int | Internal identifier of the last help page viewed by this user. |
| `--from-last-help-visited` | range | |
| `--to-last-help-visited` | range | |
| `--last-received-community-thread-date` | DateTime | Internal timestamp of the latest community thread included in this user's notification tracking. |
| `--from-last-received-community-thread-date` | range | |
| `--to-last-received-community-thread-date` | range | |
| `--last-received-community-message-date` | DateTime | Internal timestamp of the latest community message included in this user's notification tracking. |
| `--from-last-received-community-message-date` | range | |
| `--to-last-received-community-message-date` | range | |
| `--next-community-digest` | DateTime | Internal timestamp for this user's next scheduled community digest. |
| `--from-next-community-digest` | range | |
| `--to-next-community-digest` | range | |
| `--support-team-user-email` | string | Internal support-team routing email associated with this account. |
| `--invalid-login-attempts` | int | Internal count of failed login attempts; the platform resets it after a successful password change and applies its lockout threshold. |
| `--from-invalid-login-attempts` | range | |
| `--to-invalid-login-attempts` | range | |
| `--last-login-attempt` | DateTime | Internal timestamp of the most recent failed login attempt, used with InvalidLoginAttempts for lockout handling. |
| `--from-last-login-attempt` | range | |
| `--to-last-login-attempt` | range | |
| `--on-access-control-errors` | bool | Whether to notify this user about access-control errors for their locations. |
| `--next-help-desk-message-reminder` | DateTime | Timestamp of the next help desk message reminder for this user. |
| `--from-next-help-desk-message-reminder` | range | |
| `--to-next-help-desk-message-reminder` | range | |
| `--on-member-removed-from-team` | bool | Whether to notify this user when a customer is removed from a team. |
| `--on-virtual-office-tariff-change` | bool | Whether to notify this active user about virtual-office plan changes for their locations. |
| `--on-virtual-office-delivery-preference-update` | bool | Whether to notify this user when a virtual-office customer updates delivery preferences. |
| `--on-identity-check-update` | bool | Whether to notify this user when a customer's identity-check status changes. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### User sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### User create options

| Option | Type | Description |
| --- | --- | --- |
| `--full-name` | string, required | Required full name shown for this staff account. |
| `--email` | string, required | Required valid email address used to identify and sign in to this staff account. |
| `--preferred-language-id` | long | ID of the optional location language used for this account's preferred interface and content language. |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--application-id` | long | ID of the optional marketplace application whose integration uses this account. |
| `--active` | bool | Whether this staff account is active; notification recipient queries generally require an active account. |
| `--is-admin` | bool | Whether this account has administrator access in addition to any permissions granted through UserRoles. |
| `--a-p-i-access` | bool | Whether this account may authenticate for API access. |
| `--validated` | bool | Whether the platform marks this account as validated. |
| `--must-reset-password` | bool | Whether the user must reset their sign-in password; the platform sets this when it generates a password. |
| `--last-access` | DateTime | Read-only UTC timestamp of the latest account access, rounded down to the nearest 15 minutes. |
| `--on-new-email` | bool | Whether to notify this active user about new internal messages for their locations. |
| `--on-help-desk-msg` | bool | Whether to notify this active user about new help desk messages for their locations. |
| `--on-new-wall-post` | bool | Whether to notify this active user about new community wall posts for their locations. |
| `--on-new-member` | bool | Whether to notify this active user when a new customer profile is created for their locations. |
| `--on-profile-changes` | bool | Whether to notify this user about customer profile changes. |
| `--on-new-blog-comment` | bool | Whether to notify this active user with a customer profile at the location about new blog comments. |
| `--on-new-event-comment` | bool | Whether to notify this active user with a customer profile at the location about new calendar-event comments. |
| `--on-tariff-change` | bool | Whether to notify this active user about plan changes; virtual-office plans instead use OnVirtualOfficeTariffChange. |
| `--on-booking-change` | bool | Whether to notify this active user about booking changes for their locations. |
| `--on-tentative-booking-change` | bool | Whether to notify this active user about tentative booking changes for their locations. |
| `--on-purchases` | bool | Whether to notify this active user about purchases for their locations. |
| `--on-visitor-registration` | bool | Whether to notify this user when visitors register at their locations. |
| `--on-plaform-invoices` | bool | Whether to notify this user about Nexudus platform invoices for their locations. |
| `--receive-community-digest` | bool | Whether this user is subscribed to scheduled community-board digest emails; new accounts inherit the location digest setting. |
| `--receive-every-message` | bool | Whether this user receives an email for each new community-board message instead of only digest notifications. |
| `--businesses` | list, repeat flag | List of locations this staff account can access; the account is included in location-scoped user queries only when linked to that location. |
| `--added-businesses` | list, repeat flag | IDs added to the Businesses relationship. |
| `--removed-businesses` | list, repeat flag | IDs removed from the Businesses relationship. |
| `--user-roles` | list, repeat flag | List of location-scoped user roles that grant this account permissions; administrator access may grant permissions independently. |
| `--added-user-roles` | list, repeat flag | IDs added to the UserRoles relationship. |
| `--removed-user-roles` | list, repeat flag | IDs removed from the UserRoles relationship. |
| `--added-chat-rooms` | list, repeat flag | IDs added to the ChatRooms relationship. |
| `--removed-chat-rooms` | list, repeat flag | IDs removed from the ChatRooms relationship. |
| `--last-help-visited` | int, required | Internal identifier of the last help page viewed by this user. |
| `--last-received-community-thread-date` | DateTime | Internal timestamp of the latest community thread included in this user's notification tracking. |
| `--last-received-community-message-date` | DateTime | Internal timestamp of the latest community message included in this user's notification tracking. |
| `--next-community-digest` | DateTime | Internal timestamp for this user's next scheduled community digest. |
| `--support-team-user-email` | string | Internal support-team routing email associated with this account. |
| `--invalid-login-attempts` | int, required | Internal count of failed login attempts; the platform resets it after a successful password change and applies its lockout threshold. |
| `--last-login-attempt` | DateTime | Internal timestamp of the most recent failed login attempt, used with InvalidLoginAttempts for lockout handling. |
| `--on-access-control-errors` | bool | Whether to notify this user about access-control errors for their locations. |
| `--next-help-desk-message-reminder` | DateTime | Timestamp of the next help desk message reminder for this user. |
| `--on-member-removed-from-team` | bool | Whether to notify this user when a customer is removed from a team. |
| `--on-virtual-office-tariff-change` | bool | Whether to notify this active user about virtual-office plan changes for their locations. |
| `--on-virtual-office-delivery-preference-update` | bool | Whether to notify this user when a virtual-office customer updates delivery preferences. |
| `--on-identity-check-update` | bool | Whether to notify this user when a customer's identity-check status changes. |

#### User update options

| Option | Type | Description |
| --- | --- | --- |
| `--full-name` | string | Required full name shown for this staff account. |
| `--email` | string | Required valid email address used to identify and sign in to this staff account. |
| `--preferred-language-id` | long | ID of the optional location language used for this account's preferred interface and content language. |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--application-id` | long | ID of the optional marketplace application whose integration uses this account. |
| `--active` | bool | Whether this staff account is active; notification recipient queries generally require an active account. |
| `--is-admin` | bool | Whether this account has administrator access in addition to any permissions granted through UserRoles. |
| `--a-p-i-access` | bool | Whether this account may authenticate for API access. |
| `--validated` | bool | Whether the platform marks this account as validated. |
| `--must-reset-password` | bool | Whether the user must reset their sign-in password; the platform sets this when it generates a password. |
| `--last-access` | DateTime | Read-only UTC timestamp of the latest account access, rounded down to the nearest 15 minutes. |
| `--on-new-email` | bool | Whether to notify this active user about new internal messages for their locations. |
| `--on-help-desk-msg` | bool | Whether to notify this active user about new help desk messages for their locations. |
| `--on-new-wall-post` | bool | Whether to notify this active user about new community wall posts for their locations. |
| `--on-new-member` | bool | Whether to notify this active user when a new customer profile is created for their locations. |
| `--on-profile-changes` | bool | Whether to notify this user about customer profile changes. |
| `--on-new-blog-comment` | bool | Whether to notify this active user with a customer profile at the location about new blog comments. |
| `--on-new-event-comment` | bool | Whether to notify this active user with a customer profile at the location about new calendar-event comments. |
| `--on-tariff-change` | bool | Whether to notify this active user about plan changes; virtual-office plans instead use OnVirtualOfficeTariffChange. |
| `--on-booking-change` | bool | Whether to notify this active user about booking changes for their locations. |
| `--on-tentative-booking-change` | bool | Whether to notify this active user about tentative booking changes for their locations. |
| `--on-purchases` | bool | Whether to notify this active user about purchases for their locations. |
| `--on-visitor-registration` | bool | Whether to notify this user when visitors register at their locations. |
| `--on-plaform-invoices` | bool | Whether to notify this user about Nexudus platform invoices for their locations. |
| `--receive-community-digest` | bool | Whether this user is subscribed to scheduled community-board digest emails; new accounts inherit the location digest setting. |
| `--receive-every-message` | bool | Whether this user receives an email for each new community-board message instead of only digest notifications. |
| `--businesses` | list, repeat flag | List of locations this staff account can access; the account is included in location-scoped user queries only when linked to that location. |
| `--added-businesses` | list, repeat flag | IDs added to the Businesses relationship. |
| `--removed-businesses` | list, repeat flag | IDs removed from the Businesses relationship. |
| `--user-roles` | list, repeat flag | List of location-scoped user roles that grant this account permissions; administrator access may grant permissions independently. |
| `--added-user-roles` | list, repeat flag | IDs added to the UserRoles relationship. |
| `--removed-user-roles` | list, repeat flag | IDs removed from the UserRoles relationship. |
| `--added-chat-rooms` | list, repeat flag | IDs added to the ChatRooms relationship. |
| `--removed-chat-rooms` | list, repeat flag | IDs removed from the ChatRooms relationship. |
| `--last-help-visited` | int | Internal identifier of the last help page viewed by this user. |
| `--last-received-community-thread-date` | DateTime | Internal timestamp of the latest community thread included in this user's notification tracking. |
| `--last-received-community-message-date` | DateTime | Internal timestamp of the latest community message included in this user's notification tracking. |
| `--next-community-digest` | DateTime | Internal timestamp for this user's next scheduled community digest. |
| `--support-team-user-email` | string | Internal support-team routing email associated with this account. |
| `--invalid-login-attempts` | int | Internal count of failed login attempts; the platform resets it after a successful password change and applies its lockout threshold. |
| `--last-login-attempt` | DateTime | Internal timestamp of the most recent failed login attempt, used with InvalidLoginAttempts for lockout handling. |
| `--on-access-control-errors` | bool | Whether to notify this user about access-control errors for their locations. |
| `--next-help-desk-message-reminder` | DateTime | Timestamp of the next help desk message reminder for this user. |
| `--on-member-removed-from-team` | bool | Whether to notify this user when a customer is removed from a team. |
| `--on-virtual-office-tariff-change` | bool | Whether to notify this active user about virtual-office plan changes for their locations. |
| `--on-virtual-office-delivery-preference-update` | bool | Whether to notify this user when a virtual-office customer updates delivery preferences. |
| `--on-identity-check-update` | bool | Whether to notify this user when a customer's identity-check status changes. |

#### User PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--on-new-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--support-team-user-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus users update <id> --full-name "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `UserRoles`, `AddedUserRoles`, `RemovedUserRoles`, `AddedChatRooms`, `RemovedChatRooms`

<!-- END:GENERATED entity=Users -->
