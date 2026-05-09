# BlogPosts

<!-- BEGIN:GENERATED entity=BlogPosts -->

A **BlogPost** represents an article published on the Members Portal. Articles can be used to share news, updates, or useful content with customers.

Articles support scheduled publishing via `PublishDate` and automatic unpublishing via `UnpublishDate`. Setting a `PublishDate` in the past publishes the article immediately; setting a future date schedules it. Leaving `UnpublishDate` blank keeps the article published until it is manually unpublished or deleted.

Each article has a `SummaryText` (short overview displayed at the top) and a `FullText` (the main body content). Articles can be organised into categories using the `BlogCategory` entity and can optionally allow customer comments.

Visibility can be controlled with `OnlyForMembers` (customers with an active contract) and `OnlyForContacts` (customers without an active contract). Articles can also be featured on the Members Portal home page before login (`ShowInHomeBanner`) or after login (`ShowInHomePage`).

BlogPosts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus blogposts list --agent` | List all blogposts |
| `nexudus blogposts list --id <id> --agent` | Filter by single ID |
| `nexudus blogposts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus blogposts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus blogposts list --title <value> --agent` | Filter blogposts by properties |
| `nexudus blogposts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus blogposts get <id> --agent` | Get single blogpost |
| `nexudus blogposts create --business-id <value> --title <value> --comments-count <value> --agent` | Create blogpost |
| `nexudus blogposts update <id> --name "New Name" --agent` | Update blogpost |
| `nexudus blogposts delete <id> --yes --agent` | Delete blogpost (no prompt) |

#### BlogPost list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--language-id` | long |  |
| `--posted-by-id` | long |  |
| `--title` | string | Article title |
| `--summary` | string | Short overview displayed at the top of the article |
| `--body` | string | Main body content of the article |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--new-large-image-url` | string |  |
| `--clear-large-image-file` | bool |  |
| `--publish-date` | DateTime | Date and time when the article is published. Past dates publish immediately; future dates schedule publication |
| `--from-publish-date` | range | |
| `--to-publish-date` | range | |
| `--show-in-home-banner` | bool | Feature this article on the Members Portal home page before users log in |
| `--show-in-home-page` | bool | Feature this article on the Members Portal home page after users log in |
| `--unpublish-date` | DateTime | Date and time when the article is automatically unpublished. Leave blank to keep published indefinitely |
| `--from-unpublish-date` | range | |
| `--to-unpublish-date` | range | |
| `--allow-comments` | bool | Whether customers can post comments on this article |
| `--comments-count` | int | Number of comments on this article |
| `--from-comments-count` | range | |
| `--to-comments-count` | range | |
| `--only-for-contacts` | bool | Restrict visibility to contacts (customers without an active contract) |
| `--only-for-members` | bool | Restrict visibility to members (customers with an active contract) |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BlogPost create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--language-id` | long |  |
| `--posted-by-id` | long |  |
| `--title` | string, required | Article title |
| `--summary` | string | Short overview displayed at the top of the article |
| `--body` | string | Main body content of the article |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--new-large-image-url` | string |  |
| `--clear-large-image-file` | bool |  |
| `--publish-date` | DateTime | Date and time when the article is published. Past dates publish immediately; future dates schedule publication |
| `--show-in-home-banner` | bool | Feature this article on the Members Portal home page before users log in |
| `--show-in-home-page` | bool | Feature this article on the Members Portal home page after users log in |
| `--unpublish-date` | DateTime | Date and time when the article is automatically unpublished. Leave blank to keep published indefinitely |
| `--allow-comments` | bool | Whether customers can post comments on this article |
| `--blog-categories` | list, repeat flag |  |
| `--added-blog-categories` | list, repeat flag |  |
| `--removed-blog-categories` | list, repeat flag |  |
| `--comments-count` | int, required | Number of comments on this article |
| `--only-for-contacts` | bool | Restrict visibility to contacts (customers without an active contract) |
| `--only-for-members` | bool | Restrict visibility to members (customers with an active contract) |

#### BlogPost update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--language-id` | long |  |
| `--posted-by-id` | long |  |
| `--title` | string | Article title |
| `--summary` | string | Short overview displayed at the top of the article |
| `--body` | string | Main body content of the article |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--new-large-image-url` | string |  |
| `--clear-large-image-file` | bool |  |
| `--publish-date` | DateTime | Date and time when the article is published. Past dates publish immediately; future dates schedule publication |
| `--show-in-home-banner` | bool | Feature this article on the Members Portal home page before users log in |
| `--show-in-home-page` | bool | Feature this article on the Members Portal home page after users log in |
| `--unpublish-date` | DateTime | Date and time when the article is automatically unpublished. Leave blank to keep published indefinitely |
| `--allow-comments` | bool | Whether customers can post comments on this article |
| `--blog-categories` | list, repeat flag |  |
| `--added-blog-categories` | list, repeat flag |  |
| `--removed-blog-categories` | list, repeat flag |  |
| `--comments-count` | int | Number of comments on this article |
| `--only-for-contacts` | bool | Restrict visibility to contacts (customers without an active contract) |
| `--only-for-members` | bool | Restrict visibility to members (customers with an active contract) |

### BlogPost (key fields)

`Id`, `Title`

**List properties (only returned by `get`, not by `list`):** `BlogCategories`, `AddedBlogCategories`, `RemovedBlogCategories`

<!-- END:GENERATED entity=BlogPosts -->
