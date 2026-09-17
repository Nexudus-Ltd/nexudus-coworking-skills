# CoworkerIdentityChecks

<!-- BEGIN:GENERATED entity=CoworkerIdentityChecks -->

Customer ID checks verify a customer's identity or address for a location through operator-reviewed documents or Stripe Identity, and track progress from pending through completion.

CoworkerIdentityChecks support Search, Get, Create, Update, Delete.
CoworkerIdentityChecks also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkeridentitychecks list --agent` | List all coworkeridentitychecks |
| `nexudus coworkeridentitychecks list --id <id> --agent` | Filter by single ID |
| `nexudus coworkeridentitychecks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkeridentitychecks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkeridentitychecks list --business-name <value> --coworker-full-name <value> --agent` | Filter coworkeridentitychecks by properties |
| `nexudus coworkeridentitychecks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkeridentitychecks list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkeridentitychecks get <id> --agent` | Get single coworkeridentitycheck |
| `nexudus coworkeridentitychecks create --business-id <value> --coworker-id <value> --name <value> --identity-check-provider <value> --identity-document-type <value> --address-document-type <value> --verification-type <value> --agent` | Create coworkeridentitycheck |
| `nexudus coworkeridentitychecks update <id> --name "New Name" --agent` | Update coworkeridentitycheck |
| `nexudus coworkeridentitychecks delete <id> --yes --agent` | Delete coworkeridentitycheck (no prompt) |
| `nexudus coworkeridentitychecks run-command <key> <ids> --agent` | Run entity command |

#### CoworkerIdentityCheck list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this identity check. |
| `--business-name` | string | Display value for Business.Name. |
| `--coworker-id` | long | ID of the customer whose identity or address is being verified. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--name` | string | Required operator-facing label for this verification check. |
| `--identity-check-provider` | enum | How the check is performed: Manual for operator-reviewed documents, or StripeIdentity for a Stripe Identity session. |
| `--identity-document-type` | enum | Identity document type when VerificationType is IdDocument: Passport, DriversLicense, IdCard, UniformedServiceId, CertificateOfNaturalization, AccessCard, MatriculaConsular, ResidentCard, UniversityId, NEXUSCard, or Other. |
| `--identity-document-number` | string | Optional number or identifier printed on the identity document. |
| `--identity-document-issued-by` | string | Optional authority or organization that issued the identity document. |
| `--identity-document-expiration-date` | DateTime | Optional expiration date recorded on the identity document. |
| `--from-identity-document-expiration-date` | range | |
| `--to-identity-document-expiration-date` | range | |
| `--address-document-type` | enum | Address document type when VerificationType is Address: Passport, DriversLicense, IdCard, LeaseRentalAgreement, InsurancePolicy, Mortgage, VehicleRegistrationCard, VoterCard, or Other. |
| `--verification-type` | enum | Purpose of the check: IdDocument for identity verification or Address for address verification. |
| `--description` | string | Optional free-text notes describing this verification check. |
| `--verification-status` | enum | Read-only verification lifecycle status: Pending, Submitted, Successful, Failed, or Cancelled; manual checks derive it from their document records. |
| `--last-error` | string | Read-only most recent error message reported when the verification fails. |
| `--identity-check-provider1` | enum | Optional provider for a second check created with this request: Manual or StripeIdentity; requires VerificationType1. |
| `--verification-type1` | enum | Optional purpose for a second check created with this request: IdDocument or Address; requires IdentityCheckProvider1. |
| `--description1` | string | Optional notes for the second check created with this request; used only with VerificationType1. |
| `--identity-check-provider2` | enum | Optional provider for a third check created with this request: Manual or StripeIdentity; requires VerificationType2. |
| `--verification-type2` | enum | Optional purpose for a third check created with this request: IdDocument or Address; requires IdentityCheckProvider2. |
| `--description2` | string | Optional notes for the third check created with this request; used only with VerificationType2. |
| `--address-check-document-types` | string | Document types accepted as proof of address for this check, used when VerificationType is Address. |
| `--identity-check-document-types` | string | Document types accepted as proof of identity for this check, used when VerificationType is IdDocument. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerIdentityCheck sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerIdentityCheck create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this identity check. |
| `--coworker-id` | long, required | ID of the customer whose identity or address is being verified. |
| `--name` | string, required | Required operator-facing label for this verification check. |
| `--identity-check-provider` | enum, required | How the check is performed: Manual for operator-reviewed documents, or StripeIdentity for a Stripe Identity session. |
| `--identity-document-type` | enum, required | Identity document type when VerificationType is IdDocument: Passport, DriversLicense, IdCard, UniformedServiceId, CertificateOfNaturalization, AccessCard, MatriculaConsular, ResidentCard, UniversityId, NEXUSCard, or Other. |
| `--identity-document-number` | string | Optional number or identifier printed on the identity document. |
| `--identity-document-issued-by` | string | Optional authority or organization that issued the identity document. |
| `--identity-document-expiration-date` | DateTime | Optional expiration date recorded on the identity document. |
| `--address-document-type` | enum, required | Address document type when VerificationType is Address: Passport, DriversLicense, IdCard, LeaseRentalAgreement, InsurancePolicy, Mortgage, VehicleRegistrationCard, VoterCard, or Other. |
| `--verification-type` | enum, required | Purpose of the check: IdDocument for identity verification or Address for address verification. |
| `--description` | string | Optional free-text notes describing this verification check. |
| `--identity-check-provider1` | enum | Optional provider for a second check created with this request: Manual or StripeIdentity; requires VerificationType1. |
| `--verification-type1` | enum | Optional purpose for a second check created with this request: IdDocument or Address; requires IdentityCheckProvider1. |
| `--description1` | string | Optional notes for the second check created with this request; used only with VerificationType1. |
| `--identity-check-provider2` | enum | Optional provider for a third check created with this request: Manual or StripeIdentity; requires VerificationType2. |
| `--verification-type2` | enum | Optional purpose for a third check created with this request: IdDocument or Address; requires IdentityCheckProvider2. |
| `--description2` | string | Optional notes for the third check created with this request; used only with VerificationType2. |
| `--address-check-document-types` | string | Document types accepted as proof of address for this check, used when VerificationType is Address. |
| `--identity-check-document-types` | string | Document types accepted as proof of identity for this check, used when VerificationType is IdDocument. |

#### CoworkerIdentityCheck update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this identity check. |
| `--coworker-id` | long | ID of the customer whose identity or address is being verified. |
| `--name` | string | Required operator-facing label for this verification check. |
| `--identity-check-provider` | enum | How the check is performed: Manual for operator-reviewed documents, or StripeIdentity for a Stripe Identity session. |
| `--identity-document-type` | enum | Identity document type when VerificationType is IdDocument: Passport, DriversLicense, IdCard, UniformedServiceId, CertificateOfNaturalization, AccessCard, MatriculaConsular, ResidentCard, UniversityId, NEXUSCard, or Other. |
| `--identity-document-number` | string | Optional number or identifier printed on the identity document. |
| `--identity-document-issued-by` | string | Optional authority or organization that issued the identity document. |
| `--identity-document-expiration-date` | DateTime | Optional expiration date recorded on the identity document. |
| `--address-document-type` | enum | Address document type when VerificationType is Address: Passport, DriversLicense, IdCard, LeaseRentalAgreement, InsurancePolicy, Mortgage, VehicleRegistrationCard, VoterCard, or Other. |
| `--verification-type` | enum | Purpose of the check: IdDocument for identity verification or Address for address verification. |
| `--description` | string | Optional free-text notes describing this verification check. |
| `--address-check-document-types` | string | Document types accepted as proof of address for this check, used when VerificationType is Address. |
| `--identity-check-document-types` | string | Document types accepted as proof of identity for this check, used when VerificationType is IdDocument. |

#### CoworkerIdentityCheck PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coworkeridentitychecks update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerIdentityCheck (key fields)

`Id`, `BusinessName`, `CoworkerFullName`, `Name`, `VerificationType`, `VerificationStatus`

#### CoworkerIdentityCheck enum values

| Option | Valid values |
| ------ | ------------ |
| `--identity-check-provider` | `1` Manual, `2` StripeIdentity |
| `--identity-document-type` | `1` Passport, `2` DriversLicense, `3` IdCard, `4` UniformedServiceId, `5` CertificateOfNaturalization, `6` AccessCard, `7` MatriculaConsular, `8` ResidentCard, `9` UniversityId, `10` NEXUSCard, `99` Other |
| `--address-document-type` | `1` Passport, `2` DriversLicense, `3` IdCard, `4` LeaseRentalAgreement, `5` InsurancePolicy, `6` Mortgage, `7` VehicleRegistrationCard, `8` VoterCard, `9` BankStatement, `99` Other |
| `--verification-type` | `1` IdDocument, `2` Address |

<!-- END:GENERATED entity=CoworkerIdentityChecks -->
