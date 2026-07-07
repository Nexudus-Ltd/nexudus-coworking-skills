# TaxRates

<!-- BEGIN:GENERATED entity=TaxRates -->

A **TaxRate** defines a tax percentage applied to products, services, and invoices. Multiple tax rates can be configured for different jurisdictions or product categories.

TaxRates support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus taxrates list --agent` | List all taxrates |
| `nexudus taxrates list --id <id> --agent` | Filter by single ID |
| `nexudus taxrates list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus taxrates list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus taxrates list --business-id <value> --name <value> --agent` | Filter taxrates by properties |
| `nexudus taxrates list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus taxrates list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus taxrates get <id> --agent` | Get single taxrate |
| `nexudus taxrates create --business-id <value> --name <value> --rate <value> --exemption-reason <value> --agent` | Create taxrate |
| `nexudus taxrates update <id> --name "New Name" --agent` | Update taxrate |
| `nexudus taxrates delete <id> --yes --agent` | Delete taxrate (no prompt) |

#### TaxRate list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this tax rate |
| `--rate` | decimal | The rate value for this tax rate |
| `--from-rate` | range | |
| `--to-rate` | range | |
| `--exemption-reason` | enum | Tax exemption reason code (e.g. M01-M99 for various exemptions, or None if no exemption applies) |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TaxRate sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TaxRate create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this tax rate |
| `--rate` | decimal, required | The rate value for this tax rate |
| `--exemption-reason` | enum, required | Tax exemption reason code (e.g. M01-M99 for various exemptions, or None if no exemption applies) |

#### TaxRate update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this tax rate |
| `--rate` | decimal | The rate value for this tax rate |
| `--exemption-reason` | enum | Tax exemption reason code (e.g. M01-M99 for various exemptions, or None if no exemption applies) |

#### TaxRate enum values

| Option | Valid values |
| ------ | ------------ |
| `--exemption-reason` | `1` None, `2` M01, `3` M02, `4` M04, `5` M05, `6` M06, `7` M07, `8` M09, `9` M10, `10` M11, `11` M12, `12` M13, `13` M14, `14` M15, `15` M16, `16` M19, `17` M20, `18` M21, `19` M25, `20` M26, `21` M30, `22` M31, `23` M32, `24` M33, `25` M34, `26` M40, `27` M41, `28` M42, `29` M43, `30` M99 |

<!-- END:GENERATED entity=TaxRates -->
