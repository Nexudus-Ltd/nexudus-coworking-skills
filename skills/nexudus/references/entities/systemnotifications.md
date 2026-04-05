# SystemNotifications

<!-- BEGIN:GENERATED entity=SystemNotifications -->

SystemNotifications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus systemnotifications list --agent` | List all systemnotifications |
| `nexudus systemnotifications list --id <id> --agent` | Filter by single ID |
| `nexudus systemnotifications list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus systemnotifications list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus systemnotifications list --title <value> --severity <value> --agent` | Filter systemnotifications by properties |
| `nexudus systemnotifications list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus systemnotifications get <id> --agent` | Get single systemnotification |
| `nexudus systemnotifications create --title <value> --start-time <value> --short-description <value> --description <value> --agent` | Create systemnotification |
| `nexudus systemnotifications update <id> --name "New Name" --agent` | Update systemnotification |
| `nexudus systemnotifications delete <id> --yes --agent` | Delete systemnotification (no prompt) |

#### SystemNotification list filter options

`--title`, `--severity`, `--start-time`, `--from-start-time` (range), `--to-start-time` (range), `--publish-on`, `--from-publish-on` (range), `--to-publish-on` (range), `--un-publish-on`, `--from-un-publish-on` (range), `--to-un-publish-on` (range), `--short-description`, `--description`, `--resolution-description`, `--resolved`, `--resolved-on`, `--from-resolved-on` (range), `--to-resolved-on` (range), `--display-to-admins`, `--display-to-setting-integrations`, `--display-to-setting-general`, `--display-to-portal-version`, `--message-type`, `--has-button`, `--button-label`, `--button-url`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### SystemNotification create options

`--title` (required), `--severity`, `--start-time` (required), `--publish-on`, `--un-publish-on`, `--short-description` (required), `--description` (required), `--resolution-description`, `--resolved`, `--resolved-on`, `--display-to-admins`, `--display-to-setting-integrations`, `--display-to-setting-general`, `--display-to-portal-version`, `--message-type`, `--has-button`, `--button-label`, `--button-url`

#### SystemNotification update options

`--title`, `--severity`, `--start-time`, `--publish-on`, `--un-publish-on`, `--short-description`, `--description`, `--resolution-description`, `--resolved`, `--resolved-on`, `--display-to-admins`, `--display-to-setting-integrations`, `--display-to-setting-general`, `--display-to-portal-version`, `--message-type`, `--has-button`, `--button-label`, `--button-url`

<!-- END:GENERATED entity=SystemNotifications -->
