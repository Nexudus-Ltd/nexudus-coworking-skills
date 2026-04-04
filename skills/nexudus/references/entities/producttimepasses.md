# ProductTimePasses

<!-- BEGIN:GENERATED entity=ProductTimePasses -->

A **ProductTimePass** links a `TimePass` to a `Product` so that customers purchasing the product automatically receive an amount of check-in time. The nature of that time depends on the type of the linked `TimePass`:

- **Day Pass** (TimePass with `MinutesIncluded` = null) — `PassesIncluded` is the number of calendar days. The customer can check in any number of times during each calendar day they hold.
- **Time Pass** (TimePass with `MinutesIncluded` set) — `PassesIncluded` is the number of pass instances (each worth `MinutesIncluded` minutes). Multiply `PassesIncluded` by `MinutesIncluded` to get total hours. For example, `PassesIncluded = 10` with a 60-minute time pass gives the customer 10 hours of check-in time to use across different dates.

ProductTimePasses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus producttimepasses list --agent` | List all producttimepasses |
| `nexudus producttimepasses list --id <id> --agent` | Filter by single ID |
| `nexudus producttimepasses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus producttimepasses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus producttimepasses list --passes-included <value> --agent` | Filter producttimepasses by properties |
| `nexudus producttimepasses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus producttimepasses get <id> --agent` | Get single producttimepass |
| `nexudus producttimepasses create --product-id <value> --time-pass-id <value> --passes-included <value> --agent` | Create producttimepass |
| `nexudus producttimepasses update <id> --name "New Name" --agent` | Update producttimepass |
| `nexudus producttimepasses delete <id> --yes --agent` | Delete producttimepass (no prompt) |

#### ProductTimePass list filter options

`--product-id`, `--time-pass-id`, `--passes-included`, `--expire-time-in-months`, `--expire-time-in-weeks`, `--expiration-type`, `--expires-in`

#### ProductTimePass create options

`--product-id` (required), `--time-pass-id` (required), `--passes-included` (required), `--expire-time-in-months`, `--expire-time-in-weeks`, `--expiration-type`, `--expires-in`

#### ProductTimePass update options

`--product-id`, `--time-pass-id`, `--passes-included`, `--expire-time-in-months`, `--expire-time-in-weeks`, `--expiration-type`, `--expires-in`

### ProductTimePass (key fields)

`Id`, `ProductName`, `TimePassName`, `PassesIncluded`

<!-- END:GENERATED entity=ProductTimePasses -->

## Workflows

### "Add passes to a product"

A ProductTimePass links a `TimePass` to a `Product` so customers purchasing the product receive check-in time. The amount and type of time depends on the linked `TimePass`:

- Linking a **Day Pass** (no `MinutesIncluded`) gives the customer a number of calendar days — each day allows unlimited check-ins. Set `--passes-included` to the number of calendar days.
- Linking a **Time Pass** (has `MinutesIncluded`) gives the customer a number of hours to use across any dates. Set `--passes-included` to the number of pass instances; total minutes = `PassesIncluded × MinutesIncluded`.

**Example: 5 calendar days**

1. Find the product: `nexudus products list --query "Day Pass Bundle" --agent` → note the `Id`
2. Find the day pass: `nexudus timepasses list --query "Day Pass" --agent` → confirm `MinutesIncluded` is null → note the `Id`
3. Create the link:
   ```shell
   nexudus producttimepasses create \
     --product-id <productId> \
     --time-pass-id <timePassId> \
     --passes-included 5 \
     --agent
   ```

**Example: 100 hours across different dates**

1. Find the product and note its `Id`
2. Find a time pass with `MinutesIncluded = 60` (1 hour per pass): `nexudus timepasses list --query "1 Hour Pass" --agent` → note the `Id`
3. Create the link with `--passes-included 100` (100 × 60 min = 6000 min = 100 hours):
   ```shell
   nexudus producttimepasses create \
     --product-id <productId> \
     --time-pass-id <timePassId> \
     --passes-included 100 \
     --agent
   ```
4. Check `ok` is `true`, read `data.Id` for the new link ID

### "List passes included in a product"

1. `nexudus producttimepasses list --agent`
2. Filter results where `ProductId` matches the target product

### "Update passes included in a product"

1. `nexudus producttimepasses list --agent` → find the link by `ProductId` and `TimePassId`
2. `nexudus producttimepasses update <id> --passes-included 20 --agent`
3. Verify the update by checking the returned `data`

### "Remove a pass from a product"

1. `nexudus producttimepasses list --agent` → find the link by `ProductId` and `TimePassId`
2. `nexudus producttimepasses delete <id> --yes --agent`
3. Check `ok` is `true`
