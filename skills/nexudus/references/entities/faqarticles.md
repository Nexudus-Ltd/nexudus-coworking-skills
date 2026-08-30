# FaqArticles

<!-- BEGIN:GENERATED entity=FaqArticles -->

A FaqArticle is a frequently asked question and answer published in the members portal, with optional audience restrictions for customers, plans, and teams; location-network visibility is controlled by the viewing location's FAQ data-visibility setting. Active, customer-eligible articles are also semantically matched to answer questions through the AI chat, WhatsApp, and voice channels. The same matcher can automatically answer Help Desk messages and customer comments when OpenAI Help Desk automation is enabled; matched replies include a link to the source FAQ. FAQ content changes refresh the embeddings used for these AI answers.

FaqArticles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus faqarticles list --agent` | List all faqarticles |
| `nexudus faqarticles list --id <id> --agent` | Filter by single ID |
| `nexudus faqarticles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus faqarticles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus faqarticles list --business-id <value> --title <value> --agent` | Filter faqarticles by properties |
| `nexudus faqarticles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus faqarticles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus faqarticles get <id> --agent` | Get single faqarticle |
| `nexudus faqarticles create --business-id <value> --title <value> --display-order <value> --agent` | Create faqarticle |
| `nexudus faqarticles update <id> --name "New Name" --agent` | Update faqarticle |
| `nexudus faqarticles delete <id> --yes --agent` | Delete faqarticle (no prompt) |

#### FaqArticle list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this FAQ article; the viewing location's FAQ data-visibility setting controls where it can be displayed across a location network. |
| `--title` | string | Required question or heading shown for this FAQ article. |
| `--summary-text` | string | Optional short plain-text or HTML summary of the answer, used with the article content in FAQ search indexing. |
| `--full-text` | string | Optional full answer displayed in the members portal; HTML content is supported and is included in FAQ search indexing. |
| `--image-file-name` | string | Current file name of the image (read-only; upload via the corresponding URL field) |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--large-image-file-name` | string | Current file name of the large image (read-only; upload via the corresponding URL field) |
| `--new-large-image-url` | string | URL of a new file to upload as the large image |
| `--clear-large-image-file` | bool | Set to true to remove the current large image file |
| `--active` | bool | Whether the article is active and therefore eligible to appear in the members portal, subject to its audience restrictions. |
| `--group-name` | string | Optional group or category name used to organize FAQ articles; portal lists are ordered by group first. |
| `--display-order` | int | Numeric position used to order articles within a group; create and update handlers normalize stored positions after changes. |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--show-in-home-page` | bool | Whether the article is marked to be shown on the members portal home page. |
| `--only-for-contacts` | bool | Whether the article is restricted to contacts, meaning customers without an active contract; this restriction is cumulative with all other audience restrictions. |
| `--only-for-members` | bool | Whether the article is restricted to members, meaning customers with an active contract; this restriction is cumulative with all other audience restrictions. |
| `--tariff-names` | string | Read-only denormalized names of the selected plans, maintained from Tariffs; use Tariffs to change the restriction. |
| `--team-names` | string | Read-only denormalized names of the selected teams, maintained from Teams; use Teams to change the restriction. |
| `--coworker-full-names` | string | Read-only denormalized names of the selected customers, maintained from Members; use Members to change the restriction. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FaqArticle sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FaqArticle create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this FAQ article; the viewing location's FAQ data-visibility setting controls where it can be displayed across a location network. |
| `--title` | string, required | Required question or heading shown for this FAQ article. |
| `--summary-text` | string | Optional short plain-text or HTML summary of the answer, used with the article content in FAQ search indexing. |
| `--full-text` | string | Optional full answer displayed in the members portal; HTML content is supported and is included in FAQ search indexing. |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--new-large-image-url` | string | URL of a new file to upload as the large image |
| `--clear-large-image-file` | bool | Set to true to remove the current large image file |
| `--active` | bool | Whether the article is active and therefore eligible to appear in the members portal, subject to its audience restrictions. |
| `--group-name` | string | Optional group or category name used to organize FAQ articles; portal lists are ordered by group first. |
| `--display-order` | int, required | Numeric position used to order articles within a group; create and update handlers normalize stored positions after changes. |
| `--show-in-home-page` | bool | Whether the article is marked to be shown on the members portal home page. |
| `--only-for-contacts` | bool | Whether the article is restricted to contacts, meaning customers without an active contract; this restriction is cumulative with all other audience restrictions. |
| `--only-for-members` | bool | Whether the article is restricted to members, meaning customers with an active contract; this restriction is cumulative with all other audience restrictions. |
| `--tariffs` | list, repeat flag | List of plan IDs whose active members may view this article; an empty list does not restrict access, and this restriction is cumulative with the other audience restrictions. |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--members` | list, repeat flag | List of customer IDs who may view this article; an empty list does not restrict access, and this restriction is cumulative with the other audience restrictions. |
| `--added-members` | list, repeat flag |  |
| `--removed-members` | list, repeat flag |  |
| `--teams` | list, repeat flag | List of team IDs whose customers may view this article; an empty list does not restrict access, and this restriction is cumulative with the other audience restrictions. |
| `--added-teams` | list, repeat flag |  |
| `--removed-teams` | list, repeat flag |  |

#### FaqArticle update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this FAQ article; the viewing location's FAQ data-visibility setting controls where it can be displayed across a location network. |
| `--title` | string | Required question or heading shown for this FAQ article. |
| `--summary-text` | string | Optional short plain-text or HTML summary of the answer, used with the article content in FAQ search indexing. |
| `--full-text` | string | Optional full answer displayed in the members portal; HTML content is supported and is included in FAQ search indexing. |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--new-large-image-url` | string | URL of a new file to upload as the large image |
| `--clear-large-image-file` | bool | Set to true to remove the current large image file |
| `--active` | bool | Whether the article is active and therefore eligible to appear in the members portal, subject to its audience restrictions. |
| `--group-name` | string | Optional group or category name used to organize FAQ articles; portal lists are ordered by group first. |
| `--display-order` | int | Numeric position used to order articles within a group; create and update handlers normalize stored positions after changes. |
| `--show-in-home-page` | bool | Whether the article is marked to be shown on the members portal home page. |
| `--only-for-contacts` | bool | Whether the article is restricted to contacts, meaning customers without an active contract; this restriction is cumulative with all other audience restrictions. |
| `--only-for-members` | bool | Whether the article is restricted to members, meaning customers with an active contract; this restriction is cumulative with all other audience restrictions. |
| `--tariffs` | list, repeat flag | List of plan IDs whose active members may view this article; an empty list does not restrict access, and this restriction is cumulative with the other audience restrictions. |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--members` | list, repeat flag | List of customer IDs who may view this article; an empty list does not restrict access, and this restriction is cumulative with the other audience restrictions. |
| `--added-members` | list, repeat flag |  |
| `--removed-members` | list, repeat flag |  |
| `--teams` | list, repeat flag | List of team IDs whose customers may view this article; an empty list does not restrict access, and this restriction is cumulative with the other audience restrictions. |
| `--added-teams` | list, repeat flag |  |
| `--removed-teams` | list, repeat flag |  |

#### FaqArticle PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-names` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus faqarticles update <id> --coworker-full-names "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Members`, `AddedMembers`, `RemovedMembers`, `Teams`, `AddedTeams`, `RemovedTeams`

<!-- END:GENERATED entity=FaqArticles -->
