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
| `nexudus systemnotifications create --title <value> --severity <value> --start-time <value> --short-description <value> --description <value> --message-type <value> --agent` | Create systemnotification |
| `nexudus systemnotifications update <id> --name "New Name" --agent` | Update systemnotification |
| `nexudus systemnotifications delete <id> --yes --agent` | Delete systemnotification (no prompt) |

#### SystemNotification list filter options

`--title`, `--severity` (enum), `--start-time` (DateTime), `--from-start-time` (range), `--to-start-time` (range), `--publish-on` (DateTime), `--from-publish-on` (range), `--to-publish-on` (range), `--un-publish-on` (DateTime), `--from-un-publish-on` (range), `--to-un-publish-on` (range), `--short-description`, `--description`, `--resolution-description`, `--resolved` (bool), `--resolved-on` (DateTime), `--from-resolved-on` (range), `--to-resolved-on` (range), `--display-to-admins` (bool), `--display-to-setting-integrations`, `--display-to-setting-general`, `--display-to-portal-version`, `--message-type` (enum), `--has-button` (bool), `--button-label`, `--button-url`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### SystemNotification create options

`--title` (required), `--severity` (enum, required), `--start-time` (DateTime, required), `--publish-on` (DateTime), `--un-publish-on` (DateTime), `--short-description` (required), `--description` (required), `--resolution-description`, `--resolved` (bool), `--resolved-on` (DateTime), `--display-to-admins` (bool), `--display-to-setting-integrations`, `--display-to-setting-general`, `--display-to-portal-version`, `--message-type` (enum, required), `--has-button` (bool), `--button-label`, `--button-url`

#### SystemNotification update options

`--title`, `--severity` (enum), `--start-time` (DateTime), `--publish-on` (DateTime), `--un-publish-on` (DateTime), `--short-description`, `--description`, `--resolution-description`, `--resolved` (bool), `--resolved-on` (DateTime), `--display-to-admins` (bool), `--display-to-setting-integrations`, `--display-to-setting-general`, `--display-to-portal-version`, `--message-type` (enum), `--has-button` (bool), `--button-label`, `--button-url`

<!-- END:GENERATED entity=SystemNotifications -->
