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

`--name`, `--profile-is-public`, `--new-avatar-url`, `--clear-avatar-file`, `--new-logo-url`, `--clear-logo-file`, `--area`, `--operates-in`, `--web-address`, `--email`, `--profile-summary`, `--phone-number`, `--testimonial1`, `--testimonial1-author`, `--testimonial2`, `--testimonial2-author`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Reseller create options

`--name` (required), `--profile-is-public`, `--new-avatar-url`, `--clear-avatar-file`, `--new-logo-url`, `--clear-logo-file`, `--area`, `--operates-in`, `--web-address`, `--email`, `--profile-summary`, `--phone-number`, `--testimonial1`, `--testimonial1-author`, `--testimonial2`, `--testimonial2-author`

#### Reseller update options

`--name`, `--profile-is-public`, `--new-avatar-url`, `--clear-avatar-file`, `--new-logo-url`, `--clear-logo-file`, `--area`, `--operates-in`, `--web-address`, `--email`, `--profile-summary`, `--phone-number`, `--testimonial1`, `--testimonial1-author`, `--testimonial2`, `--testimonial2-author`

<!-- END:GENERATED entity=Resellers -->
