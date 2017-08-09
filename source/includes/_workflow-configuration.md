# Workflow Configurations

## Get a Subscription session

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
    }

conn.request("GET", "/api/workflows/configurations/subscriptions/{resourceReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference}",
  "method": "GET",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com"
  },
  "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
    "sessionToken": "7a39758cbf084f65a192ad39378f7e1b"
}
```

For the most simple integration, calling this endpoint will generate a payment session token that can be used for the client-side application (eSuite SDK) to purchase a pre-configured subscription service.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/configurations/subscriptions</span>
</div>

### Query Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`resourceReference` | string | Yes | Reference to the subscription service being purchased.
`returnUrl` | string | No | The URL location the account should be redirected to following a purchase attempt.
`processUpdateURL` | string | No | The endpoint that should be notified of the successful purchase.


## Get a Product session

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
    }

conn.request("GET", "/api/workflows/configurations/products/{resourceReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference}",
  "method": "GET",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com"
  },
  "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
    "sessionToken": "7a39758cbf084f65a192ad39378f7e1b"
}
```

For the most simple integration, calling this endpoint will generate a payment session token that can be used for the client-side application (eSuite SDK) to purchase a pre-configured product.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/configurations/products</span>
</div>

### Query Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`resourceReference` | string | Yes | Reference to the subscription service being purchased.
`returnUrl` | string | No | The URL location the account should be redirected to following a purchase attempt.
`processUpdateURL` | string | No | The endpoint that should be notified of the successful purchase.


## Retrieve a Session Configuration

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
  "url": "https://uat.mppglobal.com/api/workflows/configurations/",
  "method": "GET",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com"
  },
  "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "clientId": 433,
  "clientName": "Prospect Sandbox",
  "clientDefaultTimeZone": "GMT Standard Time",
  "clientDefaultUICulture": "en-GB",
  "createSessionInfo": {
    "bypassConfirmationPage": false,
    "clientUserId": "",
    "currency": "GBP",
    "cancelPaymentOnProcessUpdateFailure": false,
    "function": "AddSubscription",
    "orderItems": [
      {
        "description": "Access to great content on a week by week basis.",
        "grossAmount": 4.99,
        "netAmount": 0.0,
        "taxInfo": {
          "taxAmount": 0.0,
          "category": "Standard",
          "region": {
            "zeroRated": "",
            "country": "GBR",
            "state": "",
            "county": "",
            "city": ""
          }
        }
      }
    ],
    "requiresDelivery": true,
    "paymentMethod": "NotSet",
    "productId": 0,
    "returnUrl": "NotSet",
    "serviceId": 16026,
    "voucherCode": ""
  },
  "newAccount": true,
  "paymentOptions": {
    "cardTypes": [
      {
        "name": "Visa",
        "allowRepeats": true,
        "use3DSecureForAllTransactions": true,
        "use3DSecureOnFirstTransaction": true
      },
      {
        "name": "Mastercard",
        "allowRepeats": false,
        "use3DSecureForAllTransactions": false,
        "use3DSecureOnFirstTransaction": true
      }
    ],
    "directDebitTypes": [
      {
        "name": "Bacs",
        "allowed": false
      },
      {
        "name": "Sepa",
        "allowed": true
      }
    ]
  }
}
```

For the most simple integration, calling this endpoint will generate a payment session token that can be used for the client-side application (eSuite SDK) to purchase a pre-configured product.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/configurations/</span>
</div>

### Response Parameters

Parameter | Type  | Description | 
--------- | ------- | ------- | 
`clientId` | integer | The associated ClientId to your eSuite instance.
`clientName` | string | The name associated to your eSuite instance.
`clientDefaultTimeZone` | string | Friendly name of your configured time zone.
`clientDefaultUICulture` | string | ISO representation of the configured culture.
`createSessionInfo ` | object | Overarching session information object.
`createSessionInfo ` > `bypassConfirmationPage` | Bool | An indication as to whether the payment confirmation page should be bypassed following successful purchase.
`createSessionInfo ` > `clientUserId` | string | The clientUserId of the account.
`createSessionInfo ` > `currency` | string | The currency configured for the workflow.
`createSessionInfo ` > `cancelPaymentOnProcessUpdateFailure` | string | Whether the purchase requires external approval.
`createSessionInfo ` > `function` | string | The type of workflow configured AddSubscription, BuyProduct, etc.
`createSessionInfo` > `orderItems`   | string | Collection of items to be purchased.
`orderItems` > `description` | string | The description of each item.
`orderItems` > `grossAmount` | decimal | The gross amount of each item.
`orderItems` > `netAmount` | decimal | The net amount of each item.
`orderItems` > `taxInfo`   | object | Collection of tax information for the item.
`taxInfo` > `taxAmount` | decimal | The tax amount of each item.
`taxInfo` > `category` | string | The category of tax associated to the item.
`taxInfo` > `region` | object | Collection of tax region information.
`region` > `zeroRated` | bool | Indication whether the item is non-taxable.
`region` > `country` | string | The country tax rate to apply.
`region` > `state` | string | The state tax rate to apply.
`region` > `county` | string |The county tax rate to apply.
`region` > `city` | string | The city tax rate to apply.
`createSessionInfo ` > `requiresDelivery` | bool | Indication as to whether the item will require delivery.
`createSessionInfo ` > `paymentMethod` | string | The default payment method to display.
`createSessionInfo ` > `productId` | string | The associated ProductId of the purchase.
`createSessionInfo ` > `returnUrl` | string | The location the consumer should be returned to following purchase.
`createSessionInfo ` > `serviceId` | string | The associated ServiceId of the purchase.
`createSessionInfo ` > `voucherCode` | string | Any pre-entered voucher codes.
`newAccount` | bool | An indication as to whether the flow is for a new or existing account.
`paymentOptions` | object | A collection of payment options and their configuration.
`paymentOptions` > `cardTypes`  | array[object] | string.
`cardTypes` > `name` | string | Collection of cards types available.
`cardTypes` > `allowRepeats` | bool | An indication as to whether the card type can be used for one-click payments.
`cardTypes` > `use3DSecureForAllTransactions` | bool | An indication as to whether the card type requires 3D Secure.
`cardTypes` > `use3DSecureOnFirstTransaction` | bool | An indication as to whether the card type requires 3D Secure on first use only.
`paymentOptions` > `directDebitTypes` | array[object] | Collection of available Direct Debits.
`directDebitTypes` > `name` | string | Type fo direct debit.
`directDebitTypes` > `allowed` | bool | An indication as to whether it is available.

## Create a Subscription Session

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/workflows/configurations/subscriptions \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"workFlowConfiguration":{"pricing":{"priceId":18535}}}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/workflows/configurations/subscriptions");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"workFlowConfiguration\":{\"pricing\":{\"priceId\":18535}}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/workflows/configurations/subscriptions")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"workFlowConfiguration\":{\"pricing\":{\"priceId\":18535}}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/workflows/configurations/subscriptions")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"workFlowConfiguration\":{\"pricing\":{\"priceId\":18535}}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"workFlowConfiguration\":{\"pricing\":{\"priceId\":18535}}}"
headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/workflows/configurations/subscriptions", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "sessionToken": "7a305eb1d254488f8c0f12f2c086d534"
}
```

If you would like to generate a more specific session for the purpose of purchasing a recurring subscription service, calling this endpoint will allow you to have full control of the information that will be contained. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflows/configurations/subscriptions</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`workflowConfiguration` | string | Yes | 
`workflowConfiguration` > `subscriptionId` | string | No | The configured subscription service identifier|
`workflowConfiguration` > `pricing` | object | Yes | Pricing object for the purchase|
`pricing` > `priceId` | integer | Yes* |The configured price identifier|
`pricing` > `paymentMethod` | string | No |The payment method the customer should be presented by default|
`pricing` > `currency` | string | No |ISO Currency of the purchase e.g. `EUR`|
`pricing` > `priceItems` | array[objects] | Yes* |Collection of individual items being purchased on a dynamic subscription|
`priceItems` > `externalReference` | string | No |Reference from a client system|
`priceItems` > `supplierId` | string | No |Supplier identifier from a client system|
`priceItems` > `price` | decimal | Yes |The price that will be paid for the line item|
`priceItems` > `description` | string | Yes |The description that will be displayed to the account|
`pricing` > `taxInfo` | object | No |Collection of tax information|
`taxInfo` > `zeroRated` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `country` | string | No |Country specific tax rate to use|
`taxInfo` > `state` | string | No |State specific tax rate to use (US Specific)|
`taxInfo` > `county` | string | No |County specific tax rate to use (US Specific)|
`taxInfo` > `city` | string | No |City specific tax rate to use (US Specific)|
`workflowConfiguration` > `processUpdateUrl` | string | No | External endpoint eSuite should notiffy of purchase
`workflowConfiguration` > `cancelOnProcessUpdateFailure` | bool | No | An indication as to whether eSuite should cancel the purchase on failure to recieve a call out response
`workflowConfiguration` > `returnUrl` | string | No | The location to be redirected to upon leaving the purchase flow
`workflowConfiguration` > `clientUserId` | string | No | Unique, non-irrevocable value. Used when eSuite is not primary IdAM
`workflowConfiguration` > `email` | string | No | Accounts email address
`workflowConfiguration` > `voucherCode` | string | No | A pre-configured eSuite voucher code
`workflowConfiguration` > `securityToken` | string | No | Value that is passed in the `ProcessUpdate` callout to allow you to verify it is a legitimate call out
`workflowConfiguration` > `disable3DSecure` | Bool | No | An indication that 3D Secure should be disabled. Defaults to `false`
`workflowConfiguration` > `settlementType` | string | No | An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values
`workflowConfiguration` > `permitUnverifiedAccoutPurchase` | bool | No | Prevent accounts who have not verified their emails from making a purchase
`workflowConfiguration` > `workFlowCustomParameters` | dictionary | No |A collection of custom attributes associated to the configuration
`workFlowCustomParameters` > `parameterName` | string | No |The custom attribute name|
`customAccountParameters` | dictionary | No | A collection of custom attributes associated to the account |
`customAccountParameters` > `parameterName` | string | No |The custom attribute name|
`customOrderParameters` | dictionary | No | A collection of custom attributes associated to the payment |
`customOrderParameters` > `parameterName` | string | No |The custom attribute name|
`customSubscriptionParameters` | string | No |A collection of custom attributes associated to the subscription|
`customSubscriptionParameters` > `parameterName` | string | No |The custom attribute name|
`entitlements` | array[object] | No |A collection of additional entitlements to provide the account on purchase|
`entitlements` > `identifier` | string | No |Identifier for the entitlement being purchased|
`entitlements` > `startDate` | string | No |The date on which the entitlement should be valid from|
`entitlements` > `expiryDate` | string | No |The date at which the account is no longer entitled to the content|


<aside class="info">
This endpoint can only be called using server-side authentication due to the sensetive nature of some information contained in the `POST` request.
</aside>

## Create a Product Session

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/workflows/configurations/products \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"workFlowConfiguration":{"pricing":{"priceId":18535}}}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/workflows/configurations/products");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"workFlowConfiguration\":{\"pricing\":{\"priceId\":18535}}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/workflows/configurations/products")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"workFlowConfiguration\":{\"pricing\":{\"priceId\":18535}}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/workflows/configurations/products")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"workFlowConfiguration\":{\"pricing\":{\"priceId\":18535}}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"workFlowConfiguration\":{\"pricing\":{\"priceId\":18535}}}"
headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/workflows/configurations/products", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "sessionToken": "7a305eb1d254488f8c0f12f2c086d534"
}
```

If you would like to generate a more specific session for the purpose of purchasing a one time product, calling this endpoint will allow you to have full control of the information that will be contained. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflows/configurations/products</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`workflowConfiguration` | string | Yes | 
`workflowConfiguration` > `pricing` | object | Yes | Pricing object for the purchase|
`pricing` > `priceId` | integer | Yes |The configured price identifier|
`pricing` > `paymentMethod` | string | No |The payment method the customer should be presented by default|
`pricing` > `taxInfo` | object | No |Collection of tax information|
`taxInfo` > `zeroRated` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `country` | string | No |Country specific tax rate to use|
`taxInfo` > `state` | string | No |State specific tax rate to use (US Specific)|
`taxInfo` > `county` | string | No |County specific tax rate to use (US Specific)|
`taxInfo` > `city` | string | No |City specific tax rate to use (US Specific)|
`workflowConfiguration` > `processUpdateUrl` | string | No | External endpoint eSuite should notiffy of purchase
`workflowConfiguration` > `cancelOnProcessUpdateFailure` | bool | No | An indication as to whether eSuite should cancel the purchase on failure to recieve a call out response
`workflowConfiguration` > `returnUrl` | string | No | The location to be redirected to upon leaving the purchase flow
`workflowConfiguration` > `clientUserId` | string | No | Unique, non-irrevocable value. Used when eSuite is not primary IdAM
`workflowConfiguration` > `email` | string | No | Accounts email address
`workflowConfiguration` > `voucherCode` | string | No | A pre-configured eSuite voucher code
`workflowConfiguration` > `securityToken` | string | No | Value that is passed in the `ProcessUpdate` callout to allow you to verify it is a legitimate call out
`workflowConfiguration` > `disable3DSecure` | Bool | No | An indication that 3D Secure should be disabled. Defaults to `false`
`workflowConfiguration` > `settlementType` | string | No | An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values
`workflowConfiguration` > `permitUnverifiedAccoutPurchase` | bool | No | Prevent accounts who have not verified their emails from making a purchase
`workflowConfiguration` > `workFlowCustomParameters` | dictionary | No |A collection of custom attributes associated to the configuration
`workFlowCustomParameters` > `parameterName` | string | No |The custom attribute name|
`customAccountParameters` | dictionary | No | A collection of custom attributes associated to the account |
`customAccountParameters` > `parameterName` | string | No |The custom attribute name|
`customOrderParameters` | dictionary | No | A collection of custom attributes associated to the payment |
`customOrderParameters` > `parameterName` | string | No |The custom attribute name|
`entitlements` | array[object] | No |A collection of additional entitlements to provide the account on purchase|
`entitlements` > `identifier` | string | No |Identifier for the entitlement being purchased|
`entitlements` > `startDate` | string | No |The date on which the entitlement should be valid from|
`entitlements` > `expiryDate` | string | No |The date at which the account is no longer entitled to the content|


<aside class="info">
This endpoint can only be called using server-side authentication due to the sensetive nature of some information contained in the `POST` request.
</aside>


## Create a One-off Charge Session

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/workflows/configurations/miscellaneous-charge \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"orderItems":[{"description":"Demonstration Request","priceBreakDown":{"grossAmount":10},"taxInfo":{"category":"Standard"}}],"workFlowConfiguration":{}}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/workflows/configurations/miscellaneous-charge");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"orderItems\":[{\"description\":\"Demonstration Request\",\"priceBreakDown\":{\"grossAmount\":10},\"taxInfo\":{\"category\":\"Standard\"}}],\"workFlowConfiguration\":{}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/workflows/configurations/miscellaneous-charge")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"orderItems\":[{\"description\":\"Demonstration Request\",\"priceBreakDown\":{\"grossAmount\":10},\"taxInfo\":{\"category\":\"Standard\"}}],\"workFlowConfiguration\":{}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/workflows/configurations/miscellaneous-charge")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"orderItems\":[{\"description\":\"Demonstration Request\",\"priceBreakDown\":{\"grossAmount\":10},\"taxInfo\":{\"category\":\"Standard\"}}],\"workFlowConfiguration\":{}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"orderItems\":[{\"description\":\"Demonstration Request\",\"priceBreakDown\":{\"grossAmount\":10},\"taxInfo\":{\"category\":\"Standard\"}}],\"workFlowConfiguration\":{}}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/workflows/configurations/miscellaneous-charge", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "sessionToken": "7a305eb1d254488f8c0f12f2c086d534"
}
```

If you would like to generate a more specific session for a one off charge, calling this endpoint will allow you to have full control of the information that will be contained. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflows/configurations/miscellaneous-charge</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`workflowConfiguration` | string | Yes | 
`workflowConfiguration` > `processUpdateUrl` | string | No | External endpoint eSuite should notiffy of purchase
`workflowConfiguration` > `cancelOnProcessUpdateFailure` | bool | No | An indication as to whether eSuite should cancel the purchase on failure to recieve a call out response
`workflowConfiguration` > `returnUrl` | string | No | The location to be redirected to upon leaving the purchase flow
`workflowConfiguration` > `clientUserId` | string | No | Unique, non-irrevocable value. Used when eSuite is not primary IdAM
`workflowConfiguration` > `email` | string | No | Accounts email address
`workflowConfiguration` > `voucherCode` | string | No | A pre-configured eSuite voucher code
`workflowConfiguration` > `securityToken` | string | No | Value that is passed in the `ProcessUpdate` callout to allow you to verify it is a legitimate call out
`workflowConfiguration` > `disable3DSecure` | Bool | No | An indication that 3D Secure should be disabled. Defaults to `false`
`workflowConfiguration` > `settlementType` | string | No | An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values
`workflowConfiguration` > `permitUnverifiedAccoutPurchase` | bool | No | Prevent accounts who have not verified their emails from making a purchase
`workflowConfiguration` > `workFlowCustomParameters` | dictionary | No |A collection of custom attributes associated to the configuration
`workFlowCustomParameters` > `parameterName` | string | No |The custom attribute name|
`customAccountParameters` | dictionary | No | A collection of custom attributes associated to the account |
`customAccountParameters` > `parameterName` | string | No |The custom attribute name|
`orderItems` | array[object] | No |A collection of additional entitlements to provide the account on purchase|
`orderItems` > `customOrderParameters` | dictionary | No | A collection of custom attributes associated to the payment |
`customOrderParameters` > `parameterName` | string | No |The custom attribute name|
`orderItems` > `description` | object | No |A collection of additional entitlements to provide the account on purchase|
`orderItems` > `orderReference` | object | No |A collection of additional entitlements to provide the account on purchase|
`orderItems` > `comment` | object | No |A collection of additional entitlements to provide the account on purchase|
`orderItems` > `priceBreakdown` | object | No |A collection of additional entitlements to provide the account on purchase|
`priceBreakdown` > grossAmount | decimal | No |A collection of additional entitlements to provide the account on purchase|
`priceBreakdown` > netAmount | decimal | No |A collection of additional entitlements to provide the account on purchase|
`priceBreakdown` > taxAmount | decimal | No |A collection of additional entitlements to provide the account on purchase|
`orderItems` > `taxInfo` | object | Yes |Collection of tax information|
`taxInfo` > `category` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `zeroRated` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `country` | string | No |Country specific tax rate to use|
`taxInfo` > `state` | string | No |State specific tax rate to use (US Specific)|
`taxInfo` > `county` | string | No |County specific tax rate to use (US Specific)|
`taxInfo` > `city` | string | No |City specific tax rate to use (US Specific)|
`orderItems` > `entitlements` | array[object] | No |A collection of additional entitlements to provide the account on purchase|
`entitlements` > `identifier` | string | No |Identifier for the entitlement being purchased|
`entitlements` > `startDate` | string | No |The date on which the entitlement should be valid from|
`entitlements` > `expiryDate` | string | No |The date at which the account is no longer entitled to the content|

<aside class="info">
This endpoint can only be called using server-side authentication due to the sensetive nature of some information contained in the `POST` request.
</aside>


## Create a Credit Purchase Session

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/workflows/configurations/service-credits \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"serviceCredits":{"description":"Credits to buy services","paidCredits":10,"freeCredits":0},"workFlowConfiguration":{}}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/workflows/configurations/service-credits");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"serviceCredits\":{\"description\":\"Credits to buy services\",\"paidCredits\":10,\"freeCredits\":0},\"workFlowConfiguration\":{}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/workflows/configurations/service-credits")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"serviceCredits\":{\"description\":\"Credits to buy services\",\"paidCredits\":10,\"freeCredits\":0},\"workFlowConfiguration\":{}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/workflows/configurations/service-credits")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"serviceCredits\":{\"description\":\"Credits to buy services\",\"paidCredits\":10,\"freeCredits\":0},\"workFlowConfiguration\":{}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"serviceCredits\":{\"description\":\"Credits to buy services\",\"paidCredits\":10,\"freeCredits\":0},\"workFlowConfiguration\":{}}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/workflows/configurations/service-credits", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "sessionToken": "7a305eb1d254488f8c0f12f2c086d534"
}
```

If you would like to generate a more specific session for the purpose of purchasing a recurring subscription service, calling this endpoint will allow you to have full control of the information that will be contained. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflows/configurations/service-credits</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`workflowConfiguration` | string | Yes | 
`workflowConfiguration` > `subscriptionId` | string | No | The configured subscription service identifier|
`workflowConfiguration` > `pricing` | object | Yes | Pricing object for the purchase|
`pricing` > `currency` | string | No |ISO Currency of the purchase e.g. `EUR`|
`pricing` > `taxInfo` | object | No |Collection of tax information|
`taxInfo` > `zeroRated` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `country` | string | No |Country specific tax rate to use|
`taxInfo` > `state` | string | No |State specific tax rate to use (US Specific)|
`taxInfo` > `county` | string | No |County specific tax rate to use (US Specific)|
`taxInfo` > `city` | string | No |City specific tax rate to use (US Specific)|
`serviceCredits`  | object | Yes | Pricing object for the purchase|
`serviceCredits` > `description` | string | No |A description to associate to the purchase|
`serviceCredits` > `paidCredits` | string | No |The amount of credit which the account should pay for|
`serviceCredits` > `freeCredits` | string | No |The amount of free credit which the account should receive|
`workflowConfiguration` > `processUpdateUrl` | string | No | External endpoint eSuite should notiffy of purchase
`workflowConfiguration` > `cancelOnProcessUpdateFailure` | bool | No | An indication as to whether eSuite should cancel the purchase on failure to recieve a call out response
`workflowConfiguration` > `returnUrl` | string | No | The location to be redirected to upon leaving the purchase flow
`workflowConfiguration` > `clientUserId` | string | No | Unique, non-irrevocable value. Used when eSuite is not primary IdAM
`workflowConfiguration` > `email` | string | No | Accounts email address
`workflowConfiguration` > `voucherCode` | string | No | A pre-configured eSuite voucher code
`workflowConfiguration` > `securityToken` | string | No | Value that is passed in the `ProcessUpdate` callout to allow you to verify it is a legitimate call out
`workflowConfiguration` > `disable3DSecure` | Bool | No | An indication that 3D Secure should be disabled. Defaults to `false`
`workflowConfiguration` > `settlementType` | string | No | An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values
`workflowConfiguration` > `permitUnverifiedAccoutPurchase` | bool | No | Prevent accounts who have not verified their emails from making a purchase
`workflowConfiguration` > `workFlowCustomParameters` | dictionary | No |A collection of custom attributes associated to the configuration
`workFlowCustomParameters` > `parameterName` | string | No |The custom attribute name|
`customAccountParameters` | dictionary | No | A collection of custom attributes associated to the account |
`customAccountParameters` > `parameterName` | string | No |The custom attribute name|
`customOrderParameters` | dictionary | No | A collection of custom attributes associated to the payment |
`customOrderParameters` > `parameterName` | string | No |The custom attribute name|



<aside class="info">
This endpoint can only be called using server-side authentication due to the sensetive nature of some information contained in the `POST` request.
</aside>


































