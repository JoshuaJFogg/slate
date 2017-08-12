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
    'x-version': "9.0.0",
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

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`settlementType` | string | No | An indication whether to complete immediately or at a later date. `Pending` or `NextAvailable` are the available values
`pricing` | object | No | Pricing Information object
`pricing` > `paymentMethod` | string | No | The payment method the account would like to pay using
`pricing` > `currency` | string | No | The currency the payment should be taken in
`voucherCode` | string | No | eSuite generated voucher code that has been provided during the flow |
`cvv` | string | No |If the purchase is being made using an non-authorised card, this parameter can be passed in to enable authorisation to take place |
`orderItems` | array[object] | No |A collection of items that the account is attempting to purchase
`orderItems` > `description` | string | No | The description associated to the item
`orderItems` > `orderReference` | string | No | An external reference that can be associated to each item
`orderItems` > `comment` | string | No | Additional metadata that may have been provided
`orderItems` > `priceBreakdown` | object | No | The details relating to the amount the account should pay for the item
`priceBreakdown` > `grossAmount` | decimal | No | The gross amount for the item
`priceBreakdown` > `netAmount` | decimal | No | The total amount minue the associated tax amount
`priceBreakdown` > `taxAmount` | decimal | No |The amount of tax that must be paid on the item
`orderItems` > `customOrderParameters` | dictionary | No | A collection of custom attributes associated to the payment |
`customOrderParameters` > `parameterName` | string | No |The custom attribute name|
`orderItems` > `entitlements` | array[object] | No |A collection of additional entitlements to provide the account on purchase|
`entitlements` > `identifier` | string | No |Identifier for the entitlement being purchased|
`entitlements` > `startDate` | string | No |The date on which the entitlement should be valid from|
`entitlements` > `expiryDate` | string | No |The date at which the account is no longer entitled to the content|
`orderItems` > `taxInfo` | object | Yes |Collection of tax information|
`taxInfo` > `category` | string | No |Indication as to which tax category to apply|
`taxInfo` > `zeroRated` | Bool | No |Indication as to whether the purchase is tax exempt|
`taxInfo` > `country` | string | No |Country specific tax rate to use|
`taxInfo` > `state` | string | No |State specific tax rate to use (US Specific)|
`taxInfo` > `county` | string | No |County specific tax rate to use (US Specific)|
`taxInfo` > `city` | string | No |City specific tax rate to use (US Specific)|
`asynchronousProcessingParameters` | object | No | Asynchronous Processing Parameters

## Retrieve Payments

```shell
curl --request GET \
  --url 'https://uat.mppglobal.com/api/accounts/{accountId}/payments?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/payments?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/payments?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/payments?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1")

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

conn.request("GET", "/api/accounts/{accountId}/payments?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/payments?createDateFrom=2010-07-06T09:06:28.640Z&createDateTo=2017-07-06T09:06:28.640Z&rowsPerPage=10&currentPage=1",
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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/payments</span>
</div>

### Query Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`createDateFrom` | string | Yes |The earliest date a payment was taken that can be included in the response 
`createDateTo` | string | Yes | The latest date a payment was taken that can be included in the response 
`rowsPerPage` | string | Yes | An indication as to how many records to return 
`currentPage` | string | Yes | The page that should be returned 

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- |  ----------- |
`totalNumberOfRecords` | string | Total number of records available
`pageNumber` | string | The page of results being displayed
`resultsPerPage` | string | The total number of records displayed in the response
`items` | object | Collection of payments associated to the account
`items` > `cartReference` | string | The specific items that were purchased
`items` > `fulfilmentReference`  | string | The specific fulfilment this payment is associated
`items` > `status`  | string | The status of the payment
`items` > `paymentReference`  | string | The unique identifier associated to the payment
`items` > `currency`  | string | The date at which the subscription should become active
`items` > `paymentDate` | string | The date at which the payment was processed
`items` > `description`  | string | The description associated to the payment
`items` > `priceBreakdown`  | object | Object relating to the price charged to the account
`priceBreakdown` > `grossAmount`  | decimal | The total amount paid by the customer for the specific payment
`priceBreakdown` > `netAmount`  | decimal | The gross amount minus the amount of tax paid
`priceBreakdown` > `taxAmount`  | decimal | The amount of tax associated to the payment
`items` > `customPaymentParameters`  | dictionary | A collection of custom attributes associated to the payment 
`customPaymentParameters` > `parameterName`  | string | The name of the custom attribute


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
    'x-version': "9.0.0",
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
Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
 - | array[objects] | Yes | A collection of updates that should be made to the resource
`op` | string | Yes | The type of change that should be executed. add, replace and remove are available operations.
`path` | string | Yes | The name of the parameter that should be updated.
`value` | string | Yes | The new value to store against the parameter.

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
    'x-version': "9.0.0",
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

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`amount` | number | Yes | The amount of money that should be refunded to the account.
`triggerBackOfficeEmail` | Bool | No | An indication as to whether a backoffice system should be notified.
`reason` | string | No | Additional information as to why the refund is being performed
`reasonCode` | string | No | A code specific to your business for refund types
`refundAsServiceCredits` | bool | No | Define whether you would like the refund to be executed against the originating payment method or as a credit on the account.
`serviceCreditExpiry` | string | No | The date at which the service credits would expire.















