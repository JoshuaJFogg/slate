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

 |   | | 
--------- | ------- | ------- |  
`voucherCode` <br />eSuite generated voucher code that has been provided during the flow | <span class="string">string</span> |  | 
`cvv` <br />If the purchase is being made using an non-authorised card, this parameter can be passed in to enable authorisation to take place | <span class="string">string</span> |  |
`renewalDay` <br />The date of the month the subscription should be renewed on, specifically for monthly or annual subscriptions| <span class="integer">integer</span> |  | 
`renewalDayOffset` <br />The number of days before or after the renewal date. This can be positive or negative| <span class="string">string</span> |  |
`startDate` <br />The date at which the subscription should be purchased and started | <span class="string">string</span> |  |
`paymentMethod` <br />The type of payment method the account has selected. Standard methods are `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`. Other methods are available| <span class="string">string</span> |  |
`entitlements` <br />A collection of additional entitlements to provide the account on purchase| <span class="array">array[object]</span> |  |
`entitlements` > `identifier` <br />Identifier for the entitlement being purchased| <span class="string">string</span> |  |
`entitlements` > `startDate` <br />The date on which the entitlement should be valid from| <span class="string">string</span> |  |
`entitlements` > `expiryDate` <br />The date at which the account is no longer entitled to the content| <span class="string">string</span> |  |
`customOrderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary*</span> |  | 
`customOrderParameters` > `parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customSubscriptionParameters` <br />A collection of custom attributes associated to the subscription| <span class="string">string</span> |  |
`customSubscriptionParameters` > `parameterName`<br /> The custom attribute name| <span class="string">string</span> |  |
`taxInfo` <br />Collection of tax information| <span class="object">object</span> |  |
`taxInfo` > `zeroRated` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo` > `country` <br />Country specific tax rate to use| <span class="string">string</span> |  |
`taxInfo` > `state` <br />State specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo` > `county` <br />County specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo` > `city` <br />City specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`groupSubscriptionInfo` <br />Account Group information| <span class="string">string</span> |  | 
`groupSubscriptionInfo` > `groupToken` <br />The associated group account identifier| <span class="string">string</span> |  |
`groupSubscriptionInfo` > `subscriberAccounts` <br />A collection of accounts that should be assigned to the subscription| <span class="array">array[object]</span> |  |
`subscriberAccounts` > `clientUserId` <br />The clientUserId of the account that should be assigned| <span class="string">string</span> |  |
`subscriberAccounts` > `emailAddress` <br />The email address of the account that should be assigned| <span class="string">string</span> |  |
`subscriberAccounts` > `taxInfo` <br />Collection of tax information for each account| <span class="object">object</span> |  |
`taxInfo` > `zeroRated` <br />Indication as to whether the purchase is tax exempt| <span class="string">string</span> |  |
`taxInfo` > `country` <br />Country specific tax rate to use| <span class="string">string</span> |  |
`taxInfo` > `state` <br />State specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo` > `county` <br />County specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo` > `city` <br />City specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`asynchronousInitiationParameters` <br />Parameter set provided if you would like to trigger an advanced payment type| <span class="string">string</span> |  |
`asynchronousInitiationParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |

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

 |   | | 
--------- | ------- | ------- | 
`productDetails` <br />A collection of additional entitlements to provide the account on purchase| <span class="object">object</span> |  |
`productDetails` > `description` <br />If the product description configured in eSuite should be overridden| <span class="string">string</span> |  |
`productDetails` > `referenceNumber` <br />Client reference for the purchase| <span class="string">string</span> |  |
`productDetails` > `comments` <br />Any additional comments on the purchase| <span class="string">string</span> |  |
`voucherCode` <br />eSuite generated voucher code that has been provided during the flow | <span class="string">string</span> |  | 
`settlementType` <br />An indication as to whether the purchase should be completed immediately or delayed | <span class="string">string</span> |  | 
`cvv` <br />If the purchase is being made using an non-authorised card, this parameter can be passed in to enable authorisation to take place | <span class="string">string</span> |  |
`paymentMethod` <br />The type of payment method the account has selected. Standard methods are `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`. Other methods are available| <span class="string">string</span> |  |
`entitlementParameters` <br />A collection of additional entitlements to provide the account on purchase| <span class="array">array[object]</span> |  |
`entitlementParameters` > `identifier` <br />Identifier for the entitlement being purchased| <span class="string">string</span> |  |
`entitlementParameters` > `startDate` <br />The date on which the entitlement should be valid from| <span class="string">string</span> |  |
`entitlementParameters` > `expiryDate` <br />The date at which the account is no longer entitled to the content| <span class="string">string</span> |  |
`orderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary*</span> |  | 
`orderParameters` > `parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`taxInfo` <br />Collection of tax information| <span class="object">object</span> |  |
`taxInfo` > `zeroRated` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo` > `country` <br />Country specific tax rate to use| <span class="string">string</span> |  |
`taxInfo` > `state` <br />State specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo` > `county` <br />County specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo` > `city` <br />City specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`asynchronousInitiationParameters` <br />Parameter set provided if you would like to trigger an advanced payment type| <span class="string">string</span> |  |
`asynchronousInitiationParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |


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

 |   |  | 
--------- | ------- | ------- | 
`paymentMethod` <br />The payment method the account has selected to pay with if it differs from the initial configuration| <span class="string">string</span> |  |
`cvv` <br />Security code of a card if the payment method is set to `creditDebitCard`| <span class="string">string</span> |  |
`voucherCode` <br />A voucher code provided by the account during the workflow| <span class="string">string</span> |  |
`orderItems` <br />A collection of additional entitlements to provide the account on purchase| <span class="array">array[object]</span> |  |
`orderItems` > `customOrderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary*</span> |  | 
`customOrderParameters` > `parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`orderItems` > `description` <br />A collection of additional entitlements to provide the account on purchase| <span class="object">object</span> |  |
`orderItems` > `orderReference` <br />A collection of additional entitlements to provide the account on purchase| <span class="object">object</span> |  |
`orderItems` > `comment` <br />A collection of additional entitlements to provide the account on purchase| <span class="object">object</span> |  |
`orderItems` > `taxInfo` <br />Collection of tax information| <span class="object">object</span> | <span class="required">Required</span> |
`taxInfo` > `category` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo` > `zeroRated` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo` > `country` <br />Country specific tax rate to use| <span class="string">string</span> |  |
`taxInfo` > `state` <br />State specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo` > `county` <br />County specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo` > `city` <br />City specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`orderItems` > `customOrderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary*</span> |  | 
`customOrderParameters` > `parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`orderItems` > `entitlements` <br />A collection of additional entitlements to provide the account on purchase| <span class="array">array[object]</span> |  |
`entitlements` > `identifier` <br />Identifier for the entitlement being purchased| <span class="string">string</span> |  |
`entitlements` > `startDate` <br />The date on which the entitlement should be valid from| <span class="string">string</span> |  |
`entitlements` > `expiryDate` <br />The date at which the account is no longer entitled to the content| <span class="string">string</span> |  |
`asynchronousInitiationParameters` <br />Parameter set provided if you would like to trigger an advanced payment type| <span class="string">string</span> |  |
`asynchronousInitiationParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |


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

 |   | |  
--------- | ------- | ------- | 
`paymentMethod` <br />The payment method the account has selected to pay with if it differs from the initial configuration| <span class="string">string</span> |  |
`cvv` <br />Security code of a card if the payment method is set to `creditDebitCard`| <span class="string">string</span> |  |
`voucherCode` <br />A voucher code provided by the account during the workflow| <span class="string">string</span> |  |
`asynchronousInitiationParameters` <br />Parameter set provided if you would like to trigger an advanced payment type| <span class="string">string</span> |  |
`asynchronousInitiationParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |

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

 |   | |  
--------- | ------- | ------- | 
`asynchronousProcessingParameters` <br />Parameter set provided if you would like to complete an advanced payment type| <span class="string">string</span> |  |
`asynchronousProcessingParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |

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

 |   | |  
--------- | ------- | ------- | 
`asynchronousProcessingParameters` <br />Parameter set provided if you would like to complete an advanced payment type| <span class="string">string</span> |  |
`asynchronousProcessingParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |

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

 |   | | 
--------- | ------- | ------- | 
`asynchronousProcessingParameters` <br />Parameter set provided if you would like to complete an advanced payment type| <span class="string">string</span> |  |
`asynchronousProcessingParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |

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

 |   | | 
--------- | ------- | ------- | 
`asynchronousProcessingParameters` <br />Parameter set provided if you would like to complete an advanced payment type| <span class="string">string</span> |  |
`asynchronousProcessingParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |









