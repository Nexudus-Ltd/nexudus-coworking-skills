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
| `nexudus coworkeridentitychecks list --query "search" --agent` | Search coworkeridentitychecks by name |
| `nexudus coworkeridentitychecks list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkeridentitychecks get <id> --agent` | Get single coworkeridentitycheck |
| `nexudus coworkeridentitychecks create --business <value> --coworker-id <value> --name <value> --agent` | Create coworkeridentitycheck |
| `nexudus coworkeridentitychecks update <id> --name "New Name" --agent` | Update coworkeridentitycheck |
| `nexudus coworkeridentitychecks delete <id> --yes --agent` | Delete coworkeridentitycheck (no prompt) |
| `nexudus coworkeridentitychecks run-command <key> <ids> --agent` | Run entity command |

#### CoworkerIdentityCheck create options

`--business` (required), `--coworker-id` (required), `--name` (required), `--identity-check-provider`, `--identity-document-type`, `--identity-document-number`, `--identity-document-issued-by`, `--identity-document-expiration-date`, `--address-document-type`, `--verification-type`, `--description`, `--verification-status`

#### CoworkerIdentityCheck update options

`--coworker-id`, `--name`, `--identity-check-provider`, `--identity-document-type`, `--identity-document-number`, `--identity-document-issued-by`, `--identity-document-expiration-date`, `--address-document-type`, `--verification-type`, `--description`, `--verification-status`

### CoworkerIdentityCheck (key fields)

`Id`, `BusinessId`, `BusinessName`, `CoworkerId`, `CoworkerFullName`, `Name`, `VerificationType`, `VerificationStatus`

#### CoworkerIdentityCheck enum values

| Option | Valid values |
| ------ | ------------ |
| `--identity-check-provider` | `0` None, `1` Manual, `2` StripeIdentity |
| `--identity-document-type` | `0` None, `1` Passport, `2` DriversLicense, `3` IdCard, `4` UniformedServiceId, `5` CertificateOfNaturalization, `6` AccessCard, `7` MatriculaConsular, `8` ResidentCard, `9` UniversityId, `10` NEXUSCard, `99` Other |
| `--address-document-type` | `0` None, `1` Passport, `2` DriversLicense, `3` IdCard, `4` LeaseRentalAgreement, `5` InsurancePolicy, `6` Mortgage, `7` VehicleRegistrationCard, `8` VoterCard, `99` Other |
| `--verification-type` | `0` None, `1` IdDocument, `2` Address |
| `--verification-status` | `0` None, `1` Pending, `2` Submitted, `3` Successful, `4` Failed, `5` Cancelled |

<!-- END:GENERATED entity=CoworkerIdentityChecks -->
