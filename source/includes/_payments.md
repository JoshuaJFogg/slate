# Payments

## Make a Payment

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

`POST http://uat.mppglobal.com/api/accounts/{accountId}/orders`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
settlementType | string | Optional | Gets or sets the SettlementType
pricing | object | Optional | {MppGlobal.Api.Rest.Dtos.v1.Pricing} Price for create session
pricing > priceId | integer | Optional | Gets or sets the price id
pricing > paymentMethod | string | Optional | Gets or sets the payment method
pricing > currency | string | Optional | Gets or sets the currency
pricing > price | number | Optional | Gets or sets the price
pricing > taxInfo | object | Optional | {MppGlobal.Api.Rest.Dtos.v1.TaxRegionInfo} Tax region info class
pricing > taxInfo > zeroRated | string | Optional | Gets or sets the zero rated
pricing > taxInfo > country | string | Optional | Gets or sets the country
pricing > taxInfo > state | string | Optional | Gets or sets the state
pricing > taxInfo > county | string | Optional | Gets or sets the county
pricing > taxInfo > city | string | Optional | Gets or sets the city
pricing > priceItems | string | Optional | Gets or sets the price items
pricing > priceItems > externalReference | string | Optional | Gets or sets the external reference
pricing > priceItems > supplierId | integer | Optional | Gets or sets the supplier id
pricing > priceItems > price | number | Optional | Gets or sets the price
pricing > priceItems > description | string | Optional | Gets or sets the description
cvv | string | Optional | Gets or sets the cv2 number
voucherCode | string | Optional | Gets or sets the promotion code
orderItems | string | Optional | Gets or sets the order items
orderItems > priceBreakDown | object | Optional | Order price breakdown
orderItems > priceBreakDown > grossAmount | number | Optional | Gross amount
orderItems > priceBreakDown > netAmount | number | Optional | Net amount
orderItems > priceBreakDown > taxAmount | number | Optional | Tax amount
orderItems > orderReference | string | Optional | Gets or sets the order reference
orderItems > description | string | Optional | Gets or sets the description
orderItems > comments | string | Optional | Gets or sets the comments
orderItems > customOrderParameters | object | Optional | Gets or sets the custom order parameters
orderItems > entitlements | string | Optional | Gets or sets the entitlement parameters
orderItems > entitlements > identifier | string | Optional | Gets or sets the identifier of the entitlement
orderItems > entitlements > startDate | string | Optional | Gets or sets the create date of the entitlement
orderItems > entitlements > expiryDate | string | Optional | Gets or sets the expire date of the entitlement
orderItems > taxInfo | object | Optional | Tax region info class
orderItems > taxInfo > zeroRated | string | Optional | Gets or sets the zero rated
orderItems > taxInfo > country | string | Optional | Gets or sets the country
orderItems > taxInfo > state | string | Optional | Gets or sets the state
orderItems > taxInfo > county | string | Optional | Gets or sets the county
orderItems > taxInfo > city | string | Optional | Gets or sets the city
asynchronousProcessingParameters | object | Optional | Asynchronous Processing Parameters






## Refund a Payment

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

`POST http://uat.mppglobal.com/api/orders/{orderId}/refund`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
amount | number | Yes | Gets or sets the amount
triggerBackOfficeEmail | boolean | Optional | Gets or sets the trigger back office email
reason | string | Optional | Gets or sets the refund reason
reasonCode | string | Optional | Gets or sets the refund reason code






## Cancel a Payment

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

`PATCH http://uat.mppglobal.com/api/orders/{orderId}/cancellations`

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
reason | string | Optional | The reason for the edit
emailNotification | boolean | Optional | EmailNotification
type | string | Optional | Type







## Purchase Service Credits

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

`POST http://uat.mppglobal.com/api/accounts/{accountId}/service-credits`

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
paymentMethod | string | Optional | Gets or sets the payment method
currency | string | Optional | Currency
cvv | string | Optional | Gets or sets the cv2 number
voucherCode | string | Optional | Gets or sets the voucher code
paidCredits | number | Optional | Gets or sets the paid credits
freeCredits | number | Optional | Gets or sets the free credits
asynchronousProcessingParameters | object | Optional | Asynchronous Processing Parameters







## Retrieve Service Credits Balance

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

`GET http://uat.mppglobal.com/api/accounts/{accountId}/service-credits`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
credit | array[object] | Optional | Credit
credit > currency | string | Optional | Currency
credit > amount | number | Optional | Amount
creditPurchases | integer | Optional | Credit purchases






## Get Payment History

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

`GET http://uat.mppglobal.com/api/accounts/{accountId}/orders`

### Query string

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
createDateFrom | string | Required | 1 validations
createDateTo | string | Required | 1 validations
rowsPerPage | integer | Required | 1 validations
currentPage | integer | Required | 1 validations
isAscending | boolean | Optional | 






## Complete Asynchronous Service Credits Payment

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

`PATCH http://uat.mppglobal.com/api/orders/{orderId}/complete`

### PATCH Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
reason | string | Optional | The reason for the edit
amount | number | Optional | The new amount to be passed in






## Complete Asynchronous Payment

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

`PATCH http://uat.mppglobal.com/api/accounts/{accountId}/orders`

### PATCH Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
asynchronousProcessingParameters | object | Optional | Asybchronous processing parameters






