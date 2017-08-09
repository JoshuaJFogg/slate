# Workflow Purchases

## Standard Subscription Purchase

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
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflow/purchases/subscriptions",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "amountCharged": 10
  "currency": "GBP",
  "paymentType": "SEPA",
  "subscriptionStatus": "Active",
  "renewalDay": 1,
  "renewalDayOffset": 0,
  "startDate": "2017-01-01T00:00:00",
  "renewalDate": "2018-01-01T00:00:00",
  "orderReference": 12548,
  "subscriptionId": 4555888,
  "subscriptionPriceId": 568845,
  "subscriptionReference": "458845",
  "resourceReference": "001DFTBDC03",
  "asynchronousProcessingParameters": {
    "redirectLocation": "https://my-payments.com/?token=34089573094093784"
  }
}
```

For the completion of standard payment options, making the following `POST` request will purchase the subscription service configured within the initial configuration request. A simple payment type is `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/purchases/subscriptions</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`voucherCode` | string | No | eSuite generated voucher code that has been provided during the flow |
`cvv` | string | No |If the purchase is being made using an non-authorised card, this parameter can be passed in to enable authorisation to take place |
`renewalDay` | integer | No | The date of the month the subscription should be renewed on, specifically for monthly or annual subscriptions|
`renewalDayOffset` | string | No |The number of days before or after the renewal date. This can be positive or negative|
`startDate` | string | No |The date at which the subscription should be purchased and started |
`paymentMethod` | string | No |The type of payment method the account has selected. Standard methods are `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`. Other methods are available|
`entitlements` | array[object] | No |A collection of additional entitlements to provide the account on purchase|
`entitlements` > `identifier` | string | No |Identifier for the entitlement being purchased|
`entitlements` > `startDate` | string | No |The date on which the entitlement should be valid from|
`entitlements` > `expiryDate` | string | No |The date at which the account is no longer entitled to the content|
`customOrderParameters` | dictionary | No | A collection of custom attributes associated to the payment |
`customOrderParameters` > `parameterName` | string | No |The custom attribute name|
`customSubscriptionParameters` | string | No |A collection of custom attributes associated to the subscription|
`customSubscriptionParameters` > `parameterName` | string | No |The custom attribute name|
`taxInfo` | object | No |Collection of tax information|
`taxInfo` > `zeroRated` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `country` | string | No |Country specific tax rate to use|
`taxInfo` > `state` | string | No |State specific tax rate to use (US Specific)|
`taxInfo` > `county` | string | No |County specific tax rate to use (US Specific)|
`taxInfo` > `city` | string | No |City specific tax rate to use (US Specific)|
`groupSubscriptionInfo` | string | No | Account Group information|
`groupSubscriptionInfo` > `groupToken` | string | No |The associated group account identifier|
`groupSubscriptionInfo` > `subscriberAccounts` | array[object] | No |A collection of accounts that should be assigned to the subscription|
`subscriberAccounts` > `clientUserId` | string | No |The clientUserId of the account that should be assigned|
`subscriberAccounts` > `emailAddress` | string | No |The email address of the account that should be assigned|
`subscriberAccounts` > `taxInfo` | object | No |Collection of tax information for each account|
`taxInfo` > `zeroRated` | string | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `country` | string | No |Country specific tax rate to use|
`taxInfo` > `state` | string | No |State specific tax rate to use (US Specific)|
`taxInfo` > `county` | string | No |County specific tax rate to use (US Specific)|
`taxInfo` > `city` | string | No |City specific tax rate to use (US Specific)|
`asynchronousInitiationParameters` | string | No |Parameter set provided if you would like to trigger an advanced payment type|
`asynchronousInitiationParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|

## Standard Product Purchase

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflow/purchases/products",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "orderId" : ""
  "asynchronousProcessingParameters": {
     "redirectLocation": "https://my-payments.com/?token=34089573094093784"
  }
}
```

For the completion of standard payment options, making the following `POST` request will purchase the product configured within the initial configuration request. A simple payment type is `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/purchases/products</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`productDetails` | object | No |A collection of additional entitlements to provide the account on purchase|
`productDetails` > `description` | string | No |If the product description configured in eSuite should be overridden|
`productDetails` > `referenceNumber` | string | No |Client reference for the purchase|
`productDetails` > `comments` | string | No |Any additional comments on the purchase|
`voucherCode` | string | No | eSuite generated voucher code that has been provided during the flow |
`settlementType` | string | No | An indication as to whether the purchase should be completed immediately or delayed |
`cvv` | string | No |If the purchase is being made using an non-authorised card, this parameter can be passed in to enable authorisation to take place |
`paymentMethod` | string | No |The type of payment method the account has selected. Standard methods are `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`. Other methods are available|
`entitlementParameters` | array[object] | No |A collection of additional entitlements to provide the account on purchase|
`entitlementParameters` > `identifier` | string | No |Identifier for the entitlement being purchased|
`entitlementParameters` > `startDate` | string | No |The date on which the entitlement should be valid from|
`entitlementParameters` > `expiryDate` | string | No |The date at which the account is no longer entitled to the content|
`orderParameters` | dictionary | No | A collection of custom attributes associated to the payment |
`orderParameters` > `parameterName` | string | No |The custom attribute name|
`taxInfo` | object | No |Collection of tax information|
`taxInfo` > `zeroRated` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `country` | string | No |Country specific tax rate to use|
`taxInfo` > `state` | string | No |State specific tax rate to use (US Specific)|
`taxInfo` > `county` | string | No |County specific tax rate to use (US Specific)|
`taxInfo` > `city` | string | No |City specific tax rate to use (US Specific)|
`asynchronousInitiationParameters` | string | No |Parameter set provided if you would like to trigger an advanced payment type|
`asynchronousInitiationParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|


## Standard One-off Charge

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflow/purchases/miscellaneous-charge",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "basketNumber": "433M098765",
  "orders": [
    {
      "orderId": 154874,
      "externalOrderReference": "134Order"
    }
  ],
  "asynchronousProcessingParameters": {
     "redirectLocation": "https://my-payments.com/?token=34089573094093784"
  }
}
```

For the completion of standard payment options, making the following `POST` request will purchase the product configured within the initial configuration request. A simple payment type is `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/purchases/miscellaneous-charge</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`paymentMethod` | string | No |The payment method the account has selected to pay with if it differs from the initial configuration|
`cvv` | string | No |Security code of a card if the payment method is set to `creditDebitCard`|
`voucherCode` | string | No |A voucher code provided by the account during the workflow|
`orderItems` | array[object] | No |A collection of additional entitlements to provide the account on purchase|
`orderItems` > `customOrderParameters` | dictionary | No | A collection of custom attributes associated to the payment |
`customOrderParameters` > `parameterName` | string | No |The custom attribute name|
`orderItems` > `description` | object | No |A collection of additional entitlements to provide the account on purchase|
`orderItems` > `orderReference` | object | No |A collection of additional entitlements to provide the account on purchase|
`orderItems` > `comment` | object | No |A collection of additional entitlements to provide the account on purchase|
`orderItems` > `taxInfo` | object | Yes |Collection of tax information|
`taxInfo` > `category` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `zeroRated` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `country` | string | No |Country specific tax rate to use|
`taxInfo` > `state` | string | No |State specific tax rate to use (US Specific)|
`taxInfo` > `county` | string | No |County specific tax rate to use (US Specific)|
`taxInfo` > `city` | string | No |City specific tax rate to use (US Specific)|
`orderItems` > `customOrderParameters` | dictionary | No | A collection of custom attributes associated to the payment |
`customOrderParameters` > `parameterName` | string | No |The custom attribute name|
`orderItems` > `entitlements` | array[object] | No |A collection of additional entitlements to provide the account on purchase|
`entitlements` > `identifier` | string | No |Identifier for the entitlement being purchased|
`entitlements` > `startDate` | string | No |The date on which the entitlement should be valid from|
`entitlements` > `expiryDate` | string | No |The date at which the account is no longer entitled to the content|
`asynchronousInitiationParameters` | string | No |Parameter set provided if you would like to trigger an advanced payment type|
`asynchronousInitiationParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|


## Standard Credits Purchase

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflow/purchases/service-credits",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "basketNumber": "433M098765",
  "orders": [
    {
      "orderId": 154874,
      "externalOrderReference": "134Order"
    }
  ],
  "asynchronousProcessingParameters": {
     "redirectLocation": "https://my-payments.com/?token=34089573094093784"
  }
}
```

For the completion of standard payment options, making the following `POST` request will purchase the product configured within the initial configuration request. A simple payment type is `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/purchases/service-credits</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`paymentMethod` | string | No |The payment method the account has selected to pay with if it differs from the initial configuration|
`cvv` | string | No |Security code of a card if the payment method is set to `creditDebitCard`|
`voucherCode` | string | No |A voucher code provided by the account during the workflow|
`asynchronousInitiationParameters` | string | No |Parameter set provided if you would like to trigger an advanced payment type|
`asynchronousInitiationParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|


## Alternative Subscription Purchase

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflow/purchases/subscriptions",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"asynchronousProcessingParameters\":{\"paymentConfirmationToken\":\"12SDE45GVFT5TGFWSY6\"}}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "amountCharged": 10
  "currency": "GBP",
  "paymentType": "PayPal",
  "subscriptionStatus": "Active",
  "renewalDay": 1,
  "renewalDayOffset": 0,
  "startDate": "2017-01-01T00:00:00",
  "renewalDate": "2018-01-01T00:00:00",
  "orderReference": 12548,
  "subscriptionId": 4555888,
  "subscriptionPriceId": 568845,
  "subscriptionReference": "458845",
  "resourceReference": "001DFTBDC03",
  "asynchronousProcessingParameters": null
}
```

For the completion of alternative subscription options, making the following `PATCH` request will purchase the subscription service configured within the initial configuration request. A alternative payment type is `PayPal` `Alipay`, and any other which requires a redirect.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/purchases/subscription</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`asynchronousProcessingParameters` | string | No |Parameter set provided if you would like to complete an advanced payment type|
`asynchronousProcessingParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|

## Alternative Product Purchase

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflow/purchases/products",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"asynchronousProcessingParameters\":{\"paymentConfirmationToken\":\"12SDE45GVFT5TGFWSY6\"}}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "orderId" : "154847"
  "asynchronousProcessingParameters": null
}
```

For the completion of alternative product purchase options, making the following `PATCH` request will purchase the subscription service configured within the initial configuration request. A alternative payment type is `PayPal` `Alipay`, and any other which requires a redirect.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/purchases/products</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`asynchronousProcessingParameters` | string | No |Parameter set provided if you would like to complete an advanced payment type|
`asynchronousProcessingParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|

## Alternative One-off Charge

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflow/purchases/miscellaneous-charge",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"asynchronousProcessingParameters\":{\"paymentConfirmationToken\":\"12SDE45GVFT5TGFWSY6\"}}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "basketNumber": "433M098765",
  "orders": [
    {
      "orderId": 154874,
      "externalOrderReference": "134Order"
    }
  ],
  "asynchronousProcessingParameters": null
}
```

For the completion of alternative one-off charge, making the following `PATCH` request will purchase the subscription service configured within the initial configuration request. A alternative payment type is `PayPal` `Alipay`, and any other which requires a redirect.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/purchases/miscellaneous-charge</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`asynchronousProcessingParameters` | string | No |Parameter set provided if you would like to complete an advanced payment type|
`asynchronousProcessingParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|

## Alternative Credits Purchase

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflow/purchases/service-credits",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"asynchronousProcessingParameters\":{\"paymentConfirmationToken\":\"12SDE45GVFT5TGFWSY6\"}}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
      "orderId": 154874,
      "asynchronousProcessingParameters": null
}
```

For the completion of alternative credits purchase, making the following `PATCH` request will purchase the subscription service configured within the initial configuration request. A alternative payment type is `PayPal` `Alipay`, and any other which requires a redirect.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/purchases/service-credits</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`asynchronousProcessingParameters` | string | No |Parameter set provided if you would like to complete an advanced payment type|
`asynchronousProcessingParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|









