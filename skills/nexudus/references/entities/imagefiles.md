# ImageFiles

<!-- BEGIN:GENERATED entity=ImageFiles -->

ImageFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus imagefiles list --agent` | List all imagefiles |
| `nexudus imagefiles list --id <id> --agent` | Filter by single ID |
| `nexudus imagefiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus imagefiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus imagefiles list --business-id <value> --name <value> --agent` | Filter imagefiles by properties |
| `nexudus imagefiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus imagefiles get <id> --agent` | Get single imagefile |
| `nexudus imagefiles create --business-id <value> --name <value> --agent` | Create imagefile |
| `nexudus imagefiles update <id> --name "New Name" --agent` | Update imagefile |
| `nexudus imagefiles delete <id> --yes --agent` | Delete imagefile (no prompt) |

#### ImageFile list filter options

`--business-id` (long), `--name`, `--description`, `--use-in-gallery` (bool), `--new-image-url`, `--clear-image-file` (bool), `--file-size-bytes` (int), `--from-file-size-bytes` (range), `--to-file-size-bytes` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ImageFile create options

`--business-id` (long, required), `--name` (required), `--description`, `--use-in-gallery` (bool), `--new-image-url`, `--clear-image-file` (bool), `--file-size-bytes` (int)

#### ImageFile update options

`--business-id` (long), `--name`, `--description`, `--use-in-gallery` (bool), `--new-image-url`, `--clear-image-file` (bool), `--file-size-bytes` (int)

<!-- END:GENERATED entity=ImageFiles -->
