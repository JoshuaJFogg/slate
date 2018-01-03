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
    'x-version': '9.0.0'
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

 |  |  |  
--------- | ------- | ------- | 
`resourceReference` <br /> Reference to the subscription service being purchased.| <span class="string">string<span> | <span class="required">Required</span>
`returnUrl` <br /> The URL location the account should be redirected to following a purchase attempt.| <span class="string">string<span> |  
`processUpdateURL` <br /> The endpoint that should be notified of the successful purchase.| <span class="string">string<span> |  


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
    'x-version': '9.0.0'
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

 |  |  |  
--------- | ------- | ------- | 
`resourceReference` <br />Reference to the subscription service being purchased. | <span class="string">string</span> | <span class="required">Required</span> | 
`returnUrl` <br />The URL location the account should be redirected to following a purchase attempt.| <span class="string">string</span> |  | 
`processUpdateURL` <br />The endpoint that should be notified of the successful purchase.| <span class="string">string</span> |  | 


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

For the most simple integration, calling this endpoint will generate a payment session token that can be used for the client-side application (eSuite SDK) to purchase a pre-configured product. You are required to provide a valid `x-sessionId` in order for this API request to be successful.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/configurations/</span>
</div>

### Response Parameters

 |   |  
--------- | ------- |  
`clientId` <br />The associated ClientId to your eSuite instance.| <span class="integer">integer</span> | 
`clientName` <br />The name associated to your eSuite instance.| <span class="string">string</span> | 
`clientDefaultTimeZone` <br />Friendly name of your configured time zone.| <span class="string">string</span> | 
`clientDefaultUICulture` <br />ISO representation of the configured culture.| <span class="string"><span class="string">string</span> | 
`createSessionInfo ` <br />Overarching session information object.| <span class="object">object</span> | 
`createSessionInfo  \ bypassConfirmationPage` <br />An indication as to whether the payment confirmation page should be bypassed following successful purchase.| <span class="bool">bool</span> | 
`createSessionInfo  \ clientUserId` <br />The clientUserId of the account.| <span class="string">string</span> | 
`createSessionInfo  \ currency` <br />The currency configured for the workflow.| <span class="string">string</span> | 
`createSessionInfo  \ cancelPaymentOnProcessUpdateFailure` <br />Whether the purchase requires external approval.| <span class="string">string</span> | 
`createSessionInfo  \ function` <br />The type of workflow configured AddSubscription, BuyProduct, etc.| <span class="string">string</span> | 
`createSessionInfo \ orderItems`   <br />Collection of items to be purchased.| <span class="string">string</span> | 
`orderItems \ description` <br />The description of each item.| <span class="string">string</span> | 
`orderItems \ grossAmount` <br />The gross amount of each item.| <span class="decimal">decimal</span> | 
`orderItems \ netAmount` <br />The net amount of each item.| <span class="decimal">decimal</span> | 
`orderItems \ taxInfo`   <br />Collection of tax information for the item.| <span class="object">object</span> | 
`taxInfo \ taxAmount` <br />The tax amount of each item.| <span class="decimal">decimal</span> | 
`taxInfo \ category` <br />The category of tax associated to the item.| <span class="string">string</span> | 
`taxInfo \ region` <br />Collection of tax region information.| <span class="object">object</span> | 
`region \ zeroRated` <br />Indication whether the item is non-taxable.| <span class="bool">bool</span> | 
`region \ country` <br />The country tax rate to apply.| <span class="string">string</span> | 
`region \ state` <br />The state tax rate to apply.| <span class="string">string</span> | 
`region \ county` <br />The county tax rate to apply.| <span class="string">string</span> |
`region \ city` <br />The city tax rate to apply.| <span class="string">string</span> | 
`createSessionInfo  \ requiresDelivery` <br />Indication as to whether the item will require delivery.| <span class="bool">bool</span> | 
`createSessionInfo  \ paymentMethod` <br />The default payment method to display.| <span class="string">string</span> | 
`createSessionInfo  \ productId` <br />The associated ProductId of the purchase.| <span class="string">string</span> | 
`createSessionInfo  \ returnUrl` <br />The location the consumer should be returned to following purchase.| <span class="string">string</span></span> | 
`createSessionInfo  \ serviceId` <br />The associated ServiceId of the purchase.| <span class="string">string</span> | 
`createSessionInfo  \ voucherCode` <br />Any pre-entered voucher codes.| <span class="string">string</span> | 
`newAccount` <br />An indication as to whether the flow is for a new or existing account.| <span class="bool">bool</span> | 
`paymentOptions` <br />A collection of payment options and their configuration.| <span class="object">object</span> | 
`paymentOptions \ cardTypes` <br />Object detailing the specifics of the available card types  | <span class="array">array[object]</span> | 
`cardTypes \ name` <br />Collection of cards types available.| <span class="string">string</span> | 
`cardTypes \ allowRepeats` <br />An indication as to whether the card type can be used for one-click payments.| <span class="bool">bool</span> | 
`cardTypes \ use3DSecureForAllTransactions` <br />An indication as to whether the card type requires 3D Secure.| <span class="bool">bool</span> | 
`cardTypes \ use3DSecureOnFirstTransaction` <br />An indication as to whether the card type requires 3D Secure on first use only.| <span class="bool">bool</span> | 
`paymentOptions \ directDebitTypes` <br />Collection of available Direct Debits.| <span class="array">array[object]</span> | 
`directDebitTypes \ name` <br />Type fo direct debit.| <span class="string">string</span> | 
`directDebitTypes \ allowed` <br />An indication as to whether it is available.| <span class="bool">bool</span> | 

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
    'x-version': '9.0.0',
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
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflows/configurations/subscriptions</span>
</div>

### Parameters

 |  |  |
--------- | ------- | ------- | 
`workflowConfiguration` | <span class="string">string</span> | <span class="required">Required</span> | 
`workflowConfiguration \ subscriptionId` <br />The configured subscription service identifier| <span class="string">string</span> |  | 
`workflowConfiguration \ pricing` <br />Pricing object for the purchase| <span class="object">object</span> | <span class="required">Required</span> | 
`pricing \ priceId` <br />The configured price identifier| <span class="integer">integer</span> | <span class="required">Required</span> |
`pricing \ paymentMethod` <br />The payment method the customer should be presented by default| <span class="string">string</span> |  |
`pricing \ currency` <br />ISO Currency of the purchase e.g. `EUR`| <span class="string">string</span> |  |
`pricing \ priceItems` <br />Collection of individual items being purchased on a dynamic subscription| <span class="array">array[objects]</span> |  |
`priceItems \ externalReference` <br />Reference from a client system| <span class="string">string</span> |  |
`priceItems \ supplierId` <br />Supplier identifier from a client system| <span class="string">string</span> |  |
`priceItems \ price` <br />The price that will be paid for the line item| <span class="decimal">decimal</span> | <span class="required">Required</span> |
`priceItems \ description` <br />The description that will be displayed to the account| <span class="string">string</span> | <span class="required">Required</span> |
`pricing \ taxInfo` <br />Collection of tax information| <span class="object">object</span> |  |
`taxInfo \ zeroRated` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo \ country` <br />Country specific tax rate to use| <span class="string">string</span> |  |
`taxInfo \ state` <br />State specific tax rate to use (US Specific)|<span class="string">string</span> |  |
`taxInfo \ county` <br />County specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo \ city` <br />City specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`workflowConfiguration \ processUpdateUrl` <br />External endpoint eSuite should notiffy of purchase| <span class="string">string</span> |  | 
`workflowConfiguration \ cancelOnProcessUpdateFailure` <br />An indication as to whether eSuite should cancel the purchase on failure to recieve a call out response| <span class="bool">bool</span> |  | 
`workflowConfiguration \ returnUrl` <br />The location to be redirected to upon leaving the purchase flow| <span class="string">string</span> |  | 
`workflowConfiguration \ clientUserId` <br />Unique, non-irrevocable value. Used when eSuite is not primary IdAM| <span class="string">string</span> |  | 
`workflowConfiguration \ email` <br />Accounts email address| <span class="string">string</span> |  | 
`workflowConfiguration \ voucherCode` <br />A pre-configured eSuite voucher code| <span class="string">string</span> |  | 
`workflowConfiguration \ securityToken` <br />Value that is passed in the `ProcessUpdate` callout to allow you to verify it is a legitimate call out| <span class="string">string</span> |  | 
`workflowConfiguration \ disable3DSecure` <br />An indication that 3D Secure should be disabled. Defaults to `false`| <span class="bool">bool</span> |  | 
`workflowConfiguration \ settlementType` <br />An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values| <span class="string">string</span> |  | 
`workflowConfiguration \ permitUnverifiedAccountPurchase` <br />Prevent accounts who have not verified their emails from making a purchase| <span class="bool">bool</span> |  | 
`workflowConfiguration \ workFlowCustomParameters` <br />A collection of custom attributes associated to the configuration| <span class="dictionary">dictionary</span> |  |
`workFlowCustomParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customAccountParameters` <br />A collection of custom attributes associated to the account | <span class="dictionary">dictionary</span> |  | 
`customAccountParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customOrderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary</span> |  | 
`customOrderParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customSubscriptionParameters` <br />A collection of custom attributes associated to the subscription| <span class="string">string</span> |  |
`customSubscriptionParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`entitlements` <br />A collection of additional entitlements to provide the account on purchase| <span class="array">array[object]</span> |  |
`entitlements \ identifier` <br />Identifier for the entitlement being purchased| <span class="string">string</span> |  |
`entitlements \ startDate` <br />The date on which the entitlement should be valid from| <span class="string">string</span> |  |
`entitlements \ expiryDate` <br />The date at which the account is no longer entitled to the content| <span class="string">string</span> |  |


<aside class="info">
This endpoint can only be called using server-side authentication due to the sensitive nature of some information contained in the `POST` request.
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
    'x-version': '9.0.0',
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
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflows/configurations/products</span>
</div>

### Parameters

 |  |  |  
--------- | ------- | ------- | 
`workflowConfiguration` | <span class="string">string</span> | <span class="required">Required</span> | 
`workflowConfiguration \ pricing` <br />Pricing object for the purchase| <span class="object">object</span> | <span class="required">Required</span> | 
`pricing \ priceId` <br />The configured price identifier| <span class="integer">integer</span> | <span class="required">Required</span> |
`pricing \ paymentMethod` <br />The payment method the customer should be presented by default| <span class="string">string</span> |  |
`pricing \ taxInfo` <br />Collection of tax information| <span class="object">object</span> |  |
`taxInfo \ zeroRated` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo \ country` <br />Country specific tax rate to use| <span class="string">string</span> |  |
`taxInfo \ state` <br />State specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo \ county` <br />County specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo \ city` <br />City specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`workflowConfiguration \ processUpdateUrl` <br />External endpoint eSuite should notiffy of purchase| <span class="string">string</span> |  | 
`workflowConfiguration \ cancelOnProcessUpdateFailure` <br />An indication as to whether eSuite should cancel the purchase on failure to recieve a call out response| <span class="bool">bool</span> |  | 
`workflowConfiguration \ returnUrl` <br />The location to be redirected to upon leaving the purchase flow| <span class="string">string</span> |  | 
`workflowConfiguration \ clientUserId` <br />Unique, non-irrevocable value. Used when eSuite is not primary IdAM| <span class="string">string</span> |  | 
`workflowConfiguration \ email` <br />Accounts email address| <span class="string">string</span> |  | 
`workflowConfiguration \ voucherCode` <br />A pre-configured eSuite voucher code| <span class="string">string</span> |  | 
`workflowConfiguration \ securityToken` <br />Value that is passed in the `ProcessUpdate` callout to allow you to verify it is a legitimate call out| <span class="string">string</span> |  | 
`workflowConfiguration \ disable3DSecure` <br />An indication that 3D Secure should be disabled. Defaults to `false`| <span class="bool">bool</span> |  | 
`workflowConfiguration \ settlementType` <br />An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values| <span class="string">string</span> |  | 
`workflowConfiguration \ permitUnverifiedAccountPurchase` <br />Prevent accounts who have not verified their emails from making a purchase| <span class="bool">bool</span> |  | 
`workflowConfiguration \ workFlowCustomParameters` <br />A collection of custom attributes associated to the configuration| <span class="dictionary">dictionary</span> |  |
`workFlowCustomParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customAccountParameters` <br />A collection of custom attributes associated to the account | <span class="dictionary">dictionary</span> |  | 
`customAccountParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customOrderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary</span> |  | 
`customOrderParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`entitlements` <br />A collection of additional entitlements to provide the account on purchase| <span class="array">array[object]</span> |  |
`entitlements \ identifier` <br />Identifier for the entitlement being purchased| <span class="string">string</span> |  |
`entitlements \ startDate` <br />The date on which the entitlement should be valid from| <span class="string">string</span> |  |
`entitlements \ expiryDate` <br />The date at which the account is no longer entitled to the content| <span class="string">string</span> |  |


<aside class="info">
This endpoint can only be called using server-side authentication due to the sensitive nature of some information contained in the `POST` request.
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
    'x-version': '9.0.0',
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
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflows/configurations/miscellaneous-charge</span>
</div>

### Parameters

 |  |  |  
--------- | ------- | ------- | 
`workflowConfiguration` | <span class="string">string</span> | <span class="required">Required</span> | 
`workflowConfiguration \ processUpdateUrl` <br />External endpoint eSuite should notiffy of purchase| <span class="string">string</span> |  | 
`workflowConfiguration \ cancelOnProcessUpdateFailure` <br />An indication as to whether eSuite should cancel the purchase on failure to recieve a call out response| <span class="bool">bool</span> |  | 
`workflowConfiguration \ returnUrl` <br />The location to be redirected to upon leaving the purchase flow| <span class="string">string</span> |  | 
`workflowConfiguration \ clientUserId` <br />Unique, non-irrevocable value. Used when eSuite is not primary IdAM| <span class="string">string</span> |  | 
`workflowConfiguration \ email` <br />Accounts email address| <span class="string">string</span> |  | 
`workflowConfiguration \ voucherCode` <br />A pre-configured eSuite voucher code| <span class="string">string</span> |  | 
`workflowConfiguration \ securityToken` <br />Value that is passed in the `ProcessUpdate` callout to allow you to verify it is a legitimate call out| <span class="string">string</span> |  | 
`workflowConfiguration \ disable3DSecure` <br />An indication that 3D Secure should be disabled. Defaults to `false`| <span class="bool">bool</span> |  | 
`workflowConfiguration \ settlementType` <br />An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values| <span class="string">string</span> |  | 
`workflowConfiguration \ permitUnverifiedAccountPurchase` <br />Prevent accounts who have not verified their emails from making a purchase| <span class="bool">bool</span> |  | 
`workflowConfiguration \ workFlowCustomParameters` <br />A collection of custom attributes associated to the configuration| <span class="dictionary">dictionary</span> |  |
`workFlowCustomParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customAccountParameters` <br />A collection of custom attributes associated to the account | <span class="dictionary">dictionary</span> |  | 
`customAccountParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`orderItems` <br />A collection ofitems that will be purchased| <span class="array">array[object]</span> | <span class="required">Required</span> |
`orderItems \ customOrderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary</span> |  | 
`customOrderParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`orderItems \ description` <br />The description of the item being purchased| <span class="string">string</span> | <span class="required">Required</span> |
`orderItems \ orderReference` <br />External reference for the item being purchased| <span class="string">string</span> |  |
`orderItems \ comment` <br />Additional comment against the item| <span class="string">string</span> |  |
`orderItems \ priceBreakdown` <br />The payment amounts related to the purchase| <span class="object">object</span> | <span class="required">Required</span> |
`priceBreakdown > grossAmount` <br />The amount the account will be charged| <span class="decimal">decimal</span> | <span class="required">Required</span> |
`priceBreakdown > netAmount` <br />The amount that will be available after tax| <span class="decimal">decimal</span> | <span class="required">Required</span> |
`priceBreakdown > taxAmount` <br />The amount of tax associated to the item| <span class="decimal">decimal</span> | <span class="required">Required</span> |
`orderItems \ taxInfo` <br />Collection of tax information| <span class="object">object</span> | <span class="required">Required</span> |
`taxInfo \ category` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo \ zeroRated` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo \ country` <br />Country specific tax rate to use| <span class="string">string</span> |  |
`taxInfo \ state` <br />State specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo \ county` <br />County specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo \ city` <br />City specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`orderItems \ entitlements` <br />A collection of additional entitlements to provide the account on purchase| <span class="array">array[object]</span> | <span class="required">Required</span> |
`entitlements \ identifier` <br />Identifier for the entitlement being purchased| <span class="string">string</span> |  |
`entitlements \ startDate` <br />The date on which the entitlement should be valid from| <span class="string">string</span> |  |
`entitlements \ expiryDate` <br />The date at which the account is no longer entitled to the content| <span class="string">string</span> |  |

<aside class="info">
This endpoint can only be called using server-side authentication due to the sensitive nature of some information contained in the `POST` request.
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
    'x-version': '9.0.0',
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
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflows/configurations/service-credits</span>
</div>

### Parameters

 |  |  |  
--------- | ------- | ------- | 
`workflowConfiguration` | <span class="string">string</span> | <span class="required">Required</span> | 
`workflowConfiguration \ subscriptionId` <br />The configured subscription service identifier| <span class="string">string</span> |  | 
`workflowConfiguration \ pricing` <br />Pricing object for the purchase| <span class="object">object</span> | <span class="required">Required</span> | 
`pricing \ currency` <br />ISO Currency of the purchase e.g. `EUR`| <span class="string">string</span> |  |
`pricing \ taxInfo` <br />Collection of tax information| <span class="object">object</span> |  |
`taxInfo \ zeroRated` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo \ country` <br />Country specific tax rate to use| <span class="string">string</span> |  |
`taxInfo \ state` <br />State specific tax rate to use (US Specific)| <br /><span class="string">string</span> |  |
`taxInfo \ county` <br />County specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo \ city` <br />City specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`serviceCredits`  <br />Pricing object for the purchase| <span class="object">object</span> | <span class="required">Required</span> | 
`serviceCredits \ description` <br />A description to associate to the purchase| <span class="string">string</span> |  |
`serviceCredits \ paidCredits` <br />The amount of credit which the account should pay for| <span class="string">string</span> |  |
`serviceCredits \ freeCredits` <br />The amount of free credit which the account should receive| <span class="string">string</span> |  |
`workflowConfiguration \ processUpdateUrl` <br />External endpoint eSuite should notify of purchase| <span class="string">string</span> |  | 
`workflowConfiguration \ cancelOnProcessUpdateFailure` <br />An indication as to whether eSuite should cancel the purchase on failure to receive a call out response| <span class="bool">bool</span> |  | 
`workflowConfiguration \ returnUrl` <br />The location to be redirected to upon leaving the purchase flow| <span class="string">string</span> |  | 
`workflowConfiguration \ clientUserId` <br />Unique, non-irrevocable value. Used when eSuite is not primary IdAM| <span class="string">string</span> |  | 
`workflowConfiguration \ email` <br />Accounts email address| <span class="string">string</span> |  | 
`workflowConfiguration \ voucherCode` <br />A pre-configured eSuite voucher code| <span class="string">string</span> |  | 
`workflowConfiguration \ securityToken` <br />Value that is passed in the `ProcessUpdate` call out to allow you to verify it is a legitimate call out| <span class="string">string</span> |  | 
`workflowConfiguration \ disable3DSecure` <br />An indication that 3D Secure should be disabled. Defaults to `false`| <span class="bool">bool</span> |  | 
`workflowConfiguration \ settlementType` <br />An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values| <span class="string">string</span> |  | 
`workflowConfiguration \ permitUnverifiedAccountPurchase` <br />Prevent accounts who have not verified their emails from making a purchase| <span class="bool">bool</span> |  | 
`workflowConfiguration \ workFlowCustomParameters` <br />A collection of custom attributes associated to the configuration| <span class="dictionary">dictionary</span> |  |
`workFlowCustomParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customAccountParameters` <br />A collection of custom attributes associated to the account | <span class="dictionary">dictionary</span> |  | 
`customAccountParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customOrderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary</span> |  | 
`customOrderParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |



<aside class="info">
This endpoint can only be called using server-side authentication due to the sensitive nature of some information contained in the `POST` request.
</aside>


































