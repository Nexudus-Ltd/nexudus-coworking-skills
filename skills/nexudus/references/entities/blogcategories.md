# BlogCategories

<!-- BEGIN:GENERATED entity=BlogCategories -->

A blog category is a named grouping of blog posts for a location, used as a public blog filter and to show related posts.

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
| `--business-id` | long | ID of the location this blog category belongs to. |
| `--language-id` | long | ID of the optional location language this category is limited to; leave unset for a category available in every language. |
| `--title` | string | Required category name shown in blog filters and used to group related blog posts. |
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
| `--business-id` | long, required | ID of the location this blog category belongs to. |
| `--language-id` | long | ID of the optional location language this category is limited to; leave unset for a category available in every language. |
| `--title` | string, required | Required category name shown in blog filters and used to group related blog posts. |
| `--blog-posts` | list, repeat flag | List of IDs of blog posts assigned to this category; when supplied on update, the list replaces the current assignments. |
| `--added-blog-posts` | list, repeat flag | The added blog posts value for this blog category |
| `--removed-blog-posts` | list, repeat flag | The removed blog posts value for this blog category |

#### BlogCategory update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this blog category belongs to. |
| `--language-id` | long | ID of the optional location language this category is limited to; leave unset for a category available in every language. |
| `--title` | string | Required category name shown in blog filters and used to group related blog posts. |
| `--blog-posts` | list, repeat flag | List of IDs of blog posts assigned to this category; when supplied on update, the list replaces the current assignments. |
| `--added-blog-posts` | list, repeat flag | The added blog posts value for this blog category |
| `--removed-blog-posts` | list, repeat flag | The removed blog posts value for this blog category |

### BlogCategory (key fields)

`Id`, `Title`

**List properties (only returned by `get`, not by `list`):** `BlogPosts`, `AddedBlogPosts`, `RemovedBlogPosts`

<!-- END:GENERATED entity=BlogCategories -->
