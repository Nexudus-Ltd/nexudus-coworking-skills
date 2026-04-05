# ResellerPayouts

<!-- BEGIN:GENERATED entity=ResellerPayouts -->

ResellerPayouts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resellerpayouts list --agent` | List all resellerpayouts |
| `nexudus resellerpayouts list --id <id> --agent` | Filter by single ID |
| `nexudus resellerpayouts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resellerpayouts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resellerpayouts list --new-reseller-invoice-data-url <value> --clear-reseller-invoice-data-file <value> --agent` | Filter resellerpayouts by properties |
| `nexudus resellerpayouts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resellerpayouts get <id> --agent` | Get single resellerpayout |
| `nexudus resellerpayouts create  --agent` | Create resellerpayout |
| `nexudus resellerpayouts update <id> --name "New Name" --agent` | Update resellerpayout |
| `nexudus resellerpayouts delete <id> --yes --agent` | Delete resellerpayout (no prompt) |

#### ResellerPayout list filter options

`--new-reseller-invoice-data-url`, `--clear-reseller-invoice-data-file`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ResellerPayout create options

`--new-reseller-invoice-data-url`, `--clear-reseller-invoice-data-file`

#### ResellerPayout update options

`--new-reseller-invoice-data-url`, `--clear-reseller-invoice-data-file`

<!-- END:GENERATED entity=ResellerPayouts -->
