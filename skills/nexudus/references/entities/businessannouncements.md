# BusinessAnnouncements

<!-- BEGIN:GENERATED entity=BusinessAnnouncements -->

A **BusinessAnnouncement** is a notification displayed to customers on the members portal and mobile app. Announcements support plain text only (no bold, italics, or lists) and can include an optional image and a call-to-action button.

Use `ActiveFrom` and `ActiveTo` to schedule when the announcement is visible. Use `OnlyForContacts` and `OnlyForMembers` to control the audience:

| OnlyForContacts | OnlyForMembers | Audience                                     |
| --------------- | -------------- | -------------------------------------------- |
| false           | false          | All customers (contacts and members)         |
| true            | false          | Contacts only (no active contract)           |
| false           | true           | Members only (with an active contract)       |

Announcement images should ideally be 600x350 pixels (12:7 aspect ratio). Set `NewImageUrl` to a URL to upload a new image, or set `ClearImage` to true to remove the current image.

BusinessAnnouncements support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus businessannouncements list --agent` | List all businessannouncements |
| `nexudus businessannouncements list --id <id> --agent` | Filter by single ID |
| `nexudus businessannouncements list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus businessannouncements list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus businessannouncements list --name <value> --active <value> --agent` | Filter businessannouncements by properties |
| `nexudus businessannouncements list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus businessannouncements get <id> --agent` | Get single businessannouncement |
| `nexudus businessannouncements create --business-id <value> --name <value> --agent` | Create businessannouncement |
| `nexudus businessannouncements update <id> --name "New Name" --agent` | Update businessannouncement |
| `nexudus businessannouncements delete <id> --yes --agent` | Delete businessannouncement (no prompt) |

#### BusinessAnnouncement list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Announcement title |
| `--active` | bool | Whether the announcement is active and visible to customers |
| `--new-image-url` | string | URL of a new image to upload (ideal size 600x350 pixels, 12:7 aspect ratio) |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--body` | string | Announcement body text (plain text only, no formatting) |
| `--show-button` | bool | Whether to display a call-to-action button in the announcement |
| `--button-label` | string | Text displayed on the call-to-action button |
| `--button-url` | string | URL the call-to-action button redirects to (must start with https://) |
| `--send-push-notification` | bool | Whether to send a push notification to customers when the announcement is published |
| `--push-notification-text` | string | Text of the push notification sent to customers |
| `--active-from` | DateTime | Date from which the announcement is visible to customers (publish from) |
| `--from-active-from` | range | |
| `--to-active-from` | range | |
| `--active-to` | DateTime | Date until which the announcement is visible to customers (publish to) |
| `--from-active-to` | range | |
| `--to-active-to` | range | |
| `--only-for-contacts` | bool | Restrict announcement visibility to contacts (customers without an active contract) |
| `--only-for-members` | bool | Restrict announcement visibility to members (customers with an active contract) |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BusinessAnnouncement create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Announcement title |
| `--active` | bool | Whether the announcement is active and visible to customers |
| `--new-image-url` | string | URL of a new image to upload (ideal size 600x350 pixels, 12:7 aspect ratio) |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--body` | string | Announcement body text (plain text only, no formatting) |
| `--show-button` | bool | Whether to display a call-to-action button in the announcement |
| `--button-label` | string | Text displayed on the call-to-action button |
| `--button-url` | string | URL the call-to-action button redirects to (must start with https://) |
| `--send-push-notification` | bool | Whether to send a push notification to customers when the announcement is published |
| `--push-notification-text` | string | Text of the push notification sent to customers |
| `--active-from` | DateTime | Date from which the announcement is visible to customers (publish from) |
| `--active-to` | DateTime | Date until which the announcement is visible to customers (publish to) |
| `--only-for-contacts` | bool | Restrict announcement visibility to contacts (customers without an active contract) |
| `--only-for-members` | bool | Restrict announcement visibility to members (customers with an active contract) |

#### BusinessAnnouncement update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Announcement title |
| `--active` | bool | Whether the announcement is active and visible to customers |
| `--new-image-url` | string | URL of a new image to upload (ideal size 600x350 pixels, 12:7 aspect ratio) |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--body` | string | Announcement body text (plain text only, no formatting) |
| `--show-button` | bool | Whether to display a call-to-action button in the announcement |
| `--button-label` | string | Text displayed on the call-to-action button |
| `--button-url` | string | URL the call-to-action button redirects to (must start with https://) |
| `--send-push-notification` | bool | Whether to send a push notification to customers when the announcement is published |
| `--push-notification-text` | string | Text of the push notification sent to customers |
| `--active-from` | DateTime | Date from which the announcement is visible to customers (publish from) |
| `--active-to` | DateTime | Date until which the announcement is visible to customers (publish to) |
| `--only-for-contacts` | bool | Restrict announcement visibility to contacts (customers without an active contract) |
| `--only-for-members` | bool | Restrict announcement visibility to members (customers with an active contract) |

### BusinessAnnouncement (key fields)

`Id`, `BusinessName`, `Name`, `Active`, `Body`

<!-- END:GENERATED entity=BusinessAnnouncements -->
