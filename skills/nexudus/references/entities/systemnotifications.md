# SystemNotifications

<!-- BEGIN:GENERATED entity=SystemNotifications -->

A **SystemNotification** represents a platform-level notification displayed to administrators, such as billing alerts, integration issues, or system announcements. Notifications have a severity level and message type.

SystemNotifications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus systemnotifications list --agent` | List all systemnotifications |
| `nexudus systemnotifications list --id <id> --agent` | Filter by single ID |
| `nexudus systemnotifications list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus systemnotifications list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus systemnotifications list --title <value> --severity <value> --agent` | Filter systemnotifications by properties |
| `nexudus systemnotifications list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus systemnotifications list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus systemnotifications get <id> --agent` | Get single systemnotification |
| `nexudus systemnotifications create --title <value> --severity <value> --start-time <value> --short-description <value> --description <value> --message-type <value> --agent` | Create systemnotification |
| `nexudus systemnotifications update <id> --name "New Name" --agent` | Update systemnotification |
| `nexudus systemnotifications delete <id> --yes --agent` | Delete systemnotification (no prompt) |

#### SystemNotification list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--title` | string | The title value for this system notification |
| `--severity` | enum | The severity value for this system notification |
| `--start-time` | DateTime | Date/time value for start time |
| `--from-start-time` | range | |
| `--to-start-time` | range | |
| `--publish-on` | DateTime | Date/time value for publish on |
| `--from-publish-on` | range | |
| `--to-publish-on` | range | |
| `--un-publish-on` | DateTime | Date/time value for un publish on |
| `--from-un-publish-on` | range | |
| `--to-un-publish-on` | range | |
| `--short-description` | string | The short description value for this system notification |
| `--description` | string | Free-text description of this system notification |
| `--resolution-description` | string | The resolution description value for this system notification |
| `--resolved` | bool | Whether resolved is enabled |
| `--resolved-on` | DateTime | Date/time value for resolved on |
| `--from-resolved-on` | range | |
| `--to-resolved-on` | range | |
| `--display-to-admins` | bool | Whether display to admins is enabled |
| `--display-to-setting-integrations` | string | The display to setting integrations value for this system notification |
| `--display-to-setting-general` | string | The display to setting general value for this system notification |
| `--display-to-portal-version` | string | The display to portal version value for this system notification |
| `--message-type` | enum | The message type value for this system notification |
| `--has-button` | bool | Whether has button is enabled |
| `--button-label` | string | The button label value for this system notification |
| `--button-url` | string | The button url value for this system notification |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### SystemNotification sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### SystemNotification create options

| Option | Type | Description |
| --- | --- | --- |
| `--title` | string, required | The title value for this system notification |
| `--severity` | enum, required | The severity value for this system notification |
| `--start-time` | DateTime, required | Date/time value for start time |
| `--publish-on` | DateTime | Date/time value for publish on |
| `--un-publish-on` | DateTime | Date/time value for un publish on |
| `--short-description` | string, required | The short description value for this system notification |
| `--description` | string, required | Free-text description of this system notification |
| `--resolution-description` | string | The resolution description value for this system notification |
| `--resolved` | bool | Whether resolved is enabled |
| `--resolved-on` | DateTime | Date/time value for resolved on |
| `--display-to-admins` | bool | Whether display to admins is enabled |
| `--display-to-setting-integrations` | string | The display to setting integrations value for this system notification |
| `--display-to-setting-general` | string | The display to setting general value for this system notification |
| `--display-to-portal-version` | string | The display to portal version value for this system notification |
| `--message-type` | enum, required | The message type value for this system notification |
| `--has-button` | bool | Whether has button is enabled |
| `--button-label` | string | The button label value for this system notification |
| `--button-url` | string | The button url value for this system notification |

#### SystemNotification update options

| Option | Type | Description |
| --- | --- | --- |
| `--title` | string | The title value for this system notification |
| `--severity` | enum | The severity value for this system notification |
| `--start-time` | DateTime | Date/time value for start time |
| `--publish-on` | DateTime | Date/time value for publish on |
| `--un-publish-on` | DateTime | Date/time value for un publish on |
| `--short-description` | string | The short description value for this system notification |
| `--description` | string | Free-text description of this system notification |
| `--resolution-description` | string | The resolution description value for this system notification |
| `--resolved` | bool | Whether resolved is enabled |
| `--resolved-on` | DateTime | Date/time value for resolved on |
| `--display-to-admins` | bool | Whether display to admins is enabled |
| `--display-to-setting-integrations` | string | The display to setting integrations value for this system notification |
| `--display-to-setting-general` | string | The display to setting general value for this system notification |
| `--display-to-portal-version` | string | The display to portal version value for this system notification |
| `--message-type` | enum | The message type value for this system notification |
| `--has-button` | bool | Whether has button is enabled |
| `--button-label` | string | The button label value for this system notification |
| `--button-url` | string | The button url value for this system notification |

#### SystemNotification enum values

| Option | Valid values |
| ------ | ------------ |
| `--severity` | `1` Low, `2` Medium, `3` High |
| `--message-type` | `1` Issue, `2` Announcement |

<!-- END:GENERATED entity=SystemNotifications -->
