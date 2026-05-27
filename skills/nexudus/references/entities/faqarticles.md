# FaqArticles

<!-- BEGIN:GENERATED entity=FaqArticles -->

A **FaqArticle** represents a frequently asked question and its answer, displayed on the members portal to help customers find information without contacting support.

FaqArticles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus faqarticles list --agent` | List all faqarticles |
| `nexudus faqarticles list --id <id> --agent` | Filter by single ID |
| `nexudus faqarticles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus faqarticles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus faqarticles list --business-id <value> --title <value> --agent` | Filter faqarticles by properties |
| `nexudus faqarticles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus faqarticles get <id> --agent` | Get single faqarticle |
| `nexudus faqarticles create --business-id <value> --title <value> --display-order <value> --agent` | Create faqarticle |
| `nexudus faqarticles update <id> --name "New Name" --agent` | Update faqarticle |
| `nexudus faqarticles delete <id> --yes --agent` | Delete faqarticle (no prompt) |

#### FaqArticle list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--title` | string | The title value for this faq article |
| `--summary-text` | string | The summary text value for this faq article |
| `--full-text` | string | The full text value for this faq article |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--new-large-image-url` | string | URL of a new file to upload as the large image |
| `--clear-large-image-file` | bool | Set to true to remove the current large image file |
| `--active` | bool | Whether this faq article is currently active |
| `--group-name` | string | The group name value for this faq article |
| `--display-order` | int | The display order value for this faq article |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--show-in-home-page` | bool | Whether show in home page is enabled |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FaqArticle create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--title` | string, required | The title value for this faq article |
| `--summary-text` | string | The summary text value for this faq article |
| `--full-text` | string | The full text value for this faq article |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--new-large-image-url` | string | URL of a new file to upload as the large image |
| `--clear-large-image-file` | bool | Set to true to remove the current large image file |
| `--active` | bool | Whether this faq article is currently active |
| `--group-name` | string | The group name value for this faq article |
| `--display-order` | int, required | The display order value for this faq article |
| `--show-in-home-page` | bool | Whether show in home page is enabled |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |

#### FaqArticle update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--title` | string | The title value for this faq article |
| `--summary-text` | string | The summary text value for this faq article |
| `--full-text` | string | The full text value for this faq article |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--new-large-image-url` | string | URL of a new file to upload as the large image |
| `--clear-large-image-file` | bool | Set to true to remove the current large image file |
| `--active` | bool | Whether this faq article is currently active |
| `--group-name` | string | The group name value for this faq article |
| `--display-order` | int | The display order value for this faq article |
| `--show-in-home-page` | bool | Whether show in home page is enabled |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |

<!-- END:GENERATED entity=FaqArticles -->
