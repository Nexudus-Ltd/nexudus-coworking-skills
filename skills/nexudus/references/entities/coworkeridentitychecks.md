# CoworkerIdentityChecks

<!-- BEGIN:GENERATED entity=CoworkerIdentityChecks -->

A **CoworkerIdentityCheck** represents a manual or Stripe Identity-based verification of a customer's identity or address. Each check is linked to a `Coworker` and a `Business` (location).

The `VerificationType` determines the nature of the check:

| VerificationType | Purpose |
| ---------------- | ------- |
| IdDocument (1)   | Verifies the customer's identity using an official document (passport, driver's license, ID card, etc.) |
| Address (2)      | Verifies the customer's address using a supporting document (lease agreement, insurance policy, voter card, etc.) |

When `VerificationType` is `IdDocument`, use `IdentityDocumentType` to specify the document kind, along with `IdentityDocumentNumber`, `IdentityDocumentIssuedBy`, and `IdentityDocumentExpirationDate`. When `VerificationType` is `Address`, use `AddressDocumentType` instead.

`IdentityCheckProvider` controls how the check is performed: `Manual` (1) means the operator reviews documents directly, while `StripeIdentity` (2) delegates verification to Stripe Identity.

The `VerificationStatus` tracks progress through the check lifecycle: `Pending` → `Submitted` → `Successful` or `Failed` (or `Cancelled`).

CoworkerIdentityChecks support Search, Get, Create, Update, Delete.
CoworkerIdentityChecks also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkeridentitychecks list --agent` | List all coworkeridentitychecks |
| `nexudus coworkeridentitychecks list --id <id> --agent` | Filter by single ID |
| `nexudus coworkeridentitychecks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkeridentitychecks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkeridentitychecks list --name <value> --agent` | Filter coworkeridentitychecks by properties |
| `nexudus coworkeridentitychecks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkeridentitychecks get <id> --agent` | Get single coworkeridentitycheck |
| `nexudus coworkeridentitychecks create --business-id <value> --coworker-id <value> --name <value> --identity-check-provider <value> --identity-document-type <value> --address-document-type <value> --agent` | Create coworkeridentitycheck |
| `nexudus coworkeridentitychecks update <id> --name "New Name" --agent` | Update coworkeridentitycheck |
| `nexudus coworkeridentitychecks delete <id> --yes --agent` | Delete coworkeridentitycheck (no prompt) |
| `nexudus coworkeridentitychecks run-command <key> <ids> --agent` | Run entity command |

#### CoworkerIdentityCheck list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--coworker-id` | long |  |
| `--name` | string | Display name for this verification check |
| `--identity-check-provider` | enum | How the check is performed: Manual (operator review) or StripeIdentity (Stripe-delegated) |
| `--identity-document-type` | enum | Type of identity document used when VerificationType is IdDocument |
| `--identity-document-number` | string | Number or identifier on the identity document |
| `--identity-document-issued-by` | string | Authority or organisation that issued the identity document |
| `--identity-document-expiration-date` | DateTime | Expiration date of the identity document |
| `--from-identity-document-expiration-date` | range | |
| `--to-identity-document-expiration-date` | range | |
| `--address-document-type` | enum | Type of address document used when VerificationType is Address |
| `--description` | string | Free-text notes or details about this check |
| `--billed` | bool |  |
| `--stripe-verification-session-id` | string |  |
| `--identity-check-provider1` | enum |  |
| `--verification-type1` | enum |  |
| `--description1` | string |  |
| `--identity-check-provider2` | enum |  |
| `--verification-type2` | enum |  |
| `--description2` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerIdentityCheck create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--coworker-id` | long, required |  |
| `--name` | string, required | Display name for this verification check |
| `--identity-check-provider` | enum, required | How the check is performed: Manual (operator review) or StripeIdentity (Stripe-delegated) |
| `--identity-document-type` | enum, required | Type of identity document used when VerificationType is IdDocument |
| `--identity-document-number` | string | Number or identifier on the identity document |
| `--identity-document-issued-by` | string | Authority or organisation that issued the identity document |
| `--identity-document-expiration-date` | DateTime | Expiration date of the identity document |
| `--address-document-type` | enum, required | Type of address document used when VerificationType is Address |
| `--description` | string | Free-text notes or details about this check |
| `--billed` | bool |  |
| `--stripe-verification-session-id` | string |  |
| `--identity-check-provider1` | enum |  |
| `--verification-type1` | enum |  |
| `--description1` | string |  |
| `--identity-check-provider2` | enum |  |
| `--verification-type2` | enum |  |
| `--description2` | string |  |

#### CoworkerIdentityCheck update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--coworker-id` | long |  |
| `--name` | string | Display name for this verification check |
| `--identity-check-provider` | enum | How the check is performed: Manual (operator review) or StripeIdentity (Stripe-delegated) |
| `--identity-document-type` | enum | Type of identity document used when VerificationType is IdDocument |
| `--identity-document-number` | string | Number or identifier on the identity document |
| `--identity-document-issued-by` | string | Authority or organisation that issued the identity document |
| `--identity-document-expiration-date` | DateTime | Expiration date of the identity document |
| `--address-document-type` | enum | Type of address document used when VerificationType is Address |
| `--description` | string | Free-text notes or details about this check |
| `--billed` | bool |  |
| `--stripe-verification-session-id` | string |  |

### CoworkerIdentityCheck (key fields)

`Id`, `BusinessName`, `CoworkerFullName`, `Name`, `VerificationType`, `VerificationStatus`

#### CoworkerIdentityCheck enum values

| Option | Valid values |
| ------ | ------------ |
| `--identity-check-provider` | `0` None, `1` Manual, `2` StripeIdentity |
| `--identity-document-type` | `0` None, `1` Passport, `2` DriversLicense, `3` IdCard, `4` UniformedServiceId, `5` CertificateOfNaturalization, `6` AccessCard, `7` MatriculaConsular, `8` ResidentCard, `9` UniversityId, `10` NEXUSCard, `99` Other |
| `--address-document-type` | `0` None, `1` Passport, `2` DriversLicense, `3` IdCard, `4` LeaseRentalAgreement, `5` InsurancePolicy, `6` Mortgage, `7` VehicleRegistrationCard, `8` VoterCard, `99` Other |

<!-- END:GENERATED entity=CoworkerIdentityChecks -->
