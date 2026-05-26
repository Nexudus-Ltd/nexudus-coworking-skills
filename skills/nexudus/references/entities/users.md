# Users

<!-- BEGIN:GENERATED entity=Users -->

Users support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus users list --agent` | List all users |
| `nexudus users list --id <id> --agent` | Filter by single ID |
| `nexudus users list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus users list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus users list --full-name <value> --email <value> --agent` | Filter users by properties |
| `nexudus users list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus users get <id> --agent` | Get single user |
| `nexudus users create --full-name <value> --email <value> --language <value> --password-salt <value> --last-help-visited <value> --invalid-login-attempts <value> --agent` | Create user |
| `nexudus users update <id> --name "New Name" --agent` | Update user |
| `nexudus users delete <id> --yes --agent` | Delete user (no prompt) |

#### User list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--full-name` | string |  |
| `--email` | string |  |
| `--access-token` | string |  |
| `--language` | enum |  |
| `--preferred-language-id` | long |  |
| `--new-password` | string |  |
| `--password` | string |  |
| `--password-salt` | string |  |
| `--new-avatar-url` | string |  |
| `--clear-avatar-file` | bool |  |
| `--application-id` | long |  |
| `--active` | bool |  |
| `--is-admin` | bool |  |
| `--a-p-i-access` | bool |  |
| `--validated` | bool |  |
| `--must-reset-password` | bool |  |
| `--last-access` | DateTime |  |
| `--from-last-access` | range | |
| `--to-last-access` | range | |
| `--devices` | string |  |
| `--on-new-email` | bool |  |
| `--on-help-desk-msg` | bool |  |
| `--on-new-wall-post` | bool |  |
| `--on-new-member` | bool |  |
| `--on-profile-changes` | bool |  |
| `--on-new-blog-comment` | bool |  |
| `--on-new-event-comment` | bool |  |
| `--on-tariff-change` | bool |  |
| `--on-booking-change` | bool |  |
| `--on-tentative-booking-change` | bool |  |
| `--on-purchases` | bool |  |
| `--on-visitor-registration` | bool |  |
| `--on-plaform-invoices` | bool |  |
| `--receive-community-digest` | bool |  |
| `--receive-every-message` | bool |  |
| `--two-factor-secret` | string |  |
| `--email-call-back-guid` | string |  |
| `--last-help-visited` | int |  |
| `--from-last-help-visited` | range | |
| `--to-last-help-visited` | range | |
| `--last-received-community-thread-date` | DateTime |  |
| `--from-last-received-community-thread-date` | range | |
| `--to-last-received-community-thread-date` | range | |
| `--last-received-community-message-date` | DateTime |  |
| `--from-last-received-community-message-date` | range | |
| `--to-last-received-community-message-date` | range | |
| `--next-community-digest` | DateTime |  |
| `--from-next-community-digest` | range | |
| `--to-next-community-digest` | range | |
| `--support-team-user-email` | string |  |
| `--invalid-login-attempts` | int |  |
| `--from-invalid-login-attempts` | range | |
| `--to-invalid-login-attempts` | range | |
| `--last-login-attempt` | DateTime |  |
| `--from-last-login-attempt` | range | |
| `--to-last-login-attempt` | range | |
| `--on-access-control-errors` | bool |  |
| `--next-help-desk-message-reminder` | DateTime |  |
| `--from-next-help-desk-message-reminder` | range | |
| `--to-next-help-desk-message-reminder` | range | |
| `--on-member-removed-from-team` | bool |  |
| `--on-virtual-office-tariff-change` | bool |  |
| `--on-virtual-office-delivery-preference-update` | bool |  |
| `--on-identity-check-update` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### User create options

| Option | Type | Description |
| --- | --- | --- |
| `--full-name` | string, required |  |
| `--email` | string, required |  |
| `--access-token` | string |  |
| `--language` | enum, required |  |
| `--preferred-language-id` | long |  |
| `--new-password` | string |  |
| `--password` | string |  |
| `--password-salt` | string, required |  |
| `--new-avatar-url` | string |  |
| `--clear-avatar-file` | bool |  |
| `--application-id` | long |  |
| `--active` | bool |  |
| `--is-admin` | bool |  |
| `--a-p-i-access` | bool |  |
| `--validated` | bool |  |
| `--must-reset-password` | bool |  |
| `--last-access` | DateTime |  |
| `--devices` | string |  |
| `--on-new-email` | bool |  |
| `--on-help-desk-msg` | bool |  |
| `--on-new-wall-post` | bool |  |
| `--on-new-member` | bool |  |
| `--on-profile-changes` | bool |  |
| `--on-new-blog-comment` | bool |  |
| `--on-new-event-comment` | bool |  |
| `--on-tariff-change` | bool |  |
| `--on-booking-change` | bool |  |
| `--on-tentative-booking-change` | bool |  |
| `--on-purchases` | bool |  |
| `--on-visitor-registration` | bool |  |
| `--on-plaform-invoices` | bool |  |
| `--receive-community-digest` | bool |  |
| `--receive-every-message` | bool |  |
| `--two-factor-secret` | string |  |
| `--email-call-back-guid` | string |  |
| `--businesses` | list, repeat flag |  |
| `--added-businesses` | list, repeat flag |  |
| `--removed-businesses` | list, repeat flag |  |
| `--user-roles` | list, repeat flag |  |
| `--added-user-roles` | list, repeat flag |  |
| `--removed-user-roles` | list, repeat flag |  |
| `--chat-rooms` | list, repeat flag |  |
| `--added-chat-rooms` | list, repeat flag |  |
| `--removed-chat-rooms` | list, repeat flag |  |
| `--last-help-visited` | int, required |  |
| `--last-received-community-thread-date` | DateTime |  |
| `--last-received-community-message-date` | DateTime |  |
| `--next-community-digest` | DateTime |  |
| `--support-team-user-email` | string |  |
| `--invalid-login-attempts` | int, required |  |
| `--last-login-attempt` | DateTime |  |
| `--on-access-control-errors` | bool |  |
| `--next-help-desk-message-reminder` | DateTime |  |
| `--on-member-removed-from-team` | bool |  |
| `--on-virtual-office-tariff-change` | bool |  |
| `--on-virtual-office-delivery-preference-update` | bool |  |
| `--on-identity-check-update` | bool |  |

#### User update options

| Option | Type | Description |
| --- | --- | --- |
| `--full-name` | string |  |
| `--email` | string |  |
| `--access-token` | string |  |
| `--language` | enum |  |
| `--preferred-language-id` | long |  |
| `--new-password` | string |  |
| `--password` | string |  |
| `--password-salt` | string |  |
| `--new-avatar-url` | string |  |
| `--clear-avatar-file` | bool |  |
| `--application-id` | long |  |
| `--active` | bool |  |
| `--is-admin` | bool |  |
| `--a-p-i-access` | bool |  |
| `--validated` | bool |  |
| `--must-reset-password` | bool |  |
| `--last-access` | DateTime |  |
| `--devices` | string |  |
| `--on-new-email` | bool |  |
| `--on-help-desk-msg` | bool |  |
| `--on-new-wall-post` | bool |  |
| `--on-new-member` | bool |  |
| `--on-profile-changes` | bool |  |
| `--on-new-blog-comment` | bool |  |
| `--on-new-event-comment` | bool |  |
| `--on-tariff-change` | bool |  |
| `--on-booking-change` | bool |  |
| `--on-tentative-booking-change` | bool |  |
| `--on-purchases` | bool |  |
| `--on-visitor-registration` | bool |  |
| `--on-plaform-invoices` | bool |  |
| `--receive-community-digest` | bool |  |
| `--receive-every-message` | bool |  |
| `--two-factor-secret` | string |  |
| `--email-call-back-guid` | string |  |
| `--businesses` | list, repeat flag |  |
| `--added-businesses` | list, repeat flag |  |
| `--removed-businesses` | list, repeat flag |  |
| `--user-roles` | list, repeat flag |  |
| `--added-user-roles` | list, repeat flag |  |
| `--removed-user-roles` | list, repeat flag |  |
| `--chat-rooms` | list, repeat flag |  |
| `--added-chat-rooms` | list, repeat flag |  |
| `--removed-chat-rooms` | list, repeat flag |  |
| `--last-help-visited` | int |  |
| `--last-received-community-thread-date` | DateTime |  |
| `--last-received-community-message-date` | DateTime |  |
| `--next-community-digest` | DateTime |  |
| `--support-team-user-email` | string |  |
| `--invalid-login-attempts` | int |  |
| `--last-login-attempt` | DateTime |  |
| `--on-access-control-errors` | bool |  |
| `--next-help-desk-message-reminder` | DateTime |  |
| `--on-member-removed-from-team` | bool |  |
| `--on-virtual-office-tariff-change` | bool |  |
| `--on-virtual-office-delivery-preference-update` | bool |  |
| `--on-identity-check-update` | bool |  |

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

<!-- END:GENERATED entity=Users -->
