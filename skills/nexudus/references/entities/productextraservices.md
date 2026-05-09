# ProductExtraServices

<!-- BEGIN:GENERATED entity=ProductExtraServices -->

A **ProductExtraService** links an `ExtraService` to a `Product`. The meaning of `UsesIncluded` depends on the type of the linked extra service:

- **Booking time** (ExtraService with `IsPrintingCredit = false`) — customers receive an allowance of booking time for the resource type(s) associated with that extra service. For example, a product called "Hot Desk Bundle" might include 2 hours of meeting room usage — achieved by linking a "Meeting Room Hourly" extra service with `--uses-included 120`.
- **Printing credit** (ExtraService with `IsPrintingCredit = true`) — customers receive a number of print jobs/pages. `UsesIncluded` is the number of printing credits included. The linked extra service must have `ChargePeriod = 5` (Uses) and `Price = 1`.

Always check `IsPrintingCredit` on the linked extra service before interpreting `UsesIncluded`.

For booking-time extra services, the unit of `UsesIncluded` is determined by the **ChargePeriod** of the linked `ExtraService`:

| ExtraService ChargePeriod | UsesIncluded unit |
| ------------------------- | ----------------- |
| 1 (Minutes)               | Minutes           |
| 2 (Days)                  | Days              |
| 3 (Weeks)                 | Weeks             |
| 4 (Months)                | Months            |
| 5 (Uses)                  | Individual uses   |
| 6 (FourWeekMonths)        | 4-week periods    |

So `--uses-included 60` on a minutes extra service means 60 minutes of booking time included. On a daily extra service it means 60 full days.

ProductExtraServices support Search, Get, Create, Update, Delete.
ProductExtraServices also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus productextraservices list --agent` | List all productextraservices |
| `nexudus productextraservices list --id <id> --agent` | Filter by single ID |
| `nexudus productextraservices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus productextraservices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus productextraservices list --uses-included <value> --agent` | Filter productextraservices by properties |
| `nexudus productextraservices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus productextraservices get <id> --agent` | Get single productextraservice |
| `nexudus productextraservices create --product-id <value> --extra-service-id <value> --uses-included <value> --agent` | Create productextraservice |
| `nexudus productextraservices update <id> --name "New Name" --agent` | Update productextraservice |
| `nexudus productextraservices delete <id> --yes --agent` | Delete productextraservice (no prompt) |
| `nexudus productextraservices run-command <key> <ids> --agent` | Run entity command |

#### ProductExtraService list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--product-id` | long |  |
| `--extra-service-id` | long |  |
| `--uses-included` | int | Uses included |
| `--from-uses-included` | range | |
| `--to-uses-included` | range | |
| `--expire-time-in-months` | int |  |
| `--from-expire-time-in-months` | range | |
| `--to-expire-time-in-months` | range | |
| `--expire-time-in-weeks` | int |  |
| `--from-expire-time-in-weeks` | range | |
| `--to-expire-time-in-weeks` | range | |
| `--expiration-type` | enum | Expiration type |
| `--expires-in` | int | Expires in |
| `--from-expires-in` | range | |
| `--to-expires-in` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProductExtraService create options

| Option | Type | Description |
| --- | --- | --- |
| `--product-id` | long, required |  |
| `--extra-service-id` | long, required |  |
| `--uses-included` | int, required | Uses included |
| `--expire-time-in-months` | int |  |
| `--expire-time-in-weeks` | int |  |
| `--expiration-type` | enum | Expiration type |
| `--expires-in` | int | Expires in |

#### ProductExtraService update options

| Option | Type | Description |
| --- | --- | --- |
| `--product-id` | long |  |
| `--extra-service-id` | long |  |
| `--uses-included` | int | Uses included |
| `--expire-time-in-months` | int |  |
| `--expire-time-in-weeks` | int |  |
| `--expiration-type` | enum | Expiration type |
| `--expires-in` | int | Expires in |

### ProductExtraService (key fields)

`Id`, `ProductName`, `ExtraServiceName`, `ExtraServiceChargePeriod`, `UsesIncluded`

<!-- END:GENERATED entity=ProductExtraServices -->

## Workflows

### "Add booking time for a resource type to a product"

ProductExtraServices link an ExtraService (resource pricing rule) to a Product so that customers purchasing the product automatically receive an allowance of booking time for that resource type.

1. Find the product: `nexudus products list --query "Bundle" --agent` → note the `Id`
2. Find the extra service: `nexudus extraservices list --query "Meeting Room" --agent` → note the `Id` and `ChargePeriod`
3. Create the link — set `--uses-included` in the unit matching the extra service's charge period (e.g. 120 minutes if ChargePeriod=1):
   ```shell
   nexudus productextraservices create \
     --product-id <productId> \
     --extra-service-id <extraServiceId> \
     --uses-included 120 \
     --agent
   ```
4. Check `ok` is `true`, read `data.Id` for the new link ID

### "List booking time included in a product"

1. `nexudus productextraservices list --agent`
2. Filter results where `ProductId` matches the target product
3. The `ExtraServiceChargePeriod` field indicates the unit of `UsesIncluded` for each row

### "Update booking time included in a product"

1. `nexudus productextraservices list --agent` → find the link by `ProductId` and `ExtraServiceId`
2. `nexudus productextraservices update <id> --uses-included 5 --agent`
3. Verify the update by checking the returned `data`

### "Remove booking time from a product"

1. `nexudus productextraservices list --agent` → find the link by `ProductId` and `ExtraServiceId`
2. `nexudus productextraservices delete <id> --yes --agent`
3. Check `ok` is `true`

### "Add printing credit to a product"

A printing credit extra service has `IsPrintingCredit = true`, `ChargePeriod = 5` (Uses), and `Price = 1`. Linking it to a product via a `ProductExtraService` grants customers a number of print jobs when they purchase the product.

1. Check whether a printing credit extra service already exists: `nexudus extraservices list --agent` → look for an entry where `IsPrintingCredit` is `true`
2. If none exists, create one:
   ```shell
   nexudus extraservices create \
     --business <businessId> \
     --name "Printing Credit" \
     --printing-credit true \
     --charge-period 5 \
     --price 1 \
     --agent
   ```
   Note the `Id` from `data.Id`.
3. Find the product: `nexudus products list --query "Bundle" --agent` → note the `Id`
4. Create the link — set `--uses-included` to the number of printing credits to include:
   ```shell
   nexudus productextraservices create \
     --product-id <productId> \
     --extra-service-id <extraServiceId> \
     --uses-included 50 \
     --agent
   ```
5. Check `ok` is `true`, read `data.Id` for the new link ID

### "Update printing credit included in a product"

1. `nexudus productextraservices list --agent` → find the link where `ExtraServiceChargePeriod` is `5` and the extra service has `IsPrintingCredit = true`
2. `nexudus productextraservices update <id> --uses-included <newAmount> --agent`
3. Verify the update by checking the returned `data`

### "Remove printing credit from a product"

1. `nexudus productextraservices list --agent` → find the link by `ProductId` and the printing credit `ExtraServiceId`
2. `nexudus productextraservices delete <id> --yes --agent`
3. Check `ok` is `true`
