# BlogPostComments

<!-- BEGIN:GENERATED entity=BlogPostComments -->

A **BlogPostComment** represents a comment left on a `BlogPost`. Each comment belongs to a specific blog post via `BlogPostId`.

Comments have a `Title` and `Text` body, and can optionally include a `Rating`. The `Published` flag controls whether the comment is visible to readers — use this for moderation. The `PostedById` links the comment to the `Coworker` who authored it.

BlogPostComments support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus blogpostcomments list --agent` | List all blogpostcomments |
| `nexudus blogpostcomments list --id <id> --agent` | Filter by single ID |
| `nexudus blogpostcomments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus blogpostcomments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus blogpostcomments list --title <value> --agent` | Filter blogpostcomments by properties |
| `nexudus blogpostcomments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus blogpostcomments list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus blogpostcomments get <id> --agent` | Get single blogpostcomment |
| `nexudus blogpostcomments create --business-id <value> --blog-post-id <value> --title <value> --text <value> --agent` | Create blogpostcomment |
| `nexudus blogpostcomments update <id> --name "New Name" --agent` | Update blogpostcomment |
| `nexudus blogpostcomments delete <id> --yes --agent` | Delete blogpostcomment (no prompt) |

#### BlogPostComment list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--blog-post-id` | long | ID of the blog post linked to this record |
| `--posted-by-id` | long | ID of the posted by linked to this record |
| `--title` | string | Comment title |
| `--text` | string | Comment body text |
| `--published` | bool | Whether the comment is published and visible to readers |
| `--rating` | int | Optional rating given by the commenter |
| `--from-rating` | range | |
| `--to-rating` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BlogPostComment sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### BlogPostComment create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--blog-post-id` | long, required | ID of the blog post linked to this record |
| `--posted-by-id` | long | ID of the posted by linked to this record |
| `--title` | string, required | Comment title |
| `--text` | string, required | Comment body text |
| `--published` | bool | Whether the comment is published and visible to readers |
| `--rating` | int | Optional rating given by the commenter |

#### BlogPostComment update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--blog-post-id` | long | ID of the blog post linked to this record |
| `--posted-by-id` | long | ID of the posted by linked to this record |
| `--title` | string | Comment title |
| `--text` | string | Comment body text |
| `--published` | bool | Whether the comment is published and visible to readers |
| `--rating` | int | Optional rating given by the commenter |

#### BlogPostComment PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--posted-by-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus blogpostcomments update <id> --posted-by-name "«PII:NAME:a3f2b1c9»" --agent`

### BlogPostComment (key fields)

`Id`, `PostedByFullName`, `Title`

<!-- END:GENERATED entity=BlogPostComments -->
