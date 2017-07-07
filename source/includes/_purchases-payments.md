# Purchases and Payments

## Specfic name of the endpoint e.g. Create Account

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
name | string | Yes/No | What does the parameter represent?

<aside class="success">
Anything that needs to be called out to an integrator. Standard bootstrap classnames are available here: success, warning, error, info
</aside>

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

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/service-credits</span>
</div>

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

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/service-credits</span>
</div>

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
credit | array[object] | Optional | Credit
credit > currency | string | Optional | Currency
credit > amount | number | Optional | Amount
creditPurchases | integer | Optional | Credit purchases

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

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/orders/{orderId}/complete</span>
</div>

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

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/orders</span>
</div>

### PATCH Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
asynchronousProcessingParameters | object | Optional | Asybchronous processing parameters

