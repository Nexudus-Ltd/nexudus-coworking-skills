# PaymentGateways

<!-- BEGIN:GENERATED entity=PaymentGateways -->

A **PaymentGateway** represents a connection to one of the supported payment gateways used to process card payments.

Each gateway can be associated to one or more locations (`Business` entity) via the `DefaultPaymentGatewayId` property on the business. A gateway is configured with a specific `PaymentGatewayType` (e.g. `stripe`, `braintree`, `adyen`) and the corresponding credentials (`AccessToken`, `ConfigurationXml`).

An optional `TransactionFee` can be set to track per-transaction costs, and a `FinancialAccountId` and `TaxRateId` can be linked for accounting purposes.

PaymentGateways support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus paymentgateways list --agent` | List all paymentgateways |
| `nexudus paymentgateways list --id <id> --agent` | Filter by single ID |
| `nexudus paymentgateways list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus paymentgateways list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus paymentgateways list --name <value> --payment-gateway-type <value> --agent` | Filter paymentgateways by properties |
| `nexudus paymentgateways list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus paymentgateways list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus paymentgateways get <id> --agent` | Get single paymentgateway |
| `nexudus paymentgateways create --business-id <value> --name <value> --payment-gateway-type <value> --agent` | Create paymentgateway |
| `nexudus paymentgateways update <id> --name "New Name" --agent` | Update paymentgateway |
| `nexudus paymentgateways delete <id> --yes --agent` | Delete paymentgateway (no prompt) |

#### PaymentGateway list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Display name for this payment gateway configuration |
| `--payment-gateway-type` | enum | The payment provider to use (e.g. stripe, braintree, adyen). Determines which credentials are required |
| `--attempt3d-secure` | bool | Whether attempt3d secure is enabled |
| `--configuration-xml` | string | Provider-specific configuration in XML format (e.g. merchant ID, additional keys) |
| `--transaction-fee` | decimal | Fee charged per transaction processed through this gateway |
| `--from-transaction-fee` | range | |
| `--to-transaction-fee` | range | |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### PaymentGateway sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### PaymentGateway create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Display name for this payment gateway configuration |
| `--payment-gateway-type` | enum, required | The payment provider to use (e.g. stripe, braintree, adyen). Determines which credentials are required |
| `--attempt3d-secure` | bool | Whether attempt3d secure is enabled |
| `--configuration-xml` | string | Provider-specific configuration in XML format (e.g. merchant ID, additional keys) |
| `--transaction-fee` | decimal | Fee charged per transaction processed through this gateway |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |

#### PaymentGateway update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Display name for this payment gateway configuration |
| `--attempt3d-secure` | bool | Whether attempt3d secure is enabled |
| `--configuration-xml` | string | Provider-specific configuration in XML format (e.g. merchant ID, additional keys) |
| `--transaction-fee` | decimal | Fee charged per transaction processed through this gateway |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |

### PaymentGateway (key fields)

`Id`, `Name`, `PaymentGatewayType`

#### PaymentGateway enum values

| Option | Valid values |
| ------ | ------------ |
| `--payment-gateway-type` | `0` None, `1` test, `2` authorize_net, `3` beanstream, `4` braintree, `6` first_data_e4, `7` jetpay_v2, `8` merchant_e_solutions, `9` netbilling, `10` payment_express, `12` sage, `13` stripe, `14` trans_first, `15` usa_epay, `17` blue_pay, `18` cyber_source, `19` elavon, `20` first_data_e4_v27, `21` litle, `22` mercury, `23` nmi, `24` payflow_pro, `25` quantum, `26` secure_net, `27` trust_commerce, `28` worldpay, `29` wirecard, `30` paymill, `31` merchant_warrior, `32` nab_transact, `33` secure_pay_au, `34` eway, `35` migs, `36` pin, `37` ogone, `38` realex, `39` moneris, `40` psi_gate, `41` epay, `42` hdfc, `43` net_pay, `44` redsys, `45` iridium, `46` barclays_epdq_extra_plus, `49` paypal, `50` payex, `51` openpay, `52` hps, `53` checkout, `54` checkout_v2, `55` worldpay_us, `56` conekta, `57` orbital, `59` barclaycard_smartpay, `60` trans_first_transaction_express, `63` forte, `65` citrus_pay, `66` payu_latam, `67` global_collect, `68` cayan, `69` clearhaus, `70` sage_pay, `71` safe_charge, `72` mercado_pago, `73` payeezy, `200` acapture, `201` adyen, `203` banco_sabadell, `208` blue_snap, `209` borgun, `210` bpoint, `212` bridge_pay, `213` card_connect, `214` card_stream, `215` cardprocess, `217` cecabank, `218` cenpos, `224` creditcall, `225` credorax, `226` ct_payment, `227` culqi, `229` data_cash, `230` diamond_mind, `231` dibs, `232` digitzs, `234` element, `237` eway_rapid, `238` ezic, `239` fat_zebra, `242` first_giving, `243` first_pay, `244` flo2cash, `245` flo2cash_simple, `247` global, `249` global_iris, `250` global_transport, `253` iats_payments, `255` iveri, `256` ixopay, `257` jabstry, `258` jetpay, `260` kushki, `261` latitude19, `263` maxipago, `266` merchant_partners, `272` mundipagg, `274` ncr_secure_pay, `280` optimal_payments, `282` pay_conex, `283` pay_junction_v2, `288` paymentez, `291` paystation, `294` pro_pay, `296` qbms, `298` quickpay, `299` quickpay_v10, `300` qvalent, `303` s5, `309` securion_pay, `312` tns, `317` vanco, `318` visanet_peru, `319` wepay, `320` stripe_payment_intents, `321` stripeACH, `323` quickbooks, `324` monei, `401` HostedPaymentPage1, `402` HostedPaymentPage2, `403` HostedPaymentPage3 |

<!-- END:GENERATED entity=PaymentGateways -->
