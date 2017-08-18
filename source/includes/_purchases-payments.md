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

For the completion of standard payment options, making the following `POST` request will purchase the subscription service provided. A standard payment type is `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`.


### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions</span>
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
`customOrderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary</span> |  | 
`customOrderParameters` > `parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`customSubscriptionParameters` <br />A collection of custom attributes associated to the subscription| <span class="string">string</span> |  |
`customSubscriptionParameters` > `parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
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

For the completion of standard payment options, making the following `POST` request will purchase the service credits. A standard payment type is `CreditCard` `DirectDebit`, `Service Credits` or `SEPA`.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/service-credits</span>
</div>

### POST Parameters

 |   | |  
--------- | ------- | ------- | 
`paymentMethod` <br />The payment method the account has selected to pay with if it differs from the initial configuration| <span class="string">string</span> |  |
`cvv` <br />Security code of a card if the payment method is set to `creditDebitCard`| <span class="string">string</span> |  |
`voucherCode` <br />A voucher code provided by the account during the workflow| <span class="string">string</span> |  |
`paidCredits` <br />The amount of credits the account is purchasing| <span style="font-weight:bold;">number</span> |  | 
`freeCredits` <br />The amount of credits the account will receive without charge| <span style="font-weight:bold;">number</span> |  | 
`asynchronousInitiationParameters` <br />Parameter set provided if you would like to trigger an advanced payment type| <span class="string">string</span> |  |
`asynchronousInitiationParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |


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

 |   | | 
--------- | ------- | ------- | 
`asynchronousProcessingParameters` <br />Parameter set provided if you would like to complete an advanced payment type| <span class="string">string</span> |  |
`asynchronousProcessingParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |

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

 |   | | 
--------- | ------- | ------- | 
`asynchronousProcessingParameters` <br />Parameter set provided if you would like to complete an advanced payment type| <span class="string">string</span> |  |
`asynchronousProcessingParameters` > `parameterName` <br />Parameter name specific to the alternative payment method provided| <span class="string">string</span> |  |