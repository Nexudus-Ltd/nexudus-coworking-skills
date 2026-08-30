# BusinessAnnouncements

<!-- BEGIN:GENERATED entity=BusinessAnnouncements -->

A BusinessAnnouncement is a location announcement shown to customers in the Members Portal and app, with optional plain-text content, image, and call-to-action button. Its public availability is scheduled by UTC ActiveFrom and ActiveTo values.

BusinessAnnouncements support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus businessannouncements list --agent` | List all businessannouncements |
| `nexudus businessannouncements list --id <id> --agent` | Filter by single ID |
| `nexudus businessannouncements list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus businessannouncements list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus businessannouncements list --business-name <value> --name <value> --agent` | Filter businessannouncements by properties |
| `nexudus businessannouncements list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus businessannouncements list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus businessannouncements get <id> --agent` | Get single businessannouncement |
| `nexudus businessannouncements create --business-id <value> --name <value> --agent` | Create businessannouncement |
| `nexudus businessannouncements update <id> --name "New Name" --agent` | Update businessannouncement |
| `nexudus businessannouncements delete <id> --yes --agent` | Delete businessannouncement (no prompt) |

#### BusinessAnnouncement list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location where this announcement is published; a network location makes it available to locations in that network. |
| `--business-name` | string | Business name |
| `--name` | string | Required title displayed with the announcement. |
| `--image-file-name` | string | Current image file name |
| `--new-image-url` | string | URL of a new image to upload (ideal size 600x350 pixels, 12:7 aspect ratio) |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--body` | string | Plain-text announcement body; HTML formatting is not supported. |
| `--show-button` | bool | Whether to display the optional call-to-action button with this announcement. |
| `--button-label` | string | Text displayed on the call-to-action button when ShowButton is enabled. |
| `--button-url` | string | Destination URL for the call-to-action button when ShowButton is enabled. |
| `--send-push-notification` | bool | Whether this announcement is configured to send a push notification; scheduling is currently driven by ActiveFrom on create or update. |
| `--push-notification-text` | string | Text configured for the announcement's push notification. |
| `--active-from` | DateTime | UTC publish-from date and time; the active query requires this value to be strictly earlier than the current UTC time, and create or update schedules its push job at this time. |
| `--from-active-from` | range | |
| `--to-active-from` | range | |
| `--active-to` | DateTime | Optional UTC publish-until date and time; an announcement remains active only while this value is strictly later than the current UTC time. |
| `--from-active-to` | range | |
| `--to-active-to` | range | |
| `--only-for-contacts` | bool | Whether the announcement is marked for contacts, meaning customers without an active contract; the current active-announcement query does not apply this audience flag. |
| `--only-for-members` | bool | Whether the announcement is marked for members, meaning customers with an active contract; the current active-announcement query does not apply this audience flag. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BusinessAnnouncement sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### BusinessAnnouncement create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location where this announcement is published; a network location makes it available to locations in that network. |
| `--name` | string, required | Required title displayed with the announcement. |
| `--new-image-url` | string | URL of a new image to upload (ideal size 600x350 pixels, 12:7 aspect ratio) |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--body` | string | Plain-text announcement body; HTML formatting is not supported. |
| `--show-button` | bool | Whether to display the optional call-to-action button with this announcement. |
| `--button-label` | string | Text displayed on the call-to-action button when ShowButton is enabled. |
| `--button-url` | string | Destination URL for the call-to-action button when ShowButton is enabled. |
| `--send-push-notification` | bool | Whether this announcement is configured to send a push notification; scheduling is currently driven by ActiveFrom on create or update. |
| `--push-notification-text` | string | Text configured for the announcement's push notification. |
| `--active-from` | DateTime | UTC publish-from date and time; the active query requires this value to be strictly earlier than the current UTC time, and create or update schedules its push job at this time. |
| `--active-to` | DateTime | Optional UTC publish-until date and time; an announcement remains active only while this value is strictly later than the current UTC time. |
| `--only-for-contacts` | bool | Whether the announcement is marked for contacts, meaning customers without an active contract; the current active-announcement query does not apply this audience flag. |
| `--only-for-members` | bool | Whether the announcement is marked for members, meaning customers with an active contract; the current active-announcement query does not apply this audience flag. |

#### BusinessAnnouncement update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location where this announcement is published; a network location makes it available to locations in that network. |
| `--name` | string | Required title displayed with the announcement. |
| `--new-image-url` | string | URL of a new image to upload (ideal size 600x350 pixels, 12:7 aspect ratio) |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--body` | string | Plain-text announcement body; HTML formatting is not supported. |
| `--show-button` | bool | Whether to display the optional call-to-action button with this announcement. |
| `--button-label` | string | Text displayed on the call-to-action button when ShowButton is enabled. |
| `--button-url` | string | Destination URL for the call-to-action button when ShowButton is enabled. |
| `--send-push-notification` | bool | Whether this announcement is configured to send a push notification; scheduling is currently driven by ActiveFrom on create or update. |
| `--push-notification-text` | string | Text configured for the announcement's push notification. |
| `--active-from` | DateTime | UTC publish-from date and time; the active query requires this value to be strictly earlier than the current UTC time, and create or update schedules its push job at this time. |
| `--active-to` | DateTime | Optional UTC publish-until date and time; an announcement remains active only while this value is strictly later than the current UTC time. |
| `--only-for-contacts` | bool | Whether the announcement is marked for contacts, meaning customers without an active contract; the current active-announcement query does not apply this audience flag. |
| `--only-for-members` | bool | Whether the announcement is marked for members, meaning customers with an active contract; the current active-announcement query does not apply this audience flag. |

### BusinessAnnouncement (key fields)

`Id`, `BusinessName`, `Name`, `Body`

<!-- END:GENERATED entity=BusinessAnnouncements -->
