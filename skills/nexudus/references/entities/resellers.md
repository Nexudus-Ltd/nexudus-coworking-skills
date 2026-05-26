# Resellers

<!-- BEGIN:GENERATED entity=Resellers -->

Resellers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resellers list --agent` | List all resellers |
| `nexudus resellers list --id <id> --agent` | Filter by single ID |
| `nexudus resellers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resellers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resellers list --name <value> --profile-is-public <value> --agent` | Filter resellers by properties |
| `nexudus resellers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resellers get <id> --agent` | Get single reseller |
| `nexudus resellers create --name <value> --agent` | Create reseller |
| `nexudus resellers update <id> --name "New Name" --agent` | Update reseller |
| `nexudus resellers delete <id> --yes --agent` | Delete reseller (no prompt) |

#### Reseller list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string |  |
| `--profile-is-public` | bool |  |
| `--new-avatar-url` | string |  |
| `--clear-avatar-file` | bool |  |
| `--new-logo-url` | string |  |
| `--clear-logo-file` | bool |  |
| `--area` | string |  |
| `--operates-in` | string |  |
| `--web-address` | string |  |
| `--email` | string |  |
| `--profile-summary` | string |  |
| `--phone-number` | string |  |
| `--testimonial1` | string |  |
| `--testimonial1-author` | string |  |
| `--testimonial2` | string |  |
| `--testimonial2-author` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Reseller create options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string, required |  |
| `--profile-is-public` | bool |  |
| `--new-avatar-url` | string |  |
| `--clear-avatar-file` | bool |  |
| `--new-logo-url` | string |  |
| `--clear-logo-file` | bool |  |
| `--area` | string |  |
| `--operates-in` | string |  |
| `--web-address` | string |  |
| `--email` | string |  |
| `--profile-summary` | string |  |
| `--phone-number` | string |  |
| `--testimonial1` | string |  |
| `--testimonial1-author` | string |  |
| `--testimonial2` | string |  |
| `--testimonial2-author` | string |  |

#### Reseller update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string |  |
| `--profile-is-public` | bool |  |
| `--new-avatar-url` | string |  |
| `--clear-avatar-file` | bool |  |
| `--new-logo-url` | string |  |
| `--clear-logo-file` | bool |  |
| `--area` | string |  |
| `--operates-in` | string |  |
| `--web-address` | string |  |
| `--email` | string |  |
| `--profile-summary` | string |  |
| `--phone-number` | string |  |
| `--testimonial1` | string |  |
| `--testimonial1-author` | string |  |
| `--testimonial2` | string |  |
| `--testimonial2-author` | string |  |

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
