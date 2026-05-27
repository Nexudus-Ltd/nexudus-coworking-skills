# Reports

<!-- BEGIN:GENERATED entity=Reports -->

A **Report** defines a configured report that can be generated on demand or scheduled. Reports cover various data categories including check-ins, invoices, bookings, members, revenue, and occupancy metrics.

Reports support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus reports list --agent` | List all reports |
| `nexudus reports list --id <id> --agent` | Filter by single ID |
| `nexudus reports list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus reports list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus reports list --business-id <value> --name <value> --agent` | Filter reports by properties |
| `nexudus reports list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reports get <id> --agent` | Get single report |
| `nexudus reports create --business-id <value> --name <value> --folder <value> --report-type <value> --agent` | Create report |
| `nexudus reports update <id> --name "New Name" --agent` | Update report |
| `nexudus reports delete <id> --yes --agent` | Delete report (no prompt) |

#### Report list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this report |
| `--folder` | string | The folder value for this report |
| `--report-type` | enum | The report type value for this report |
| `--report-xml` | string | The report xml value for this report |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Report create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this report |
| `--folder` | string, required | The folder value for this report |
| `--report-type` | enum, required | The report type value for this report |
| `--report-xml` | string | The report xml value for this report |

#### Report update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this report |
| `--folder` | string | The folder value for this report |
| `--report-type` | enum | The report type value for this report |
| `--report-xml` | string | The report xml value for this report |

#### Report enum values

| Option | Valid values |
| ------ | ------------ |
| `--report-type` | `1` Checkins, `2` ExtraServices, `3` TimePasses, `4` Members, `5` AllMembers, `6` Invoices, `7` Bookings, `8` TodayBookings, `9` PaidInvoices, `10` Upgrades, `11` Tariffs, `12` Accruals, `13` Transactions, `14` AccrualsLiable, `15` AccrualsDelivered, `16` IncomePaid, `17` AccountsReceivable, `18` TariffHistory, `19` RecurrentCharges, `20` Events, `21` BookingCredit, `22` AccrualsByDelivery, `23` Tasks, `24` AllTasks, `25` Visitors, `26` CrmLeadTimes, `27` Desks, `28` UpgradesTransactions, `29` DesksOccupancy, `30` PricePlanOccupancy, `31` UnPaidInvoices, `32` ResourceOccupancy, `33` Crm, `34` SimpleBookings, `35` Surveys, `36` AccrualsBySaleDate, `37` InvoiceHeaders, `38` InvoicesBySaleDate, `39` DeferredRevenueByMonth, `40` Discounts, `41` CustomerCountChurnByMonth, `42` CustomerDetailsChurnByMonth, `43` CustomerCountChurnByMonthPayingMembers, `44` CustomerDetailsChurnByMonthPayingMembers, `45` FormPages, `46` GetCustomerDetailsRevenueChurnByMonth, `47` CancelledBookings, `998` CustomUrl, `999` CustomProcedure |

<!-- END:GENERATED entity=Reports -->
