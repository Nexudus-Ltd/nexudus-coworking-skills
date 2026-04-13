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
| `nexudus blogpostcomments get <id> --agent` | Get single blogpostcomment |
| `nexudus blogpostcomments create --business-id <value> --blog-post-id <value> --title <value> --text <value> --agent` | Create blogpostcomment |
| `nexudus blogpostcomments update <id> --name "New Name" --agent` | Update blogpostcomment |
| `nexudus blogpostcomments delete <id> --yes --agent` | Delete blogpostcomment (no prompt) |

#### BlogPostComment list filter options

`--business-id` (long), `--blog-post-id` (long), `--posted-by-id` (long), `--title`, `--text`, `--published` (bool), `--rating` (int), `--from-rating` (range), `--to-rating` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BlogPostComment create options

`--business-id` (long, required), `--blog-post-id` (long, required), `--posted-by-id` (long), `--title` (required), `--text` (required), `--published` (bool), `--rating` (int)

#### BlogPostComment update options

`--business-id` (long), `--blog-post-id` (long), `--posted-by-id` (long), `--title`, `--text`, `--published` (bool), `--rating` (int)

### BlogPostComment (key fields)

`Id`, `PostedByFullName`, `Title`

<!-- END:GENERATED entity=BlogPostComments -->
