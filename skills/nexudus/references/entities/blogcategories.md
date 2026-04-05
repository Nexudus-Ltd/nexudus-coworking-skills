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
| `nexudus blogcategories get <id> --agent` | Get single blogcategory |
| `nexudus blogcategories create --business-id <value> --title <value> --agent` | Create blogcategory |
| `nexudus blogcategories update <id> --name "New Name" --agent` | Update blogcategory |
| `nexudus blogcategories delete <id> --yes --agent` | Delete blogcategory (no prompt) |

#### BlogCategory list filter options

`--business-id`, `--language-id`, `--title`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BlogCategory create options

`--business-id` (required), `--language-id`, `--title` (required), `--blog-posts` (list, repeat flag), `--added-blog-posts` (list, repeat flag), `--removed-blog-posts` (list, repeat flag)

#### BlogCategory update options

`--business-id`, `--language-id`, `--title`, `--blog-posts` (list, repeat flag), `--added-blog-posts` (list, repeat flag), `--removed-blog-posts` (list, repeat flag)

### BlogCategory (key fields)

`Id`, `Title`

**List properties (only returned by `get`, not by `list`):** `BlogPosts`, `AddedBlogPosts`, `RemovedBlogPosts`

<!-- END:GENERATED entity=BlogCategories -->
