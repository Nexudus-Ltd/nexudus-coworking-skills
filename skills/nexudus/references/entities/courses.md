# Courses

<!-- BEGIN:GENERATED entity=Courses -->

A course (Course) is a self-paced learning program a location publishes on the Members Portal, made of lessons that can be grouped into sections. Visibility decides who can find and join it, an optional plan (TariffId) charges customers who join, and each customer's enrolment is a course member.

Courses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus courses list --agent` | List all courses |
| `nexudus courses list --id <id> --agent` | Filter by single ID |
| `nexudus courses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus courses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus courses list --business-id <value> --business-name <value> --agent` | Filter courses by properties |
| `nexudus courses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus courses list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus courses get <id> --agent` | Get single course |
| `nexudus courses create --business-id <value> --host-id <value> --title <value> --display-order <value> --visibility <value> --agent` | Create course |
| `nexudus courses update <id> --name "New Name" --agent` | Update course |
| `nexudus courses delete <id> --yes --agent` | Delete course (no prompt) |

#### Course list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that publishes the course; a course on a network location is offered at every location in that network |
| `--business-name` | string | Display value for Business.Name. |
| `--business-address` | string | Display value for Business.Address. |
| `--business-town-city` | string | Display value for Business.TownCity. |
| `--business-postal-code` | string | Display value for Business.PostalCode. |
| `--host-id` | long | Required ID of the customer shown as the course host on the Members Portal course page |
| `--host-full-name` | string | Display value for Host.FullName. |
| `--host-company-name` | string | Display value for Host.CompanyName. |
| `--host-team-names` | string | Display value for Host.TeamNames. |
| `--title` | string | Required course title shown on course cards and the course page of the Members Portal |
| `--summary-text` | string | Plain-text summary shown under the course title on the Members Portal and matched by its course search; keep it under 400 characters, the admin panel's limit |
| `--full-description` | string | Full course description in Markdown, shown as the course description on the course page to every visitor, whether or not they have joined |
| `--show-overview` | bool | Whether customers who have not joined the course can read OverviewText; members of the course always see it |
| `--has-community-group` | bool | Whether the course has its own discussion board group on the Members Portal; turning it on creates the group and turning it off deletes it |
| `--overview-text` | string | Course overview in HTML, shown on the course page below the description; hidden from customers who have not joined unless ShowOverview is true |
| `--image-file-name` | string | Stored filename of the course thumbnail image (read-only; use --new-image-url to set) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--large-image-file-name` | string | Stored filename of the course banner/large image (read-only; use --new-large-image-url to set) |
| `--new-large-image-url` | string | URL of a new banner/large image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-large-image-file` | bool | Set to true to remove the existing banner/large image |
| `--active` | bool | Whether the course is published; an unpublished course is hidden from the Members Portal and its course page cannot be opened, even by customers who joined it |
| `--group-name` | string | Optional course category shown as the course's tag and offered as a category filter on the Members Portal; reuse an existing category's exact spelling so courses group together |
| `--display-order` | int | Administrative sort position among the location's courses; on create it is an insert index (0 puts the course first, a large number puts it last), and the system renumbers every course in steps of 100 after each save. The Members Portal lists courses newest first, not by this value |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--show-in-home-page` | bool | Whether the course is featured on the Members Portal home page that customers see after signing in |
| `--visibility` | enum | Who can find and join the course: Public (1, listed, any customer can join), Hidden (2, not listed, anyone with the link can view and join), Private (3, not listed; only customers an administrator adds as course members can open it), or Paid (4, listed and joinable like Public). Charging is driven by TariffId, not by this value; defaults to Public |
| `--tariff-id` | long | Optional ID of the plan charged for the course: every new course member, whether they join on the Members Portal or an administrator adds them, gets a contract for this plan, and when the plan price is above zero their access stays pending until that invoice is paid. Applies whatever the Visibility; leave empty for a free course |
| `--tariff-name` | string | Display value for Tariff.Name. |
| `--tariff-invoice-every` | int | Display value for Tariff.InvoiceEvery. |
| `--from-tariff-invoice-every` | range | |
| `--to-tariff-invoice-every` | range | |
| `--tariff-invoice-every-weeks` | int | Display value for Tariff.InvoiceEveryWeeks. |
| `--from-tariff-invoice-every-weeks` | range | |
| `--to-tariff-invoice-every-weeks` | range | |
| `--tariff-price` | decimal | Display value for Tariff.Price. |
| `--from-tariff-price` | range | |
| `--to-tariff-price` | range | |
| `--tariff-currency-code` | string | Display value for Tariff.Currency.Code. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Course sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Course create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that publishes the course; a course on a network location is offered at every location in that network |
| `--host-id` | long, required | Required ID of the customer shown as the course host on the Members Portal course page |
| `--title` | string, required | Required course title shown on course cards and the course page of the Members Portal |
| `--summary-text` | string | Plain-text summary shown under the course title on the Members Portal and matched by its course search; keep it under 400 characters, the admin panel's limit |
| `--full-description` | string | Full course description in Markdown, shown as the course description on the course page to every visitor, whether or not they have joined |
| `--show-overview` | bool | Whether customers who have not joined the course can read OverviewText; members of the course always see it |
| `--has-community-group` | bool | Whether the course has its own discussion board group on the Members Portal; turning it on creates the group and turning it off deletes it |
| `--overview-text` | string | Course overview in HTML, shown on the course page below the description; hidden from customers who have not joined unless ShowOverview is true |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--new-large-image-url` | string | URL of a new banner/large image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-large-image-file` | bool | Set to true to remove the existing banner/large image |
| `--active` | bool | Whether the course is published; an unpublished course is hidden from the Members Portal and its course page cannot be opened, even by customers who joined it |
| `--group-name` | string | Optional course category shown as the course's tag and offered as a category filter on the Members Portal; reuse an existing category's exact spelling so courses group together |
| `--display-order` | int, required | Administrative sort position among the location's courses; on create it is an insert index (0 puts the course first, a large number puts it last), and the system renumbers every course in steps of 100 after each save. The Members Portal lists courses newest first, not by this value |
| `--show-in-home-page` | bool | Whether the course is featured on the Members Portal home page that customers see after signing in |
| `--visibility` | enum, required | Who can find and join the course: Public (1, listed, any customer can join), Hidden (2, not listed, anyone with the link can view and join), Private (3, not listed; only customers an administrator adds as course members can open it), or Paid (4, listed and joinable like Public). Charging is driven by TariffId, not by this value; defaults to Public |
| `--tariff-id` | long | Optional ID of the plan charged for the course: every new course member, whether they join on the Members Portal or an administrator adds them, gets a contract for this plan, and when the plan price is above zero their access stays pending until that invoice is paid. Applies whatever the Visibility; leave empty for a free course |

#### Course update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that publishes the course; a course on a network location is offered at every location in that network |
| `--host-id` | long | Required ID of the customer shown as the course host on the Members Portal course page |
| `--title` | string | Required course title shown on course cards and the course page of the Members Portal |
| `--summary-text` | string | Plain-text summary shown under the course title on the Members Portal and matched by its course search; keep it under 400 characters, the admin panel's limit |
| `--full-description` | string | Full course description in Markdown, shown as the course description on the course page to every visitor, whether or not they have joined |
| `--show-overview` | bool | Whether customers who have not joined the course can read OverviewText; members of the course always see it |
| `--has-community-group` | bool | Whether the course has its own discussion board group on the Members Portal; turning it on creates the group and turning it off deletes it |
| `--overview-text` | string | Course overview in HTML, shown on the course page below the description; hidden from customers who have not joined unless ShowOverview is true |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--new-large-image-url` | string | URL of a new banner/large image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-large-image-file` | bool | Set to true to remove the existing banner/large image |
| `--active` | bool | Whether the course is published; an unpublished course is hidden from the Members Portal and its course page cannot be opened, even by customers who joined it |
| `--group-name` | string | Optional course category shown as the course's tag and offered as a category filter on the Members Portal; reuse an existing category's exact spelling so courses group together |
| `--display-order` | int | Administrative sort position among the location's courses; on create it is an insert index (0 puts the course first, a large number puts it last), and the system renumbers every course in steps of 100 after each save. The Members Portal lists courses newest first, not by this value |
| `--show-in-home-page` | bool | Whether the course is featured on the Members Portal home page that customers see after signing in |
| `--visibility` | enum | Who can find and join the course: Public (1, listed, any customer can join), Hidden (2, not listed, anyone with the link can view and join), Private (3, not listed; only customers an administrator adds as course members can open it), or Paid (4, listed and joinable like Public). Charging is driven by TariffId, not by this value; defaults to Public |
| `--tariff-id` | long | Optional ID of the plan charged for the course: every new course member, whether they join on the Members Portal or an administrator adds them, gets a contract for this plan, and when the plan price is above zero their access stays pending until that invoice is paid. Applies whatever the Visibility; leave empty for a free course |

#### Course PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--host-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--host-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus courses update <id> --host-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### Course enum values

| Option | Valid values |
| ------ | ------------ |
| `--visibility` | `1` Public, `2` Hidden, `3` Private, `4` Paid |

<!-- END:GENERATED entity=Courses -->
