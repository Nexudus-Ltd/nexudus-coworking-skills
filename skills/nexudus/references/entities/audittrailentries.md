# AuditTrailEntries

<!-- BEGIN:GENERATED entity=AuditTrailEntries -->

Represents a read-only log of entity creations and modifications by users or the system. Useful for troubleshooting issues or finding out when an entity was created and what modifications were made to it.

Creation entries (`AuditType = 1`) do not record the values for the individual fields. To infer the initial values, look at the first update entry for that entity and read the `OldValue` for each property.

Use `AuditTrailEntry_EntityId` to search by the integer ID of the audited record.

Not all entities are fully audited. These are the ones currently supported by the `AuditTrailEntry_EntityShortName` filter:

Charge, ContractSchedule, CoworkerBookingCredit, CoworkerContract, CoworkerExtraService, CoworkerInvoice, CoworkerLedgerEntry, CoworkerPaymentMethod, CoworkerProduct, FinancialAccount, CoworkerTask, CrmOpportunity, Booking, Checkin, Coworker, CoworkerIdentityCheck, Resource, Team, Visitor, Business, BusinessSetting, FloorPlanDesk, User.

The `AuditType` field uses the `eAuditType` enum: `1` = Create, `2` = Update, `3` = Delete.

AuditTrailEntries support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus audittrailentries list --agent` | List all audittrailentries |
| `nexudus audittrailentries list --id <id> --agent` | Filter by single ID |
| `nexudus audittrailentries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus audittrailentries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus audittrailentries list --business-id <value> --entity-short-name <value> --agent` | Filter audittrailentries by properties |
| `nexudus audittrailentries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus audittrailentries list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus audittrailentries get <id> --agent` | Get single audittrailentry |

#### AuditTrailEntry list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--entity-short-name` | string | Short name of the audited entity type (e.g. Coworker, Booking, Charge) |
| `--description` | string | Human-readable description of the audit trail entry |
| `--property-name` | string | Name of the property that was changed |
| `--audit-type` | enum | Type of audit action: 1 = Create, 2 = Update, 3 = Delete |
| `--old-value` | string | Previous value of the property before the change |
| `--new-value` | string | New value of the property after the change |
| `--action-by` | string | User or system account that performed the action |
| `--entity-id` | int | Integer ID of the audited record |
| `--from-entity-id` | range | |
| `--to-entity-id` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AuditTrailEntry sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### AuditTrailEntry enum values

| Option | Valid values |
| ------ | ------------ |
| `--audit-type` | `1` Create, `2` Update, `3` Delete |

<!-- END:GENERATED entity=AuditTrailEntries -->
