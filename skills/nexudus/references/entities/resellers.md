# Resellers

<!-- BEGIN:GENERATED entity=Resellers -->

A **Reseller** represents a partner organisation that resells Nexudus services or manages multiple business locations on behalf of their clients.

Resellers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resellers list --agent` | List all resellers |
| `nexudus resellers list --id <id> --agent` | Filter by single ID |
| `nexudus resellers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resellers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resellers list --name <value> --profile-is-public <value> --agent` | Filter resellers by properties |
| `nexudus resellers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resellers list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus resellers get <id> --agent` | Get single reseller |
| `nexudus resellers create --name <value> --agent` | Create reseller |
| `nexudus resellers update <id> --name "New Name" --agent` | Update reseller |
| `nexudus resellers delete <id> --yes --agent` | Delete reseller (no prompt) |

#### Reseller list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | The name value for this reseller |
| `--profile-is-public` | bool | Whether profile is public is enabled |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--new-logo-url` | string | URL of a new file to upload as the logo |
| `--clear-logo-file` | bool | Set to true to remove the current logo file |
| `--area` | string | The area value for this reseller |
| `--operates-in` | string | The operates in value for this reseller |
| `--web-address` | string | The web address value for this reseller |
| `--email` | string | The email value for this reseller |
| `--profile-summary` | string | The profile summary value for this reseller |
| `--phone-number` | string | The phone number value for this reseller |
| `--testimonial1` | string | The testimonial1 value for this reseller |
| `--testimonial1-author` | string | The testimonial1 author value for this reseller |
| `--testimonial2` | string | The testimonial2 value for this reseller |
| `--testimonial2-author` | string | The testimonial2 author value for this reseller |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Reseller sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Reseller create options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string, required | The name value for this reseller |
| `--profile-is-public` | bool | Whether profile is public is enabled |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--new-logo-url` | string | URL of a new file to upload as the logo |
| `--clear-logo-file` | bool | Set to true to remove the current logo file |
| `--area` | string | The area value for this reseller |
| `--operates-in` | string | The operates in value for this reseller |
| `--web-address` | string | The web address value for this reseller |
| `--email` | string | The email value for this reseller |
| `--profile-summary` | string | The profile summary value for this reseller |
| `--phone-number` | string | The phone number value for this reseller |
| `--testimonial1` | string | The testimonial1 value for this reseller |
| `--testimonial1-author` | string | The testimonial1 author value for this reseller |
| `--testimonial2` | string | The testimonial2 value for this reseller |
| `--testimonial2-author` | string | The testimonial2 author value for this reseller |

#### Reseller update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | The name value for this reseller |
| `--profile-is-public` | bool | Whether profile is public is enabled |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--new-logo-url` | string | URL of a new file to upload as the logo |
| `--clear-logo-file` | bool | Set to true to remove the current logo file |
| `--area` | string | The area value for this reseller |
| `--operates-in` | string | The operates in value for this reseller |
| `--web-address` | string | The web address value for this reseller |
| `--email` | string | The email value for this reseller |
| `--profile-summary` | string | The profile summary value for this reseller |
| `--phone-number` | string | The phone number value for this reseller |
| `--testimonial1` | string | The testimonial1 value for this reseller |
| `--testimonial1-author` | string | The testimonial1 author value for this reseller |
| `--testimonial2` | string | The testimonial2 value for this reseller |
| `--testimonial2-author` | string | The testimonial2 author value for this reseller |

#### Reseller PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--user-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--profile-summary` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus resellers update <id> --user-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=Resellers -->
