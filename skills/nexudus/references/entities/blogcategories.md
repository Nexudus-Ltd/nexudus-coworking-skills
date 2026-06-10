# BlogCategories

<!-- BEGIN:GENERATED entity=BlogCategories -->

A **BlogCategory** groups blog posts into named categories within a location. Each category belongs to a single `Business` and has a `Title` used for display and filtering.

Categories can optionally be associated with a `Language` to support multilingual blogs. Use the `BlogPosts`, `AddedBlogPosts`, and `RemovedBlogPosts` collections to manage which blog posts belong to the category.

BlogCategories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus blogcategories list --agent` | List all blogcategories |
| `nexudus blogcategories list --id <id> --agent` | Filter by single ID |
| `nexudus blogcategories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus blogcategories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus blogcategories list --title <value> --agent` | Filter blogcategories by properties |
| `nexudus blogcategories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus blogcategories list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus blogcategories get <id> --agent` | Get single blogcategory |
| `nexudus blogcategories create --business-id <value> --title <value> --agent` | Create blogcategory |
| `nexudus blogcategories update <id> --name "New Name" --agent` | Update blogcategory |
| `nexudus blogcategories delete <id> --yes --agent` | Delete blogcategory (no prompt) |

#### BlogCategory list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--language-id` | long | ID of the language linked to this record |
| `--title` | string | Category title |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BlogCategory sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Title` ascending. If no `--order-by` is specified, the API returns results ordered by `Title` (ascending).

#### BlogCategory create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--language-id` | long | ID of the language linked to this record |
| `--title` | string, required | Category title |
| `--blog-posts` | list, repeat flag | List of blog posts linked to this record |
| `--added-blog-posts` | list, repeat flag | The added blog posts value for this blog category |
| `--removed-blog-posts` | list, repeat flag | The removed blog posts value for this blog category |

#### BlogCategory update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--language-id` | long | ID of the language linked to this record |
| `--title` | string | Category title |
| `--blog-posts` | list, repeat flag | List of blog posts linked to this record |
| `--added-blog-posts` | list, repeat flag | The added blog posts value for this blog category |
| `--removed-blog-posts` | list, repeat flag | The removed blog posts value for this blog category |

### BlogCategory (key fields)

`Id`, `Title`

**List properties (only returned by `get`, not by `list`):** `BlogPosts`, `AddedBlogPosts`, `RemovedBlogPosts`

<!-- END:GENERATED entity=BlogCategories -->
