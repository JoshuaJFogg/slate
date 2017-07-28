# Purchases

## Standard Subscription Purchase

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"pricing":{"priceId":18763,"paymentMethod":"CreditCard"}}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"pricing\":{\"priceId\":18763,\"paymentMethod\":\"CreditCard\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"pricing\":{\"priceId\":18763,\"paymentMethod\":\"CreditCard\"}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"pricing\":{\"priceId\":18763,\"paymentMethod\":\"CreditCard\"}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"pricing\":{\"priceId\":18763,\"paymentMethod\":\"CreditCard\"}}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/accounts/{accountId}/subscriptions", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "amountCharged": 10.00,
  "currency": "GBP",
  "paymentType": "DirectDebit",
  "subscriptionStatus": "Active",
  "renewalDay": 1,
  "renewalDayOffset": 0,
  "startDate": "2015-01-01T00:00:00",
  "renewalDate": "2017-01-01T00:00:00",
  "orderReference": 12548,
  "subscriptionId": 4555888,
  "subscriptionPriceId": 568845,
  "subscriptionReference": "458845",
  "resourceReference": "ResourceReference",
  "asynchronousProcessingParameters": null
}
```

For the completion of standard payment options, making the following `POST` request will purchase the subscription service configured within the initial configuration request. A simple payment type is `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`.


### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions</span>
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
`taxInfo` > `zeroRated` | boolean | No |Indication as to whether the purchase is tax exempt|
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


## Standard Credits Purchase

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/service-credits \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"paymentMethod":"CreditDebitCard","currency":"GBP","paidCredits":10.12,"freeCredits":10.99}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/service-credits");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
equest.AddParameter("application/json", "{\"paymentMethod\":\"CreditDebitCard\",\"currency\":\"GBP\",\"paidCredits\":10.12,\"freeCredits\":10.99}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/service-credits")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"paymentMethod\":\"CreditDebitCard\",\"currency\":\"GBP\",\"paidCredits\":10.12,\"freeCredits\":10.99}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/service-credits")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"paymentMethod\":\"CreditDebitCard\",\"currency\":\"GBP\",\"paidCredits\":10.12,\"freeCredits\":10.99}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"paymentMethod\":\"CreditDebitCard\",\"currency\":\"GBP\",\"paidCredits\":10.12,\"freeCredits\":10.99}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/accounts/{accountId}/service-credits", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "orderId": "123456",
  "asynchronousProcessingParameters": {
    "redirectL:ink": "https://my-payments.com/?token=12345"
  }
```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/service-credits</span>
</div>

### POST Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`paymentMethod` | string | No |The payment method the account has selected to pay with if it differs from the initial configuration|
`cvv` | string | No |Security code of a card if the payment method is set to `creditDebitCard`|
`voucherCode` | string | No |A voucher code provided by the account during the workflow|
`paidCredits` | number | Optional | The amount of credits the account is purchasing
`freeCredits` | number | Optional | The amount of credits the account will receive without charge
`asynchronousInitiationParameters` | string | No |Parameter set provided if you would like to trigger an advanced payment type|
`asynchronousInitiationParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|


## Alternative Subscription Purchase

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscription \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"asynchronousProcessingParameters":{"paymentToken":"ASWDE345YGT"}}'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscription");
var request = new RestRequest(Method.PATCH);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"asynchronousProcessingParameters\":{\"paymentToken\":\"ASWDE345YGT\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}/subscription")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"asynchronousProcessingParameters\":{\"paymentToken\":\"ASWDE345YGT\"}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscription")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"asynchronousProcessingParameters\":{\"paymentToken\":\"ASWDE345YGT\"}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"asynchronousProcessingParameters\":{\"paymentToken\":\"ASWDE345YGT\"}}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}/subscription", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:


```json
{
  "amountCharged": 10.00,
  "currency": "GBP",
  "paymentType": "DirectDebit",
  "subscriptionStatus": "Active",
  "renewalDay": 1,
  "renewalDayOffset": 0,
  "startDate": "2015-01-01T00:00:00",
  "renewalDate": "2017-01-01T00:00:00",
  "orderReference": 12548,
  "subscriptionId": 4555888,
  "subscriptionPriceId": 568845,
  "subscriptionReference": "458845",
  "resourceReference": "ResourceReference",
  "asynchronousProcessingParameters": null
}
```


For the completion of alternative subscription options, making the following `PATCH` request will purchase the subscription service configured within the initial configuration request. A alternative payment type is `PayPal` `Alipay`, and any other which requires a redirect.


### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`asynchronousProcessingParameters` | string | No |Parameter set provided if you would like to complete an advanced payment type|
`asynchronousProcessingParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|

## Alternative Credits Purchase

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/service-credits \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"asynchronousProcessingParameters":{"paymentToken":"ASWDE345YGT"}}'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/service-credits");
var request = new RestRequest(Method.PATCH);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"asynchronousProcessingParameters\":{\"paymentToken\":\"ASWDE345YGT\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}/service-credits")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"asynchronousProcessingParameters\":{\"paymentToken\":\"ASWDE345YGT\"}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/service-credits")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"asynchronousProcessingParameters\":{\"paymentToken\":\"ASWDE345YGT\"}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"asynchronousProcessingParameters\":{\"paymentToken\":\"ASWDE345YGT\"}}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}/service-credits", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

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
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/service-credits</span>
</div>

### Request Parameters

Parameter | Type  | Mandatory| Description | 
--------- | ------- | ------- | ------- | 
`asynchronousProcessingParameters` | string | No |Parameter set provided if you would like to complete an advanced payment type|
`asynchronousProcessingParameters` > `parameterName` | string | No |Parameter name specific to the alternative payment method provided|