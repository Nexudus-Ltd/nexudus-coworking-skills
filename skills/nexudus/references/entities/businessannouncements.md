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

`--business-id`, `--name`, `--active`, `--new-image-url`, `--clear-image-file`, `--body`, `--show-button`, `--button-label`, `--button-url`, `--send-push-notification`, `--push-notification-text`, `--active-from`, `--from-active-from` (range), `--to-active-from` (range), `--active-to`, `--from-active-to` (range), `--to-active-to` (range), `--only-for-contacts`, `--only-for-members`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BusinessAnnouncement create options

`--business-id` (required), `--name` (required), `--active`, `--new-image-url`, `--clear-image-file`, `--body`, `--show-button`, `--button-label`, `--button-url`, `--send-push-notification`, `--push-notification-text`, `--active-from`, `--active-to`, `--only-for-contacts`, `--only-for-members`

#### BusinessAnnouncement update options

`--business-id`, `--name`, `--active`, `--new-image-url`, `--clear-image-file`, `--body`, `--show-button`, `--button-label`, `--button-url`, `--send-push-notification`, `--push-notification-text`, `--active-from`, `--active-to`, `--only-for-contacts`, `--only-for-members`

### BusinessAnnouncement (key fields)

`Id`, `BusinessName`, `Name`, `Active`, `Body`

<!-- END:GENERATED entity=BusinessAnnouncements -->
