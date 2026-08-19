# Users

<!-- BEGIN:GENERATED entity=Users -->

A **User** represents an administrator or staff member who can sign in to the Nexudus admin panel. Users are assigned roles that control their permissions and can be associated with one or more business locations.

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
| `nexudus users create --full-name <value> --email <value> --language <value> --password-salt <value> --last-help-visited <value> --invalid-login-attempts <value> --agent` | Create user |
| `nexudus users update <id> --name "New Name" --agent` | Update user |
| `nexudus users delete <id> --yes --agent` | Delete user (no prompt) |

#### User list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--full-name` | string | The full name value for this user |
| `--email` | string | The email value for this user |
| `--access-token` | string | The access token value for this user |
| `--language` | enum | The language value for this user |
| `--preferred-language-id` | long | ID of the preferred language linked to this record |
| `--new-password` | string | The new password value for this user |
| `--password` | string | The password value for this user |
| `--password-salt` | string | The password salt value for this user |
| `--avatar-file-name` | string | Current file name of the avatar (read-only; upload via the corresponding URL field) |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--application-id` | long | ID of the application linked to this record |
| `--passport-number` | string | The passport number value for this user |
| `--passport-card-number` | string | The passport card number value for this user |
| `--enable-passport-access` | bool | Whether enable passport access is enabled |
| `--active` | bool | Whether this user is currently active |
| `--is-admin` | bool | Whether is admin is enabled |
| `--a-p-i-access` | bool | Whether api access is enabled |
| `--validated` | bool | Whether validated is enabled |
| `--must-reset-password` | bool | Whether must reset password is enabled |
| `--last-access` | DateTime | Date/time value for last access |
| `--from-last-access` | range | |
| `--to-last-access` | range | |
| `--devices` | string | The devices value for this user |
| `--on-new-email` | bool | Whether on new email is enabled |
| `--on-help-desk-msg` | bool | Whether on help desk msg is enabled |
| `--on-new-wall-post` | bool | Whether on new wall post is enabled |
| `--on-new-member` | bool | Whether on new member is enabled |
| `--on-profile-changes` | bool | Whether on profile changes is enabled |
| `--on-new-blog-comment` | bool | Whether on new blog comment is enabled |
| `--on-new-event-comment` | bool | Whether on new event comment is enabled |
| `--on-tariff-change` | bool | Whether on tariff change is enabled |
| `--on-booking-change` | bool | Whether on booking change is enabled |
| `--on-tentative-booking-change` | bool | Whether on tentative booking change is enabled |
| `--on-purchases` | bool | Whether on purchases is enabled |
| `--on-visitor-registration` | bool | Whether on visitor registration is enabled |
| `--on-plaform-invoices` | bool | Whether on plaform invoices is enabled |
| `--receive-community-digest` | bool | Whether receive community digest is enabled |
| `--receive-every-message` | bool | Whether receive every message is enabled |
| `--two-factor-enabled` | bool | Whether two factor enabled is enabled |
| `--two-factor-secret` | string | The two factor secret value for this user |
| `--email-call-back-guid` | string | Unique identifier (GUID) for the email call back |
| `--default-business-id` | long | ID of the default business linked to this record |
| `--last-help-visited` | int | The last help visited value for this user |
| `--from-last-help-visited` | range | |
| `--to-last-help-visited` | range | |
| `--last-received-community-thread-date` | DateTime | Date/time value for last received community thread date |
| `--from-last-received-community-thread-date` | range | |
| `--to-last-received-community-thread-date` | range | |
| `--last-received-community-message-date` | DateTime | Date/time value for last received community message date |
| `--from-last-received-community-message-date` | range | |
| `--to-last-received-community-message-date` | range | |
| `--next-community-digest` | DateTime | Date/time value for next community digest |
| `--from-next-community-digest` | range | |
| `--to-next-community-digest` | range | |
| `--support-team-user-email` | string | The support team user email value for this user |
| `--invalid-login-attempts` | int | The invalid login attempts value for this user |
| `--from-invalid-login-attempts` | range | |
| `--to-invalid-login-attempts` | range | |
| `--last-login-attempt` | DateTime | Date/time value for last login attempt |
| `--from-last-login-attempt` | range | |
| `--to-last-login-attempt` | range | |
| `--on-access-control-errors` | bool | Whether on access control errors is enabled |
| `--next-help-desk-message-reminder` | DateTime | Date/time value for next help desk message reminder |
| `--from-next-help-desk-message-reminder` | range | |
| `--to-next-help-desk-message-reminder` | range | |
| `--on-member-removed-from-team` | bool | Whether on member removed from team is enabled |
| `--on-virtual-office-tariff-change` | bool | Whether on virtual office tariff change is enabled |
| `--on-virtual-office-delivery-preference-update` | bool | Whether on virtual office delivery preference update is enabled |
| `--on-identity-check-update` | bool | Whether on identity check update is enabled |
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
| `--full-name` | string, required | The full name value for this user |
| `--email` | string, required | The email value for this user |
| `--access-token` | string | The access token value for this user |
| `--language` | enum, required | The language value for this user |
| `--preferred-language-id` | long | ID of the preferred language linked to this record |
| `--new-password` | string | The new password value for this user |
| `--password` | string | The password value for this user |
| `--password-salt` | string, required | The password salt value for this user |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--application-id` | long | ID of the application linked to this record |
| `--active` | bool | Whether this user is currently active |
| `--is-admin` | bool | Whether is admin is enabled |
| `--a-p-i-access` | bool | Whether api access is enabled |
| `--validated` | bool | Whether validated is enabled |
| `--must-reset-password` | bool | Whether must reset password is enabled |
| `--last-access` | DateTime | Date/time value for last access |
| `--devices` | string | The devices value for this user |
| `--on-new-email` | bool | Whether on new email is enabled |
| `--on-help-desk-msg` | bool | Whether on help desk msg is enabled |
| `--on-new-wall-post` | bool | Whether on new wall post is enabled |
| `--on-new-member` | bool | Whether on new member is enabled |
| `--on-profile-changes` | bool | Whether on profile changes is enabled |
| `--on-new-blog-comment` | bool | Whether on new blog comment is enabled |
| `--on-new-event-comment` | bool | Whether on new event comment is enabled |
| `--on-tariff-change` | bool | Whether on tariff change is enabled |
| `--on-booking-change` | bool | Whether on booking change is enabled |
| `--on-tentative-booking-change` | bool | Whether on tentative booking change is enabled |
| `--on-purchases` | bool | Whether on purchases is enabled |
| `--on-visitor-registration` | bool | Whether on visitor registration is enabled |
| `--on-plaform-invoices` | bool | Whether on plaform invoices is enabled |
| `--receive-community-digest` | bool | Whether receive community digest is enabled |
| `--receive-every-message` | bool | Whether receive every message is enabled |
| `--two-factor-secret` | string | The two factor secret value for this user |
| `--email-call-back-guid` | string | Unique identifier (GUID) for the email call back |
| `--businesses` | list, repeat flag | List of businesses linked to this record |
| `--added-businesses` | list, repeat flag | The added businesses value for this user |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this user |
| `--user-roles` | list, repeat flag | List of user roles linked to this record |
| `--added-user-roles` | list, repeat flag | The added user roles value for this user |
| `--removed-user-roles` | list, repeat flag | The removed user roles value for this user |
| `--chat-rooms` | list, repeat flag | List of chat rooms linked to this record |
| `--added-chat-rooms` | list, repeat flag | The added chat rooms value for this user |
| `--removed-chat-rooms` | list, repeat flag | The removed chat rooms value for this user |
| `--last-help-visited` | int, required | The last help visited value for this user |
| `--last-received-community-thread-date` | DateTime | Date/time value for last received community thread date |
| `--last-received-community-message-date` | DateTime | Date/time value for last received community message date |
| `--next-community-digest` | DateTime | Date/time value for next community digest |
| `--support-team-user-email` | string | The support team user email value for this user |
| `--invalid-login-attempts` | int, required | The invalid login attempts value for this user |
| `--last-login-attempt` | DateTime | Date/time value for last login attempt |
| `--on-access-control-errors` | bool | Whether on access control errors is enabled |
| `--next-help-desk-message-reminder` | DateTime | Date/time value for next help desk message reminder |
| `--on-member-removed-from-team` | bool | Whether on member removed from team is enabled |
| `--on-virtual-office-tariff-change` | bool | Whether on virtual office tariff change is enabled |
| `--on-virtual-office-delivery-preference-update` | bool | Whether on virtual office delivery preference update is enabled |
| `--on-identity-check-update` | bool | Whether on identity check update is enabled |

#### User update options

| Option | Type | Description |
| --- | --- | --- |
| `--full-name` | string | The full name value for this user |
| `--email` | string | The email value for this user |
| `--access-token` | string | The access token value for this user |
| `--language` | enum | The language value for this user |
| `--preferred-language-id` | long | ID of the preferred language linked to this record |
| `--new-password` | string | The new password value for this user |
| `--password` | string | The password value for this user |
| `--password-salt` | string | The password salt value for this user |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--application-id` | long | ID of the application linked to this record |
| `--active` | bool | Whether this user is currently active |
| `--is-admin` | bool | Whether is admin is enabled |
| `--a-p-i-access` | bool | Whether api access is enabled |
| `--validated` | bool | Whether validated is enabled |
| `--must-reset-password` | bool | Whether must reset password is enabled |
| `--last-access` | DateTime | Date/time value for last access |
| `--devices` | string | The devices value for this user |
| `--on-new-email` | bool | Whether on new email is enabled |
| `--on-help-desk-msg` | bool | Whether on help desk msg is enabled |
| `--on-new-wall-post` | bool | Whether on new wall post is enabled |
| `--on-new-member` | bool | Whether on new member is enabled |
| `--on-profile-changes` | bool | Whether on profile changes is enabled |
| `--on-new-blog-comment` | bool | Whether on new blog comment is enabled |
| `--on-new-event-comment` | bool | Whether on new event comment is enabled |
| `--on-tariff-change` | bool | Whether on tariff change is enabled |
| `--on-booking-change` | bool | Whether on booking change is enabled |
| `--on-tentative-booking-change` | bool | Whether on tentative booking change is enabled |
| `--on-purchases` | bool | Whether on purchases is enabled |
| `--on-visitor-registration` | bool | Whether on visitor registration is enabled |
| `--on-plaform-invoices` | bool | Whether on plaform invoices is enabled |
| `--receive-community-digest` | bool | Whether receive community digest is enabled |
| `--receive-every-message` | bool | Whether receive every message is enabled |
| `--two-factor-secret` | string | The two factor secret value for this user |
| `--email-call-back-guid` | string | Unique identifier (GUID) for the email call back |
| `--businesses` | list, repeat flag | List of businesses linked to this record |
| `--added-businesses` | list, repeat flag | The added businesses value for this user |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this user |
| `--user-roles` | list, repeat flag | List of user roles linked to this record |
| `--added-user-roles` | list, repeat flag | The added user roles value for this user |
| `--removed-user-roles` | list, repeat flag | The removed user roles value for this user |
| `--chat-rooms` | list, repeat flag | List of chat rooms linked to this record |
| `--added-chat-rooms` | list, repeat flag | The added chat rooms value for this user |
| `--removed-chat-rooms` | list, repeat flag | The removed chat rooms value for this user |
| `--last-help-visited` | int | The last help visited value for this user |
| `--last-received-community-thread-date` | DateTime | Date/time value for last received community thread date |
| `--last-received-community-message-date` | DateTime | Date/time value for last received community message date |
| `--next-community-digest` | DateTime | Date/time value for next community digest |
| `--support-team-user-email` | string | The support team user email value for this user |
| `--invalid-login-attempts` | int | The invalid login attempts value for this user |
| `--last-login-attempt` | DateTime | Date/time value for last login attempt |
| `--on-access-control-errors` | bool | Whether on access control errors is enabled |
| `--next-help-desk-message-reminder` | DateTime | Date/time value for next help desk message reminder |
| `--on-member-removed-from-team` | bool | Whether on member removed from team is enabled |
| `--on-virtual-office-tariff-change` | bool | Whether on virtual office tariff change is enabled |
| `--on-virtual-office-delivery-preference-update` | bool | Whether on virtual office delivery preference update is enabled |
| `--on-identity-check-update` | bool | Whether on identity check update is enabled |

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

**List properties (only returned by `get`, not by `list`):** `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `UserRoles`, `AddedUserRoles`, `RemovedUserRoles`, `ChatRooms`, `AddedChatRooms`, `RemovedChatRooms`

#### User enum values

| Option | Valid values |
| ------ | ------------ |
| `--language` | `1` EnglishUS, `2` Spanish, `3` EnglishUK |

<!-- END:GENERATED entity=Users -->
