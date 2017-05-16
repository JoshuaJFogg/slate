# Vouchers

## Add a Voucher to a Subscription

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

`POST http://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers`

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
voucherCode | string | Optional | voucher code







## Retrieve Voucher Configuration

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

`GET http://uat.mppglobal.com/api/vouchers/{voucherCode}/validate`

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
purchaseInfo | object | Optional | Voucher purchase info
purchasePrice | number | Optional | Purchase price
discountPrice | number | Optional | Discount price
renewalPrice | number | Optional | Renewal price
nextPaymentsDates | array[string] | Optional | Next payments dates
voucherInfo | object | Optional | Voucher info
startDate | string | Optional | Start date
expiryDate | string | Optional | Expiry date
offerInfo | object | Optional | Voucher offer info
name | string | Optional | Gets or sets the Name
description | string | Optional | Gets or sets the Description
usageType | integer | Optional | Gets or sets the UsageType
applicationData | object | Optional | Application data
name | string | Optional | Gets or sets the Name
message | string | Optional | Gets or sets the Message
message2 | string | Optional | Gets or sets the Message2
addCredits | object | Optional | Add credits
amount | integer | Optional | Gets or sets the Amount
currency | string | Optional | Gets or sets the Currency
paymentDetailsRequired | boolean | Optional | Gets or sets the PaymentDetailsRequired
lowStart | object | Optional | Low start
percentage | number | Optional | Gets or sets the Percentage
numberOfPeriods | integer | Optional | Gets or sets the NumberOfPeriods
lockInPeriods | integer | Optional | Gets or sets the lockInPeriods
closeSubOnExpiry | boolean | Optional | Gets or sets the CloseSubOnExpiry
serviceIds | array[integer] | Optional | Gets or sets the ServiceIds
paymentDetailsRequired | boolean | Optional | Gets or sets the PaymentDetailsRequired
percentageDiscount | object | Optional | Percentage discount
percentage | number | Optional | Gets or sets the Percentage
paymentDetailsRequired | boolean | Optional | Gets or sets the PaymentDetailsRequired
freePeriod | object | Optional | Free period
numberOfPeriods | integer | Optional | Gets or sets the NumberOfPeriods
serviceIds | array[integer] | Optional | Gets or sets the ServiceIds
paymentDetailsRequired | boolean | Optional | Gets or sets the PaymentDetailsRequired
groupDiscount | object | Optional | Group discount
activationCodeActivated | boolean | Optional | Activation code activated
metaData | object | Optional | Group discount offer type
qualifyingItemCount | integer | Optional | Qualifying item count
freeItemCountOrDiscountAmount | number | Optional | Free item count or discount amount
productIds | array[integer] | Optional | Product ids
configurationType | string | Optional | Configuration type
productSource | string | Optional | Product source
customParameters | object | Optional | Custom parameters






