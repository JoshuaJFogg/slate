# Payment Instructions

## Create a Payment Instruction

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"cartReference":"A12347853S","paymentMethod":"SEPA","addressReference":"B123678542","voucherCode":"5OFFABCD","fulfilmentInfo":[{"fulfilmentType":"Digital","addressReference":"B123678542GV","fulfilmentDates":["2018-03-01T00:00:00"],"leadTime":4,"associatedPayments":{"paymentDates":["2018-03-01T00:00:00","2018-05-01T00:00:00","2018-05-01T00:00:00"],"customPaymentParameters":{"originator":"DirectSale"}},"customFulfilmentParameters":{"instructions":"Leave in garage."}}],"synchronousPaymentInfo":{"paymentMethod":"CreditCard","customPaymentParameters":null},"customPaymentInstructionParameters":{"paymentType":"pre-paid"}}'
 ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"cartReference\":\"A12347853S\",\"paymentMethod\":\"SEPA\",\"addressReference\":\"B123678542\",\"voucherCode\":\"5OFFABCD\",\"fulfilmentInfo\":[{\"fulfilmentType\":\"Digital\",\"addressReference\":\"B123678542GV\",\"fulfilmentDates\":[\"2018-03-01T00:00:00\"],\"leadTime\":4,\"associatedPayments\":{\"paymentDates\":[\"2018-03-01T00:00:00\",\"2018-05-01T00:00:00\",\"2018-05-01T00:00:00\"],\"customPaymentParameters\":{\"originator\":\"DirectSale\"}},\"customFulfilmentParameters\":{\"instructions\":\"Leave in garage.\"}}],\"synchronousPaymentInfo\":{\"paymentMethod\":\"CreditCard\",\"customPaymentParameters\":null},\"customPaymentInstructionParameters\":{\"paymentType\":\"pre-paid\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"cartReference\":\"A12347853S\",\"paymentMethod\":\"SEPA\",\"addressReference\":\"B123678542\",\"voucherCode\":\"5OFFABCD\",\"fulfilmentInfo\":[{\"fulfilmentType\":\"Digital\",\"addressReference\":\"B123678542GV\",\"fulfilmentDates\":[\"2018-03-01T00:00:00\"],\"leadTime\":4,\"associatedPayments\":{\"paymentDates\":[\"2018-03-01T00:00:00\",\"2018-05-01T00:00:00\",\"2018-05-01T00:00:00\"],\"customPaymentParameters\":{\"originator\":\"DirectSale\"}},\"customFulfilmentParameters\":{\"instructions\":\"Leave in garage.\"}}],\"synchronousPaymentInfo\":{\"paymentMethod\":\"CreditCard\",\"customPaymentParameters\":null},\"customPaymentInstructionParameters\":{\"paymentType\":\"pre-paid\"}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"cartReference\":\"A12347853S\",\"paymentMethod\":\"SEPA\",\"addressReference\":\"B123678542\",\"voucherCode\":\"5OFFABCD\",\"fulfilmentInfo\":[{\"fulfilmentType\":\"Digital\",\"addressReference\":\"B123678542GV\",\"fulfilmentDates\":[\"2018-03-01T00:00:00\"],\"leadTime\":4,\"associatedPayments\":{\"paymentDates\":[\"2018-03-01T00:00:00\",\"2018-05-01T00:00:00\",\"2018-05-01T00:00:00\"],\"customPaymentParameters\":{\"originator\":\"DirectSale\"}},\"customFulfilmentParameters\":{\"instructions\":\"Leave in garage.\"}}],\"synchronousPaymentInfo\":{\"paymentMethod\":\"CreditCard\",\"customPaymentParameters\":null},\"customPaymentInstructionParameters\":{\"paymentType\":\"pre-paid\"}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"cartReference\":\"A12347853S\",\"paymentMethod\":\"SEPA\",\"addressReference\":\"B123678542\",\"voucherCode\":\"5OFFABCD\",\"fulfilmentInfo\":[{\"fulfilmentType\":\"Digital\",\"addressReference\":\"B123678542GV\",\"fulfilmentDates\":[\"2018-03-01T00:00:00\"],\"leadTime\":4,\"associatedPayments\":{\"paymentDates\":[\"2018-03-01T00:00:00\",\"2018-05-01T00:00:00\",\"2018-05-01T00:00:00\"],\"customPaymentParameters\":{\"originator\":\"DirectSale\"}},\"customFulfilmentParameters\":{\"instructions\":\"Leave in garage.\"}}],\"synchronousPaymentInfo\":{\"paymentMethod\":\"CreditCard\",\"customPaymentParameters\":null},\"customPaymentInstructionParameters\":{\"paymentType\":\"pre-paid\"}}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json" }

conn.request("POST", "/api/accounts/{accountId}/payment-instructions", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
Not available
```

> The above command returns a HTTP 201 alongside a response Header of Location.


This endpoint allows you to create a payment instruction for a specific account. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions</span>
</div>

### Request Parameters

 |  |  | 
--------- | ------- | ------- | 
`cartReference` <br />The cart which is default for the payment instruction.| <span class="string">string</span> | <span class="required">Required</span> | 
`paymentMethod` <br />The default payment method for the payment instruction.| <span class="string">string</span> | <span class="required">Required</span> | 
`addressReference` <br />The reference addrress the fulfilments will be delivered to.| <span class="string">string</span> | <span class="required">Required</span> | 
`voucherCode` <br />A discount code generated from eSuite| <span class="string">string</span> |  | 
`fulfilmentInfo` <br />Information relating to each fulfilment and associated payments| <span class="array">array[objects]</span> | <span class="required">Required</span> | 
`fulfilmentInfo \ fulfilmentType` <br />The type of fulfilment being purchase. Only `physical` is available.| <span class="string">string</span> |  | 
`fulfilmentInfo \ addressReference` <br />An address reference that will override the top level address| <span class="string">string</span> |  |
`fulfilmentInfo \ fulfilmentDates`<br />The collection of dates the fulfilments will be shipped| <span class="array">array[string]</span> | <span class="required">Required</span> | 
`fulfilmentInfo \ leadTime`<br />The number of days lead time needed by a supplier | <span class="integer">integer</span> |  |
`fulfilmentInfo \ associatedPayments`<br />Collection of payments associated to the fulfilment| <span class="object">object</span> | <span class="required">Required</span> | 
`associatedPayments \ paymentDates`<br />The dates at which payment should be taken for the fulfilment| <span class="array">array[string]</span> | <span class="required">Required</span> | 
`customPaymentParameters` <br />This is a collection of custom attributes against the payments.| <span class="dictionary">dictionary</span> |  |
`customPaymentParameters \ parameterName` <br />Representation of all custom parameters against the payments.| <span class="string">string</span> |  |
`customFulfilmentParameters` <br />This is a collection of custom attributes against the fulfilments.| <span class="dictionary">dictionary</span> |  |
`customFulfilmentParameters \ parameterName` <br />Representation of all custom parameters against the fulfilment.| <span class="string">string</span> |  |
`synchronousPaymentInfo` <br />An example string| <span class="object">object</span> |  | 
`synchronousPaymentInfo \ paymentMethod`<br />The method by which the payment should be made| <span class="string">string</span> | <span class="required">Required</span> |
`synchronousPaymentInfo \ customPaymentParameters` <br />This is a collection of custom attributes against the payments.| <span class="dictionary">dictionary</span> |  |
`customPaymentParameters \ parameterName` <br />Representation of all custom parameters against the payments.| <span class="string">string</span> |  |
`customPaymentInstructionParameters` <br />This is a collection of custom attributes against the payment instructions.| <span class="dictionary">dictionary</span> |  |
`customPaymentInstructionParameters \ parameterName`  <br />Representation of all custom parameters against the payment instruction.| <span class="string">string</span> |  | 


## Retrieve a Payment Instruction

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}")

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

conn.request("GET", "/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}",
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
  "paymentInstructionReference": "0010J3O92YZYM43OP0",
  "status": "Active",
  "currency": "GBP",
  "cartReference": "0010KCKSYU72H5M3X0",
  "fulfilmentPaymentMappings": [
    {
      "fulfilments": [
        {
          "fulfilmentReference": "0010L00WASCMKX7UO3",
          "fulfilmentStatus": "Pending",
          "fulfilmentType": "Digital",
          "expectedDeliveryDate": "2017-03-30T00:00:00",
          "supplierNotificationDate": "2017-03-27T00:00:00",
          "addressReference": "0010DF5QFO4XK5H0L0",
          "dateCreated": "2017-03-20T00:00:00",
          "dateLastUpdated": "2017-03-20T00:00:00",
          "customFulfilmentParameters": {
            "Custom Fulfilment Param Name 1": "Custom Fulfilment Param Value 1",
            "Custom Fulfilment Param Name 2": "Custom Fulfilment Param Value 2",
            "Custom Fulfilment Param Name 3": "Custom Fulfilment Param Value 3"
          }
        }
      ],
      "payments": [
        {
          "paymentReference": "0010H00WASCMKX7UO3",
          "paymentDate": "2017-03-23T00:00:00",
          "paymentStatus": "Pending",
          "dateCreated": "2017-03-20T00:00:00",
          "dateLastUpdated": "2017-03-20T00:00:00",
          "vatAmount": 20,
          "grossAmount": 120,
          "netAmount": 100,
          "customPaymentParameters": {
            "Custom Payment Param Name 1": "Custom Payment Param Value 1",
            "Custom Payment Param Name 2": "Custom Payment Param Value 2",
            "Custom Payment Param Name 3": "Custom Payment Param Value 3"
          }
        }
      ]
    }
  ],
  "customPaymentInstructionParameters": {
    "name": "value"
  }
}
```

This endpoint allows you to retrieve a specific support log, for a specific account. 

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}/</span>
</div>

### Response Parameters

 |  |  
--------- | ------- |  
`paymentInstructionReference` <br />The identifier for the payment instruction.| <span class="string">string</span> |  
`status` <br />The status of the payment instruction.| <span class="string">string</span> | 
`currency` <br />The currency against the payment instruction. | <span class="string">string</span> | 
`cartReference` <br />The cart which is default for the payment instruction.| <span class="string">string</span> | 
`fulfilmentPaymentMappings` <br />An array of objects that map payments to their associated fulfilments.| <span class="array">array[objects]</span> | 
`fulfilmentPaymentMappings \ fulfilments` <br />An array of all fulfilments for the payment instruction.| <span class="array">array[objects]</span> | 
`fulfilments \ fulfilmentReference` <br />The reference identifier to the fulfilment| <span class="string">string</span> | 
`fulfilments \ fulfilmentStatus` <br />The status of the fulfilment e.g. pending, processing, dispatched or cancelled.| <span class="string">string</span> | 
`fulfilments \ fulfilmentType` <br />Indication as to whether it is a digital or physical fulfilment.| <span class="string">string</span> | 
`fulfilments \ expectedDeliveryDate` <br />The date and time the account expects to receive their goods.| <span class="string">string</span> | 
`fulfilments \ supplierNotificationDate` <br />The date and time at which eSuite will notify the fulfilment system.| <span class="string">string</span> | 
`fulfilments \ addressReference` <br />The reference addrress the fulfilment will be delivered to.| <span class="string">string</span> | 
`fulfilments \ dateCreated` <br />The date and time the fulfilment was created.| <span class="string">string</span> | 
`fulfilments \ dateLastUpdated` <br />The date and time the fulfilment was last updated.| <span class="string">string</span> | 
`fulfilments \ customFulfilmentParameters` <br />This is a collection of custom attributes against the fulfilment.| <span class="dictionary">dictionary</span> | 
`customFulfilmentParameters \ parameterName`  <br />Representation of all custom parameters against the fulfilment.| <span class="string">string</span> | 
`fulfilmentPaymentMappings \ payments` <br />An array of all payments for the payment instruction.| <span class="array">array[objects]</span> | 
`payments \ paymentReference` <br />The reference identifier to the fulfilment| <span class="string">string</span> | 
`payments \ paymentDate` <br />The status of the fulfilment e.g. pending, processing, dispatched or cancelled.| <span class="string">string</span> | 
`payments \ paymentStatus` <br />Indication as to whether it is a digital or physical fulfilment.| <span class="string">string</span> | 
`payments \ vatAmount` <br />The amount apportioned to tax.| <span class="string">string</span> | 
`payments \ grossAmount` <br />The amount charged and submitted to the merchant.| <span class="string">string</span> | 
`payments \ netAmount` <br />The amount charged minus tax.| <span class="string">string</span> | 
`payments \ dateCreated` <br />The date and time the payment was created.| <span class="string">string</span> | 
`payments \ dateLastUpdated` <br />The date and time the payment was last updated.| <span class="string">string</span> | 
`payments \ customPaymentParameters` <br />This is a collection of custom attributes against the payments.| <span class="dictionary">dictionary</span> | 
`customPaymentParameters \ parameterName`  <br />Representation of all custom parameters against the payment.| <span class="string">string</span> | 
`customPaymentInstructionParameters` <br />This is a collection of custom attributes against the payment instructions.| <span class="dictionary">dictionary</span> | 
`customPaymentInstructionParameters \ parameterName`  <br />Representation of all custom parameters against the payment instruction.| <span class="string">string</span> | 

## Update a Payment Instruction

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
 --data '[{"op":"replace","path":"/Status","value":"Cancelled"},{"op":"add","path":"/CancellationCode","value":"0.14"},{"op":"add","path":"/CancellationReason","value":"this is a value"}]'
 ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}");
var request = new RestRequest(Method.patch);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CancellationCode\",\"value\":\"0.14\"},{\"op\":\"add\",\"path\":\"/CancellationReason\",\"value\":\"this is a value\"}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CancellationCode\",\"value\":\"0.14\"},{\"op\":\"add\",\"path\":\"/CancellationReason\",\"value\":\"this is a value\"}]")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CancellationCode\",\"value\":\"0.14\"},{\"op\":\"add\",\"path\":\"/CancellationReason\",\"value\":\"this is a value\"}]"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CancellationCode\",\"value\":\"0.14\"},{\"op\":\"add\",\"path\":\"/CancellationReason\",\"value\":\"this is a value\"}]"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CancellationCode\",\"value\":\"0.14\"},{\"op\":\"add\",\"path\":\"/CancellationReason\",\"value\":\"this is a value\"}]"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns a HTTP 204:

In the event you need to update a payment instruction, this end point should be called to edit specific attributes of the payment instructions.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}</span>
</div>

### PATCH Parameters

 |  |  | 
--------- | ------- | ------- | 
A collection of updates that should be made to the resource | <span class="array">array[objects]</span> | <span class="required">Required</span> | 
`op` <br />The type of change that should be executed. add, replace and remove are available operations.| <span class="string">string</span> | <span class="required">Required</span> | 
`path` <br />The name of the parameter that should be updated.| <span class="string">string</span> | <span class="required">Required</span> | 
`value` <br />The new value to store against the parameter.| <span class="string">string</span> | <span class="required">Required</span> | 

## Retrieve a summary of Payment Instructions

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/summary \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/summary");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/summary")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/summary")

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

conn.request("GET", "/api/accounts/{accountId}/payment-instructions/summary", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/summary",
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
  "paymentInstructions": [
    {
      "paymentInstructionReference": "0010J3O92YZYM43OP0",
      "status": "Pending",
      "cartReference": "0010KCKSYU72H5M3X0",
      "nextFulfilmentReference": "0010L00WASCMKX7UO3",
      "nextFulfilmentDate": "2017-07-04T08:51:27.1816315Z",
      "lastPaymentDate": "2017-07-04T08:51:27.1816315Z",
      "nextPaymentDate": "2017-07-04T08:51:27.1816315Z",
      "description": null,
      "customPaymentInstructionParameters": {
        "paymentType": "pre-paid"
      }
    }
  ]
}
```

This endpoint allows you to retrieve a summary of all payment instructions against a specific account.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/summary/</span>
</div>

### Response Parameters

 |  |  
--------- | ------- |  
`paymentInstructions` <br />The collection of payment instructions.| <span class="array">array[objects]</span> | 
`paymentInstructionReference` <br />The identifier for the specific payment instruction. | <span class="string">string</span> | 
`cartReference` <br />The identifier for the Cart for the payment instruction.| <span class="string">string</span> | 
`nextFulfilmentReference` <br />The identifier for the next fulfilment on the payment instruction.| <span class="string">string</span> | 
`nextFulfilmentDate` <br />The next date a fulfilment will be dispatched.| <span class="string">string</span> | 
`lastPaymentDate` <br />The date the last payment was taken against the payment instruction.| <span class="integer">integer</span> | 
`nextPaymentDate` <br />The next scheduled date a payment will be taken.| <span class="string">string</span> | 
`description` <br />The name/description of the payment instruction| <span class="string">string</span> | 
`customPaymentInstructionParameters` <br />This is a collection of custom attributes against the payment instructions.| <span class="dictionary">dictionary</span> | 
`customPaymentInstructionParameters \ parameterName` <br />Representation of all custom parameters against the payment instruction.| <span class="string">string</span> | 







