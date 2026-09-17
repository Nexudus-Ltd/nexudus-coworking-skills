# NewsLetterSubscribers

<!-- BEGIN:GENERATED entity=NewsLetterSubscribers -->

A newsletter subscriber (NewsLetterSubscriber) is an email address held at a location that can be sent newsletters; it is identified by that email, is only mailed while Active, may belong to any number of newsletter subscriber groups, and carries open and click tracking for the last newsletter sent.

NewsLetterSubscribers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus newslettersubscribers list --agent` | List all newslettersubscribers |
| `nexudus newslettersubscribers list --id <id> --agent` | Filter by single ID |
| `nexudus newslettersubscribers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus newslettersubscribers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus newslettersubscribers list --business-id <value> --name <value> --agent` | Filter newslettersubscribers by properties |
| `nexudus newslettersubscribers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus newslettersubscribers list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus newslettersubscribers get <id> --agent` | Get single newslettersubscriber |
| `nexudus newslettersubscribers create --business-id <value> --name <value> --email <value> --agent` | Create newslettersubscriber |
| `nexudus newslettersubscribers update <id> --name "New Name" --agent` | Update newslettersubscriber |
| `nexudus newslettersubscribers delete <id> --yes --agent` | Delete newslettersubscriber (no prompt) |

#### NewsLetterSubscriber list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this newsletter subscriber; the email address only has to be unique within this location, and a newsletter reaches only the subscribers of the location that owns it. |
| `--name` | string | Required full name of the subscriber, shown as Full name in the admin and used for the {fullname}, {firstname}, and {lastname} newsletter merge tokens; public sign-ups that supply no name fall back to the email address. |
| `--company-name` | string | Optional company or organization name for the subscriber, available to newsletter content through the {companyname} merge token. |
| `--email` | string | Required email address the newsletter is delivered to, validated as an email address and unique per location; it is also the key used to find a subscriber when subscribing, unsubscribing, or adding to a group, and a send collapses duplicate email addresses so only one copy goes out. |
| `--visit-reason` | string | Optional free-text note recording why or how the subscriber was added, shown as Reason for the visit; it comes from a public newsletter sign-up form or is supplied by the system, for example when a customer checks in, and re-subscribing the same email overwrites it. |
| `--active` | bool | Whether the subscriber is still subscribed; only active subscribers are included when a newsletter is sent, unsubscribing sets it to false, and it defaults to false on create, so set it to true when adding a subscriber who should receive newsletters. |
| `--viewed` | bool | Whether this subscriber opened the most recently sent newsletter, not whether they have ever opened one; read-only, set by the open-tracking pixel and reset to false for every recipient each time a newsletter is sent. |
| `--clicked` | bool | Whether this subscriber clicked a link in the most recently sent newsletter, not whether they have ever clicked one; read-only, set by the click-tracking redirect and reset to false for every recipient each time a newsletter is sent. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### NewsLetterSubscriber sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### NewsLetterSubscriber create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this newsletter subscriber; the email address only has to be unique within this location, and a newsletter reaches only the subscribers of the location that owns it. |
| `--name` | string, required | Required full name of the subscriber, shown as Full name in the admin and used for the {fullname}, {firstname}, and {lastname} newsletter merge tokens; public sign-ups that supply no name fall back to the email address. |
| `--company-name` | string | Optional company or organization name for the subscriber, available to newsletter content through the {companyname} merge token. |
| `--email` | string, required | Required email address the newsletter is delivered to, validated as an email address and unique per location; it is also the key used to find a subscriber when subscribing, unsubscribing, or adding to a group, and a send collapses duplicate email addresses so only one copy goes out. |
| `--visit-reason` | string | Optional free-text note recording why or how the subscriber was added, shown as Reason for the visit; it comes from a public newsletter sign-up form or is supplied by the system, for example when a customer checks in, and re-subscribing the same email overwrites it. |
| `--active` | bool | Whether the subscriber is still subscribed; only active subscribers are included when a newsletter is sent, unsubscribing sets it to false, and it defaults to false on create, so set it to true when adding a subscriber who should receive newsletters. |
| `--groups` | list, repeat flag | List of newsletter subscriber group IDs this subscriber belongs to, and the side of the relationship that persists group membership, so set it here rather than from the group; an empty list still receives newsletters sent to the whole location but no group-targeted ones, and a group with smart-group criteria drops a subscriber who stops matching on its 12-hourly update. |
| `--added-groups` | list, repeat flag | IDs added to the Groups relationship. |
| `--removed-groups` | list, repeat flag | IDs removed from the Groups relationship. |

#### NewsLetterSubscriber update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this newsletter subscriber; the email address only has to be unique within this location, and a newsletter reaches only the subscribers of the location that owns it. |
| `--name` | string | Required full name of the subscriber, shown as Full name in the admin and used for the {fullname}, {firstname}, and {lastname} newsletter merge tokens; public sign-ups that supply no name fall back to the email address. |
| `--company-name` | string | Optional company or organization name for the subscriber, available to newsletter content through the {companyname} merge token. |
| `--email` | string | Required email address the newsletter is delivered to, validated as an email address and unique per location; it is also the key used to find a subscriber when subscribing, unsubscribing, or adding to a group, and a send collapses duplicate email addresses so only one copy goes out. |
| `--visit-reason` | string | Optional free-text note recording why or how the subscriber was added, shown as Reason for the visit; it comes from a public newsletter sign-up form or is supplied by the system, for example when a customer checks in, and re-subscribing the same email overwrites it. |
| `--active` | bool | Whether the subscriber is still subscribed; only active subscribers are included when a newsletter is sent, unsubscribing sets it to false, and it defaults to false on create, so set it to true when adding a subscriber who should receive newsletters. |
| `--groups` | list, repeat flag | List of newsletter subscriber group IDs this subscriber belongs to, and the side of the relationship that persists group membership, so set it here rather than from the group; an empty list still receives newsletters sent to the whole location but no group-targeted ones, and a group with smart-group criteria drops a subscriber who stops matching on its 12-hourly update. |
| `--added-groups` | list, repeat flag | IDs added to the Groups relationship. |
| `--removed-groups` | list, repeat flag | IDs removed from the Groups relationship. |

#### NewsLetterSubscriber PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus newslettersubscribers update <id> --company-name "«PII:NAME:a3f2b1c9»" --agent`

**List properties (only returned by `get`, not by `list`):** `Groups`, `AddedGroups`, `RemovedGroups`

<!-- END:GENERATED entity=NewsLetterSubscribers -->
