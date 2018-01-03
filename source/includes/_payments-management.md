# Payment Management

## Make a Payment

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/orders \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"logType":"SupportNote","logStatus":"Open","logTitle":"Unable to access content.","logDetails":"Due to the use of cellular data.","systemAccountId":12548695}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/orders");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"logType\":\"SupportNote\",\"logStatus\":\"Open\",\"logTitle\":\"Unable to access content.\",\"logDetails\":\"Due to the use of cellular data.\",\"systemAccountId\":12548695}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/orders")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"logType\":\"SupportNote\",\"logStatus\":\"Open\",\"logTitle\":\"Unable to access content.\",\"logDetails\":\"Due to the use of cellular data.\",\"systemAccountId\":12548695}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/orders")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"logType\":\"SupportNote\",\"logStatus\":\"Open\",\"logTitle\":\"Unable to access content.\",\"logDetails\":\"Due to the use of cellular data.\",\"systemAccountId\":12548695}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"logType\":\"SupportNote\",\"logStatus\":\"Open\",\"logTitle\":\"Unable to access content.\",\"logDetails\":\"Due to the use of cellular data.\",\"systemAccountId\":12548695}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json" }

conn.request("POST", "/api/accounts/{accountId}/orders", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
    "basketNumber": "433M16125900",
    "orders": [
        {
            "orderId": 16125900
        }
    ]
}
```

This end point is present for server-side integrations to take a payment against an account for a set of ad-hoc items.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/orders</span>
</div>

### POST Parameters

 |  |  | 
--------- | ------- | ------- | 
`settlementType` <br />An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values| <span class="string">string</span> |  | 
`pricing` <br />Pricing Information object| <span class="object">object</span> |  | 
`pricing \ paymentMethod` <br />The payment method the account would like to pay using| <span class="string">string</span> |  | 
`pricing \ currency` <br />The currency the payment should be taken in| <span class="string">string</span> |  | 
`voucherCode` <br />eSuite generated voucher code that has been provided during the flow | <span class="string">string</span> |  | 
`cvv` <br />If the purchase is being made using an non-authorised card, this parameter can be passed in to enable authorisation to take place | <span class="string">string</span> |  |
`orderItems` <br />A collection of items that the account is attempting to purchase| <span class="array">array[object]</span> | <span class="required">Required</span> |
`orderItems \ description` <br />The description associated to the item| <span class="string">string</span> | <span class="required">Required</span> | 
`orderItems \ orderReference` <br />An external reference that can be associated to each item| <span class="string">string</span> |  | 
`orderItems \ comment` <br />Additional metadata that may have been provided| <span class="string">string</span> |  | 
`orderItems \ priceBreakdown` <br />The details relating to the amount the account should pay for the item| <span class="object">object</span> | <span class="required">Required</span> | 
`priceBreakdown \ grossAmount` <br />The gross amount for the item| <span class="decimal">decimal</span> | <span class="required">Required</span> | 
`priceBreakdown \ netAmount` <br />The total amount minue the associated tax amount| <span class="decimal">decimal</span> |  | 
`priceBreakdown \ taxAmount` <br />The amount of tax that must be paid on the item| <span class="decimal">decimal</span> |  |
`orderItems \ customOrderParameters` <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary</span> |  | 
`customOrderParameters \ parameterName` <br />The custom attribute name| <span class="string">string</span> |  |
`orderItems \ entitlements` <br />A collection of additional entitlements to provide the account on purchase| <span class="array">array[object]</span> |  |
`entitlements \ identifier` <br />Identifier for the entitlement being purchased| <span class="string">string</span> |  |
`entitlements \ startDate` <br />The date on which the entitlement should be valid from| <span class="string">string</span> |  |
`entitlements \ expiryDate` <br />The date at which the account is no longer entitled to the content| <span class="string">string</span> |  |
`orderItems \ taxInfo` <br />Collection of tax information| <span class="object">object</span> | <span class="required">Required</span> |
`taxInfo \ category` <br />Indication as to which tax category to apply| <span class="string">string</span> |  |
`taxInfo \ zeroRated` <br />Indication as to whether the purchase is tax exempt| <span class="bool">bool</span> |  |
`taxInfo \ country` <br />Country specific tax rate to use| <span class="string">string</span> |  |
`taxInfo \ state` <br />State specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo \ county` <br />County specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`taxInfo \ city` <br />City specific tax rate to use (US Specific)| <span class="string">string</span> |  |
`asynchronousProcessingParameters` <br />Asynchronous Processing Parameters| <span class="object">object</span> |  | 

## Retrieve Payments

```shell
curl --request GET \
  --url 'https://uat.mppglobal.com/api/accounts/{accountId}/orders?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/orders?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/orders?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/orders?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1")

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

conn.request("GET", "/api/accounts/{accountId}/orders?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/orders?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1",
  "method": "GET",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
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
  "totalNumberOfRecords": 1,
  "pageNumber": 1,
  "resultsPerPage": 10,
  "items": [
    {
      "cartReference": "0010OOFT3RWEJPHMK1",
      "fulfilmentReference": "0010OOZT3RWEJPHMK1",
      "status": "Complete",
      "currency": "GBP",
      "paymentReference": "0010OOPP3RWEJPHMK1",
      "paymentDate": "2017-07-06T09:06:28.640Z",
      "description": "A example payment description",
      "priceBreakdown": {
        "grossAmount": 10.00,
        "netAmount": 8.00,
        "taxAmount": 2.00
      },
      "customPaymentParameters": {
        "externalPaymentRefernece" : "AB45frdSEGDF"
      }
    }
  ]
}
```

This endpoint allows you to retrieve all payments for a given account.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/orders</span>
</div>

### Query Parameters

 |  |  | 
--------- | ------- | ------- | 
`createDateFrom` <br />The earliest date a payment was taken that can be included in the response| <span class="string">string</span> | <span class="required">Required</span> | 
`createDateTo` <br />The latest date a payment was taken that can be included in the response | <span class="string">string</span> | <span class="required">Required</span> | 
`rowsPerPage` <br />An indication as to how many records to return | <span class="string">string</span> | <span class="required">Required</span> | 
`currentPage` <br />The page that should be returned| <span class="string">string</span> | <span class="required">Required</span> |  

### Response Parameters

 |  |  
--------- | ------- |  
`totalNumberOfRecords` <br />Total number of records available| <span class="string">string</span> | 
`pageNumber` <br />The page of results being displayed| <span class="string">string</span> | 
`resultsPerPage` <br />The total number of records displayed in the response| <span class="string">string</span> | 
`items` <br />Collection of payments associated to the account| <span class="object">object</span> | 
`items \ cartReference` <br />The specific items that were purchased| <span class="string">string</span> | 
`items \ fulfilmentReference`  <br />The specific fulfilment this payment is associated| <span class="string">string</span> | 
`items \ status`  <br />The status of the payment| <span class="string">string</span> | 
`items \ paymentReference`  <br />The unique identifier associated to the payment| <span class="string">string</span> | 
`items \ currency`  <br />The date at which the subscription should become active| <span class="string">string</span> | 
`items \ paymentDate` <br />The date at which the payment was processed| <span class="string">string</span> | 
`items \ description`  <br />The description associated to the payment| <span class="string">string</span> | 
`items \ priceBreakdown`  <br />Object relating to the price charged to the account| <span class="object">object</span> | 
`priceBreakdown \ grossAmount`  <br />The total amount paid by the customer for the specific payment| <span class="decimal">decimal</span> | 
`priceBreakdown \ netAmount`  <br />The gross amount minus the amount of tax paid| <span class="decimal">decimal</span> | 
`priceBreakdown \ taxAmount`  <br />The amount of tax associated to the payment| <span class="decimal">decimal</span> | 
`items \ customPaymentParameters`  <br />A collection of custom attributes associated to the payment | <span class="dictionary">dictionary</span> | 
`customPaymentParameters \ parameterName`  <br />The name of the custom attribute| <span class="string">string</span> | 


## Update a Payment

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}//api/payments/{paymentReference} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '[{"op":"replace","path":"/status","value":"pending"}]'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}//api/payments/{paymentReference}");
var request = new RestRequest(Method.PATCH);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"replace\",\"path\":\"/status\",\"value\":\"pending\"}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}//api/payments/{paymentReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"op\":\"replace\",\"path\":\"/status\",\"value\":\"pending\"}]")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}//api/payments/{paymentReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"op\":\"replace\",\"path\":\"/status\",\"value\":\"pending\"}]"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "[{\"op\":\"replace\",\"path\":\"/status\",\"value\":\"pending\"}]"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}//api/payments/{paymentReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}//api/payments/{paymentReference}",
  "method": "PUT",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "[{\"op\":\"replace\",\"path\":\"/status\",\"value\":\"pending\"}]"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
> The above command returns a HTTP 204.



This endpoint allows you to edit parameters of the payment that has been returned in the GET request (including custom parameters).

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/payments/{paymentReferene}</span>
</div>

### PATCH Parameters

 |  |  | 
--------- | ------- | ------- |
A collection of updates that should be made to the resource| <span class="array">array[objects]</span> | <span class="required">Required</span> | 
`op` <br />The type of change that should be executed. add, replace and remove are available operations.| <span class="string">string</span> | <span class="required">Required</span> | 
`path` <br />The name of the parameter that should be updated.| <span class="string">string</span> | <span class="required">Required</span> | 
`value` <br />The new value to store against the parameter.| <span class="string">string</span> | <span class="required">Required</span> | 

## Refund a Payment

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/payments/{paymentReference}/refund \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
--data '{"amount":20,"triggerBackOfficeEmail":true,"reason":"Customer has returned their goods.","reasonCode":"0012B","refundAsServiceCredits":true,"serviceCreditExpiry":"2018-07-05"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/payments/{paymentReference}/refund");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"amount\":20,\"triggerBackOfficeEmail\":true,\"reason\":\"Customer has returned their goods.\",\"reasonCode\":\"0012B\",\"refundAsServiceCredits\":true,\"serviceCreditExpiry\":\"2018-07-05\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/payments/{paymentReference}/refund")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"amount\":20,\"triggerBackOfficeEmail\":true,\"reason\":\"Customer has returned their goods.\",\"reasonCode\":\"0012B\",\"refundAsServiceCredits\":true,\"serviceCreditExpiry\":\"2018-07-05\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/payments/{paymentReference}/refund")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"amount\":20,\"triggerBackOfficeEmail\":true,\"reason\":\"Customer has returned their goods.\",\"reasonCode\":\"0012B\",\"refundAsServiceCredits\":true,\"serviceCreditExpiry\":\"2018-07-05\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"amount\":20,\"triggerBackOfficeEmail\":true,\"reason\":\"Customer has returned their goods.\",\"reasonCode\":\"0012B\",\"refundAsServiceCredits\":true,\"serviceCreditExpiry\":\"2018-07-05\"}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json" }

conn.request("POST", "/api/payments/{paymentReference}/refund", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
Not available from a client-side application
```

> The above command returns a HTTP 204 with a location header of the new payment reference created:



Calling this endpoint will allow the refund of a previously processed order. This endpoint cannot be called for orders that have been imported and processed via a different provider.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/orders/{orderId}/refund</span>
</div>

### POST Parameters

 |  |  |  
--------- | ------- | ------- | 
`amount` <br />The amount of money that should be refunded to the account.| <span class="decimal">decimal</span> | <span class="required">Required</span> | 
`triggerBackOfficeEmail` <br />An indication as to whether a back office system should be notified.| <span class="bool">bool</span> |  | 
`reason` <br />Additional information as to why the refund is being performed| <span class="string">string</span> |  | 
`reasonCode` <br />A code specific to your business for refund types| <span class="string">string</span> |  | 
`refundAsServiceCredits` <br />Define whether you would like the refund to be executed against the originating payment method or as a credit on the account.| <span class="bool">bool</span> |  | 
`serviceCreditExpiry` <br />The date at which the service credits would expire.| <span class="string">string</span> |  | 















