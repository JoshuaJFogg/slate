# Fulfilment Management

## Edit a Fulfilment

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/fulfiment/{fulfilmentReference} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '[{"op":"replace","path":"/Status","value":"Cancelled"},{"op":"add","path":"/CustomFulfilmentParameters/ParameterName","value":"NewParameterValue"},{"op":"replace","path":"/AddressReference","value":"QIUQIEUQIEU8173"},{"op":"replace","path":"/ExpectedDeliveryDate","value":"2017-07-07T00:00:00"},{"op":"replace","path":"/SupplierNotificationDate","value":"2017-06-07T00:00:00"}]'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/fulfiment/{fulfilmentReference}");
var request = new RestRequest(Method.patch);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CustomFulfilmentParameters/ParameterName\",\"value\":\"NewParameterValue\"},{\"op\":\"replace\",\"path\":\"/AddressReference\",\"value\":\"QIUQIEUQIEU8173\"},{\"op\":\"replace\",\"path\":\"/ExpectedDeliveryDate\",\"value\":\"2017-07-07T00:00:00\"},{\"op\":\"replace\",\"path\":\"/SupplierNotificationDate\",\"value\":\"2017-06-07T00:00:00\"}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}/fulfiment/{fulfilmentReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CustomFulfilmentParameters/ParameterName\",\"value\":\"NewParameterValue\"},{\"op\":\"replace\",\"path\":\"/AddressReference\",\"value\":\"QIUQIEUQIEU8173\"},{\"op\":\"replace\",\"path\":\"/ExpectedDeliveryDate\",\"value\":\"2017-07-07T00:00:00\"},{\"op\":\"replace\",\"path\":\"/SupplierNotificationDate\",\"value\":\"2017-06-07T00:00:00\"}]")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/fulfiment/{fulfilmentReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CustomFulfilmentParameters/ParameterName\",\"value\":\"NewParameterValue\"},{\"op\":\"replace\",\"path\":\"/AddressReference\",\"value\":\"QIUQIEUQIEU8173\"},{\"op\":\"replace\",\"path\":\"/ExpectedDeliveryDate\",\"value\":\"2017-07-07T00:00:00\"},{\"op\":\"replace\",\"path\":\"/SupplierNotificationDate\",\"value\":\"2017-06-07T00:00:00\"}]"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CustomFulfilmentParameters/ParameterName\",\"value\":\"NewParameterValue\"},{\"op\":\"replace\",\"path\":\"/AddressReference\",\"value\":\"QIUQIEUQIEU8173\"},{\"op\":\"replace\",\"path\":\"/ExpectedDeliveryDate\",\"value\":\"2017-07-07T00:00:00\"},{\"op\":\"replace\",\"path\":\"/SupplierNotificationDate\",\"value\":\"2017-06-07T00:00:00\"}]"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}/fulfiment/{fulfilmentReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/fulfiment/{fulfilmentReference}",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "[{\"op\":\"replace\",\"path\":\"/Status\",\"value\":\"Cancelled\"},{\"op\":\"add\",\"path\":\"/CustomFulfilmentParameters/ParameterName\",\"value\":\"NewParameterValue\"},{\"op\":\"replace\",\"path\":\"/AddressReference\",\"value\":\"QIUQIEUQIEU8173\"},{\"op\":\"replace\",\"path\":\"/ExpectedDeliveryDate\",\"value\":\"2017-07-07T00:00:00\"},{\"op\":\"replace\",\"path\":\"/SupplierNotificationDate\",\"value\":\"2017-06-07T00:00:00\"}]"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns a HTTP 204:

In the event you need to update a fulfilment, this end point should be called to edit specific attributes of the fulfilment.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/fulfiment/{fulfilmentReference}</span>
</div>

### PATCH Parameters

 |  |  | 
--------- | ------- | ------- | 
A collection of updates that should be made to the resource| <span class="array">array[objects]</span> | <span class="required">Required</span> | 
`op` <br />The type of change that should be executed. add, replace and remove are available operations.| <span class="string">string</span> | <span class="required">Required</span> | 
`path` <br />The name of the parameter that should be updated.| <span class="string">string</span> | <span class="required">Required</span> | 
`value` <br />The new value to store against the parameter.| <span class="string">string</span> | <span class="required">Required</span> | 


## Add additional payment

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/fulfilments/{fulfilmentReference}/payments/ \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"paymentDate":"2017-07-07T08:14:59.126Z","paymentMethod":"string","vatAmount":2,"grossAmount":10,"netAmount":8,"currency":"GBP","customPaymentParameters":{"parameterName":"parameterValue"}}'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/fulfilments/{fulfilmentReference}/payments/");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"paymentDate\":\"2017-07-07T08:14:59.126Z\",\"paymentMethod\":\"string\",\"vatAmount\":2,\"grossAmount\":10,\"netAmount\":8,\"currency\":\"GBP\",\"customPaymentParameters\":{\"parameterName\":\"parameterValue\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/fulfilments/{fulfilmentReference}/payments/")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"paymentDate\":\"2017-07-07T08:14:59.126Z\",\"paymentMethod\":\"string\",\"vatAmount\":2,\"grossAmount\":10,\"netAmount\":8,\"currency\":\"GBP\",\"customPaymentParameters\":{\"parameterName\":\"parameterValue\"}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/fulfilments/{fulfilmentReference}/payments/")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"paymentDate\":\"2017-07-07T08:14:59.126Z\",\"paymentMethod\":\"string\",\"vatAmount\":2,\"grossAmount\":10,\"netAmount\":8,\"currency\":\"GBP\",\"customPaymentParameters\":{\"parameterName\":\"parameterValue\"}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"paymentDate\":\"2017-07-07T08:14:59.126Z\",\"paymentMethod\":\"string\",\"vatAmount\":2,\"grossAmount\":10,\"netAmount\":8,\"currency\":\"GBP\",\"customPaymentParameters\":{\"parameterName\":\"parameterValue\"}}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/{accountId}/fulfilments/{fulfilmentReference}/payments/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
Not available from a client-side application.
```



If you need to add an additional payment to a specific fulfilment, this end point can be called. This is typically if the account has changed the contents of the fulfilment to something more expensive.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/fulfilments/{fulfilmentReference}/payments/</span>
</div>

### POST Parameters

 |  |  | 
--------- | ------- | ------- | 
`paymentDate` <br />The date the payment should be submitted.| <span class="string">string</span> | <span class="required">Required</span> | 
`paymentMethod` <br />The payment method the payment should be taken| <span class="string">string</span> | <span class="required">Required</span> | 
`grossAmount` <br />The amount to submit to the merchant.| <span class="string">string</span> | <span class="required">Required</span> | 
`netAmount` <br />The amount to charge minus tax.| <span class="string">string</span> | <span class="required">Required</span> | 
`vatAmount` <br />The amount apportioned to tax.| <span class="string">string</span> | <span class="required">Required</span> | 
`currency` <br />ISO Currency code| <span class="string">string</span> | <span class="required">Required</span> | 
`customPaymentParameters` <br />This is a collection of custom attributes against the payments.| <span class="dictionary">dictionary</span> |  | 
`customPaymentParameters \ parameterName` <br />Representation of each custom parameters against the payment.| <span class="string">string</span> |  | 
