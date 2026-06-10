# ImageFiles

<!-- BEGIN:GENERATED entity=ImageFiles -->

An **ImageFile** represents an uploaded image stored in the system. Image files can be used for branding, content, floor plans, or other visual elements across the platform.

ImageFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus imagefiles list --agent` | List all imagefiles |
| `nexudus imagefiles list --id <id> --agent` | Filter by single ID |
| `nexudus imagefiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus imagefiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus imagefiles list --business-id <value> --name <value> --agent` | Filter imagefiles by properties |
| `nexudus imagefiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus imagefiles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus imagefiles get <id> --agent` | Get single imagefile |
| `nexudus imagefiles create --business-id <value> --name <value> --agent` | Create imagefile |
| `nexudus imagefiles update <id> --name "New Name" --agent` | Update imagefile |
| `nexudus imagefiles delete <id> --yes --agent` | Delete imagefile (no prompt) |

#### ImageFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this image file |
| `--description` | string | Free-text description of this image file |
| `--use-in-gallery` | bool | Whether use in gallery is enabled |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--file-size-bytes` | int | The file size bytes value for this image file |
| `--from-file-size-bytes` | range | |
| `--to-file-size-bytes` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ImageFile sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ImageFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this image file |
| `--description` | string | Free-text description of this image file |
| `--use-in-gallery` | bool | Whether use in gallery is enabled |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--file-size-bytes` | int | The file size bytes value for this image file |

#### ImageFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this image file |
| `--description` | string | Free-text description of this image file |
| `--use-in-gallery` | bool | Whether use in gallery is enabled |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--file-size-bytes` | int | The file size bytes value for this image file |

<!-- END:GENERATED entity=ImageFiles -->
