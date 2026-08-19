# BlogPosts

<!-- BEGIN:GENERATED entity=BlogPosts -->

A BlogPost is a location-specific article for the Members Portal, with HTML content, optional images and categories, scheduled publication, audience restrictions, home-page placement, and optional customer comments.

BlogPosts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus blogposts list --agent` | List all blogposts |
| `nexudus blogposts list --id <id> --agent` | Filter by single ID |
| `nexudus blogposts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus blogposts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus blogposts list --title <value> --agent` | Filter blogposts by properties |
| `nexudus blogposts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus blogposts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus blogposts get <id> --agent` | Get single blogpost |
| `nexudus blogposts create --business-id <value> --title <value> --agent` | Create blogpost |
| `nexudus blogposts update <id> --name "New Name" --agent` | Update blogpost |
| `nexudus blogposts delete <id> --yes --agent` | Delete blogpost (no prompt) |

#### BlogPost list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this article. |
| `--language-id` | long | ID of the optional location-specific language used for this article. |
| `--posted-by-id` | long | ID of the user attributed as the author; creation assigns the currently authenticated user. |
| `--posted-by-name` | string | Full name of the article author |
| `--title` | string | Required title of the article. |
| `--summary` | string | Optional short overview displayed with the article. |
| `--body` | string | Optional HTML body content of the article. |
| `--image-file-name` | string | Current file name of the image (read-only; upload via the corresponding URL field) |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--large-image-file-name` | string | Current file name of the large image (read-only; upload via the corresponding URL field) |
| `--new-large-image-url` | string | URL of a new file to upload as the large image |
| `--clear-large-image-file` | bool | Set to true to remove the current large image file |
| `--publish-date` | DateTime | UTC date and time when the public article becomes available; it must be set, and a future value schedules publication. |
| `--from-publish-date` | range | |
| `--to-publish-date` | range | |
| `--show-in-home-banner` | bool | Whether to feature the article in the Members Portal home banner before sign-in. |
| `--show-in-home-page` | bool | Whether to feature the article on the Members Portal home page after sign-in. |
| `--unpublish-date` | DateTime | Optional UTC date and time recorded as the article's unpublish date; leave blank when no unpublish date is required. |
| `--from-unpublish-date` | range | |
| `--to-unpublish-date` | range | |
| `--allow-comments` | bool | Whether customers can submit comments on this article. |
| `--comments-count` | int | Read-only total number of comments, calculated from BlogPostComment records. |
| `--from-comments-count` | range | |
| `--to-comments-count` | range | |
| `--only-for-contacts` | bool | Whether the article is restricted to contacts, meaning customers without an active contract. |
| `--only-for-members` | bool | Whether the article is restricted to members, meaning customers with an active contract. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BlogPost sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### BlogPost create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this article. |
| `--language-id` | long | ID of the optional location-specific language used for this article. |
| `--posted-by-id` | long | ID of the user attributed as the author; creation assigns the currently authenticated user. |
| `--title` | string, required | Required title of the article. |
| `--summary` | string | Optional short overview displayed with the article. |
| `--body` | string | Optional HTML body content of the article. |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--new-large-image-url` | string | URL of a new file to upload as the large image |
| `--clear-large-image-file` | bool | Set to true to remove the current large image file |
| `--publish-date` | DateTime | UTC date and time when the public article becomes available; it must be set, and a future value schedules publication. |
| `--show-in-home-banner` | bool | Whether to feature the article in the Members Portal home banner before sign-in. |
| `--show-in-home-page` | bool | Whether to feature the article on the Members Portal home page after sign-in. |
| `--unpublish-date` | DateTime | Optional UTC date and time recorded as the article's unpublish date; leave blank when no unpublish date is required. |
| `--allow-comments` | bool | Whether customers can submit comments on this article. |
| `--blog-categories` | list, repeat flag | List of location-specific blog category IDs assigned to this article; an empty list leaves it uncategorized. |
| `--added-blog-categories` | list, repeat flag | The added blog categories value for this blog post |
| `--removed-blog-categories` | list, repeat flag | The removed blog categories value for this blog post |
| `--only-for-contacts` | bool | Whether the article is restricted to contacts, meaning customers without an active contract. |
| `--only-for-members` | bool | Whether the article is restricted to members, meaning customers with an active contract. |

#### BlogPost update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this article. |
| `--language-id` | long | ID of the optional location-specific language used for this article. |
| `--posted-by-id` | long | ID of the user attributed as the author; creation assigns the currently authenticated user. |
| `--title` | string | Required title of the article. |
| `--summary` | string | Optional short overview displayed with the article. |
| `--body` | string | Optional HTML body content of the article. |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--new-large-image-url` | string | URL of a new file to upload as the large image |
| `--clear-large-image-file` | bool | Set to true to remove the current large image file |
| `--publish-date` | DateTime | UTC date and time when the public article becomes available; it must be set, and a future value schedules publication. |
| `--show-in-home-banner` | bool | Whether to feature the article in the Members Portal home banner before sign-in. |
| `--show-in-home-page` | bool | Whether to feature the article on the Members Portal home page after sign-in. |
| `--unpublish-date` | DateTime | Optional UTC date and time recorded as the article's unpublish date; leave blank when no unpublish date is required. |
| `--allow-comments` | bool | Whether customers can submit comments on this article. |
| `--blog-categories` | list, repeat flag | List of location-specific blog category IDs assigned to this article; an empty list leaves it uncategorized. |
| `--added-blog-categories` | list, repeat flag | The added blog categories value for this blog post |
| `--removed-blog-categories` | list, repeat flag | The removed blog categories value for this blog post |
| `--only-for-contacts` | bool | Whether the article is restricted to contacts, meaning customers without an active contract. |
| `--only-for-members` | bool | Whether the article is restricted to members, meaning customers with an active contract. |

#### BlogPost PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--posted-by-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus blogposts update <id> --posted-by-name "«PII:NAME:a3f2b1c9»" --agent`

### BlogPost (key fields)

`Id`, `Title`

**List properties (only returned by `get`, not by `list`):** `BlogCategories`, `AddedBlogCategories`, `RemovedBlogCategories`

<!-- END:GENERATED entity=BlogPosts -->
