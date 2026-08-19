# MarketPlaceApplications

<!-- BEGIN:GENERATED entity=MarketPlaceApplications -->

A **MarketPlaceApplication** represents an application available in the Nexudus marketplace. Marketplace apps provide integrations with third-party services, automation tools, and additional platform features.

MarketPlaceApplications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus marketplaceapplications list --agent` | List all marketplaceapplications |
| `nexudus marketplaceapplications list --id <id> --agent` | Filter by single ID |
| `nexudus marketplaceapplications list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus marketplaceapplications list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus marketplaceapplications list --developer-id <value> --name <value> --agent` | Filter marketplaceapplications by properties |
| `nexudus marketplaceapplications list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus marketplaceapplications list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus marketplaceapplications get <id> --agent` | Get single marketplaceapplication |
| `nexudus marketplaceapplications create --developer-id <value> --name <value> --support-email <value> --developer-name <value> --short-description <value> --notification-email <value> --notification-url <value> --agent` | Create marketplaceapplication |
| `nexudus marketplaceapplications update <id> --name "New Name" --agent` | Update marketplaceapplication |
| `nexudus marketplaceapplications delete <id> --yes --agent` | Delete marketplaceapplication (no prompt) |

#### MarketPlaceApplication list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--developer-id` | long | ID of the developer linked to this record |
| `--name` | string | The name value for this market place application |
| `--terms-and-conditions` | string | The terms and conditions value for this market place application |
| `--support-email` | string | The support email value for this market place application |
| `--developer-name` | string | The developer name value for this market place application |
| `--published` | bool | Whether published is enabled |
| `--secret-key` | string | The secret key value for this market place application |
| `--short-description` | string | The short description value for this market place application |
| `--description` | string | Free-text description of this market place application |
| `--notification-email` | string | The notification email value for this market place application |
| `--notification-url` | string | The notification url value for this market place application |
| `--logo-file-name` | string | Current file name of the logo (read-only; upload via the corresponding URL field) |
| `--new-logo-url` | string | URL of a new file to upload as the logo |
| `--clear-logo-file` | bool | Set to true to remove the current logo file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### MarketPlaceApplication sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### MarketPlaceApplication create options

| Option | Type | Description |
| --- | --- | --- |
| `--developer-id` | long, required | ID of the developer linked to this record |
| `--name` | string, required | The name value for this market place application |
| `--terms-and-conditions` | string | The terms and conditions value for this market place application |
| `--support-email` | string, required | The support email value for this market place application |
| `--developer-name` | string, required | The developer name value for this market place application |
| `--published` | bool | Whether published is enabled |
| `--secret-key` | string | The secret key value for this market place application |
| `--short-description` | string, required | The short description value for this market place application |
| `--description` | string | Free-text description of this market place application |
| `--notification-email` | string, required | The notification email value for this market place application |
| `--notification-url` | string, required | The notification url value for this market place application |
| `--new-logo-url` | string | URL of a new file to upload as the logo |
| `--clear-logo-file` | bool | Set to true to remove the current logo file |

#### MarketPlaceApplication update options

| Option | Type | Description |
| --- | --- | --- |
| `--developer-id` | long | ID of the developer linked to this record |
| `--name` | string | The name value for this market place application |
| `--terms-and-conditions` | string | The terms and conditions value for this market place application |
| `--support-email` | string | The support email value for this market place application |
| `--developer-name` | string | The developer name value for this market place application |
| `--published` | bool | Whether published is enabled |
| `--secret-key` | string | The secret key value for this market place application |
| `--short-description` | string | The short description value for this market place application |
| `--description` | string | Free-text description of this market place application |
| `--notification-email` | string | The notification email value for this market place application |
| `--notification-url` | string | The notification url value for this market place application |
| `--new-logo-url` | string | URL of a new file to upload as the logo |
| `--clear-logo-file` | bool | Set to true to remove the current logo file |

#### MarketPlaceApplication PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--support-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--notification-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus marketplaceapplications update <id> --support-email "«PII:EMAIL:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=MarketPlaceApplications -->
