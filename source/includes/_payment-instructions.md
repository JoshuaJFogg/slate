# Payment Instructions

## CRUD: Create a Payment Instruction

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
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


This endpoint allows you to create a payment instruction. 

### HTTP Request

`POST https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions`

### Request Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
logType | string | Yes | The type of log entry. Only SupportNote is accepted on the POST.



## CRUD: Retrieve a Payment Instruction

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
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

`GET http://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}/`

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- |  ----------- |
paymentInstructionReference | string |  The identifier for the payment instruction.
status | string | The status of the payment instruction.
currency | string | The currency against the payment instruction. 
cartReference | string | The cart which is default for the payment instruction.
fulfilmentPaymentMappings | array[objects] | An array of objects that map payments to their associated fulfilments.
fulfilmentPaymentMappings > fulfilments | array[objects] | An array of all fulfilments for the payment instruction.
.. > fulfilments > fulfilmentReference | string | The reference identifier to the fulfilment
.. > fulfilments > fulfilmentStatus | string | The status of the fulfilment e.g. pending, processing, dispatched or cancelled.
.. > fulfilments > fulfilmentType | string | Indication as to whether it is a digital or physical fulfilment.
.. > fulfilments > expectedDeliveryDate | string | The date and time the account expects to receive their goods.
.. > fulfilments > supplierNotificationDate | string | The date and time at which eSuite will notify the fulfilment system.
.. > fulfilments > addressReference | string | The reference addrress the fulfilment will be delivered to.
.. > fulfilments > dateCreated | string | The date and time the fulfilment was created.
.. > fulfilments > dateLastUpdated | string | The date and time the fulfilment was last updated.
.. > fulfilments > customFulfilmentParameters | dictionary | This is a collection of custom attributes against the fulfilment.
.. > customFulfilmentParameters > parameterName  | string | Representation of all custom parameters against the fulfilment.
fulfilmentPaymentMappings > payments | array[objects] | An array of all payments for the payment instruction.
.. > payments > paymentReference | string | The reference identifier to the fulfilment
.. > payments > paymentDate | string | The status of the fulfilment e.g. pending, processing, dispatched or cancelled.
.. > payments > paymentStatus | string | Indication as to whether it is a digital or physical fulfilment.
.. > payments > vatAmount | string | The amount apportioned to tax.
.. > payments > grossAmount | string | The amount charged and submitted to the merchant.
.. > payments > netAmount | string | The amount charged minus tax.
.. > payments > dateCreated | string | The date and time the payment was created.
.. > payments > dateLastUpdated | string | The date and time the payment was last updated.
.. > payments > customPaymentParameters | dictionary | This is a collection of custom attributes against the payments.
.. > customPaymentParameters > parameterName  | string | Representation of all custom parameters against the payment.
customPaymentInstructionParameters | dictionary | This is a collection of custom attributes against the payment instructions.
.. > customPaymentInstructionParameters > parameterName  | string | Representation of all custom parameters against the payment instruction.

## CRUD: Update a Payment Instruction

```shell
curl --request PUT \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
 --data '[{"op":"replace","path":"/Status","value":"Cancelled"},{"op":"add","path":"/CancellationCode","value":"0.14"},{"op":"add","path":"/CancellationReason","value":"this is a value"}]'
 ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}");
var request = new RestRequest(Method.PUT);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CancellationCode\",\"value\":\"0.14\"},{\"op\":\"add\",\"path\":\"/CancellationReason\",\"value\":\"this is a value\"}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}")
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

request = Net::HTTP::Post.new(url)
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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("PUT", "/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}",
  "method": "PUT",
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

`PUT http://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/{paymentInstructionReference}`

### PUT Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
 - | array[objects] | Yes | A collection of updates that should be made to the resource
op | string | Yes | The type of change that should be executed. add, replace and remove are available operations.
path | string | Yes | The name of the parameter that should be updated.
value | string | Yes | The new value to store against the parameter.

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
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

`GET http://uat.mppglobal.com/api/accounts/{accountId}/payment-instructions/summary/`

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- |  ----------- |
paymentInstructions | array[objects] | The collection of payment instructions.
paymentInstructions > paymentInstructionReference | string | The identifier for the specific payment instruction. 
paymentInstructions > cartReference | string | The identifier for the Cart for the payment instruction.
paymentInstructions > nextFulfilmentReference | string | The identifier for the next fulfilment on the payment instruction.
paymentInstructions > nextFulfilmentDate | string | The next date a fulfilment will be dispatched.
paymentInstructions > lastPaymentDate | integer | The date the last payment was taken against the payment instruction.
paymentInstructions > nextPaymentDate | string | The next scheduled date a payment will be taken.
paymentInstructions > description | string | The name/description of the payment instruction
paymentInstructions > customPaymentInstructionParameters | dictionary | This is a collection of custom attributes against the payment instructions.
paymentInstructions > parameterName | string | Representation of all custom parameters against the payment instruction.







