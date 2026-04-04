# FaqArticles

<!-- BEGIN:GENERATED entity=FaqArticles -->

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

`--business-id`, `--title`, `--summary-text`, `--full-text`, `--new-image-url`, `--clear-image-file`, `--new-large-image-url`, `--clear-large-image-file`, `--active`, `--group-name`, `--display-order`, `--show-in-home-page`, `--only-for-contacts`, `--only-for-members`

#### FaqArticle create options

`--business-id` (required), `--title` (required), `--summary-text`, `--full-text`, `--new-image-url`, `--clear-image-file`, `--new-large-image-url`, `--clear-large-image-file`, `--active`, `--group-name`, `--display-order` (required), `--show-in-home-page`, `--only-for-contacts`, `--only-for-members`

#### FaqArticle update options

`--business-id`, `--title`, `--summary-text`, `--full-text`, `--new-image-url`, `--clear-image-file`, `--new-large-image-url`, `--clear-large-image-file`, `--active`, `--group-name`, `--display-order`, `--show-in-home-page`, `--only-for-contacts`, `--only-for-members`

<!-- END:GENERATED entity=FaqArticles -->
