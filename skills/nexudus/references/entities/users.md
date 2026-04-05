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
| `nexudus users create --full-name <value> --email <value> --password-salt <value> --last-help-visited <value> --invalid-login-attempts <value> --agent` | Create user |
| `nexudus users update <id> --name "New Name" --agent` | Update user |
| `nexudus users delete <id> --yes --agent` | Delete user (no prompt) |

#### User list filter options

`--full-name`, `--email`, `--access-token`, `--language`, `--preferred-language-id`, `--new-password`, `--password`, `--password-salt`, `--new-avatar-url`, `--clear-avatar-file`, `--application-id`, `--active`, `--is-admin`, `--a-p-i-access`, `--validated`, `--must-reset-password`, `--last-access`, `--from-last-access` (range), `--to-last-access` (range), `--devices`, `--on-new-email`, `--on-help-desk-msg`, `--on-new-wall-post`, `--on-new-member`, `--on-profile-changes`, `--on-new-blog-comment`, `--on-new-event-comment`, `--on-tariff-change`, `--on-booking-change`, `--on-tentative-booking-change`, `--on-purchases`, `--on-visitor-registration`, `--on-plaform-invoices`, `--receive-community-digest`, `--receive-every-message`, `--two-factor-secret`, `--email-call-back-guid`, `--last-help-visited`, `--from-last-help-visited` (range), `--to-last-help-visited` (range), `--last-received-community-thread-date`, `--from-last-received-community-thread-date` (range), `--to-last-received-community-thread-date` (range), `--last-received-community-message-date`, `--from-last-received-community-message-date` (range), `--to-last-received-community-message-date` (range), `--next-community-digest`, `--from-next-community-digest` (range), `--to-next-community-digest` (range), `--support-team-user-email`, `--invalid-login-attempts`, `--from-invalid-login-attempts` (range), `--to-invalid-login-attempts` (range), `--last-login-attempt`, `--from-last-login-attempt` (range), `--to-last-login-attempt` (range), `--on-access-control-errors`, `--next-help-desk-message-reminder`, `--from-next-help-desk-message-reminder` (range), `--to-next-help-desk-message-reminder` (range), `--on-member-removed-from-team`, `--on-virtual-office-tariff-change`, `--on-virtual-office-delivery-preference-update`, `--on-identity-check-update`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### User create options

`--full-name` (required), `--email` (required), `--access-token`, `--language`, `--preferred-language-id`, `--new-password`, `--password`, `--password-salt` (required), `--new-avatar-url`, `--clear-avatar-file`, `--application-id`, `--active`, `--is-admin`, `--a-p-i-access`, `--validated`, `--must-reset-password`, `--last-access`, `--devices`, `--on-new-email`, `--on-help-desk-msg`, `--on-new-wall-post`, `--on-new-member`, `--on-profile-changes`, `--on-new-blog-comment`, `--on-new-event-comment`, `--on-tariff-change`, `--on-booking-change`, `--on-tentative-booking-change`, `--on-purchases`, `--on-visitor-registration`, `--on-plaform-invoices`, `--receive-community-digest`, `--receive-every-message`, `--two-factor-secret`, `--email-call-back-guid`, `--businesses` (list, repeat flag), `--added-businesses` (list, repeat flag), `--removed-businesses` (list, repeat flag), `--user-roles` (list, repeat flag), `--added-user-roles` (list, repeat flag), `--removed-user-roles` (list, repeat flag), `--chat-rooms` (list, repeat flag), `--added-chat-rooms` (list, repeat flag), `--removed-chat-rooms` (list, repeat flag), `--last-help-visited` (required), `--last-received-community-thread-date`, `--last-received-community-message-date`, `--next-community-digest`, `--support-team-user-email`, `--invalid-login-attempts` (required), `--last-login-attempt`, `--on-access-control-errors`, `--next-help-desk-message-reminder`, `--on-member-removed-from-team`, `--on-virtual-office-tariff-change`, `--on-virtual-office-delivery-preference-update`, `--on-identity-check-update`

#### User update options

`--full-name`, `--email`, `--access-token`, `--language`, `--preferred-language-id`, `--new-password`, `--password`, `--password-salt`, `--new-avatar-url`, `--clear-avatar-file`, `--application-id`, `--active`, `--is-admin`, `--a-p-i-access`, `--validated`, `--must-reset-password`, `--last-access`, `--devices`, `--on-new-email`, `--on-help-desk-msg`, `--on-new-wall-post`, `--on-new-member`, `--on-profile-changes`, `--on-new-blog-comment`, `--on-new-event-comment`, `--on-tariff-change`, `--on-booking-change`, `--on-tentative-booking-change`, `--on-purchases`, `--on-visitor-registration`, `--on-plaform-invoices`, `--receive-community-digest`, `--receive-every-message`, `--two-factor-secret`, `--email-call-back-guid`, `--businesses` (list, repeat flag), `--added-businesses` (list, repeat flag), `--removed-businesses` (list, repeat flag), `--user-roles` (list, repeat flag), `--added-user-roles` (list, repeat flag), `--removed-user-roles` (list, repeat flag), `--chat-rooms` (list, repeat flag), `--added-chat-rooms` (list, repeat flag), `--removed-chat-rooms` (list, repeat flag), `--last-help-visited`, `--last-received-community-thread-date`, `--last-received-community-message-date`, `--next-community-digest`, `--support-team-user-email`, `--invalid-login-attempts`, `--last-login-attempt`, `--on-access-control-errors`, `--next-help-desk-message-reminder`, `--on-member-removed-from-team`, `--on-virtual-office-tariff-change`, `--on-virtual-office-delivery-preference-update`, `--on-identity-check-update`

**List properties (only returned by `get`, not by `list`):** `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `UserRoles`, `AddedUserRoles`, `RemovedUserRoles`, `ChatRooms`, `AddedChatRooms`, `RemovedChatRooms`

<!-- END:GENERATED entity=Users -->
