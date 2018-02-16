# Carts

## Create a Cart

```shell
curl --request POST \
--url https://uat.mppglobal.com/api/carts \
--header 'x-clientId: 1001' \
--header 'x-clientPassword: Str0ngP@ssword' \
--header 'x-version: 9.0.0' \
--header 'content-type: application/json' \
--header 'content-type: application/json' \
--data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/carts");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/carts")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/carts")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
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
    'x-version': '9.0.0',
    'content-type': "application/json" }

conn.request("POST", "/api/carts", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/carts",
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

```

In order to add items to a cart, the cart must first be created by executing a request to this endpoint.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts</span>
</div>

## Retrieve a Cart

```shell
curl --request GET \
--url https://uat.mppglobal.com/api/carts/{cartReference} \
--header 'x-clientId: 1001' \
--header 'x-clientPassword: Str0ngP@ssword' \
--header 'x-version: 9.0.0' \
--data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/carts/{cartReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/carts/{cartReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/carts/{cartReference}")

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

conn.request("GET", "/api/carts/{cartReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/carts/{cartReference}",
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
[
    {
        "resourceReference": "0010IP4Y47M3256M51",
        "description": "item description",
        "pricing": {
            "grossAmount": 10.00,
            "netAmount": 8.00,
            "taxAmount": 2.00,
            "currency": "EUR"
        },
        "quantity": 1,
        "productInfo": {},
        "customLineItemParameters": {}
    }
]
```

This endpoint allows the retrieval of a specific cart that has been created on the eSuite platform.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartReference}</span>
</div>

### Response Parameters

 |  |  
--------- | ------- | 
`lineItemReference` <br />Line Item Reference| <span class="string">string</span> | 
`description` <br />Description of the line item| <span class="string">string</span> | 
`pricing` <br />Collection of information regarding pricing| <span class="object">object</span> | 
`pricing \ grossAmount` <br />The gross amount of the line item| <span style="font-weight:bold;color:#666;">number</span> | 
`pricing \ netAmount` <br />The net amount of the line item| <span style="font-weight:bold;color:#666;">number</span> | 
`pricing \ taxAmount` <br />The tax amount of the line item| <span style="font-weight:bold;color:#666;">number</span> | 
`pricing \ currency` <br />Currency of the transaction| <span class="string">string</span> | 
`quantity` <br />Number of the line item being purchased| <span class="integer">integer</span> | 
`productInfo` <br />Collection of Product information| <span class="object">object</span> | 
`productInfo > productId` <br />The pre-configured product identifier| <span class="integer">integer</span> | 
`customLineItemParameters` <br />Collection of custom line item parameters| <span class="dictionary">dictionary</span> | 
`customLineItemParameters \ parameterName` <br />Name associated to the custom parameter| <span class="string">string</span> | 

## Update a Cart

```shell
curl --request PATCH \
--url https://uat.mppglobal.com/api/carts/{cartReference} \
--header 'content-type: application/json' \
--header 'x-clientId: 1001' \
--header 'x-clientPassword: Str0ngP@ssword' \
--header 'x-version: 9.0.0' \
--data '[{"op":"add","path":"/accountReference","value":"0010X2Y7GLHZ0Y1JH2"}]'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/carts/{cartReference}");
var request = new RestRequest(Method.PATCH);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"add\",\"path\":\"/accountReference\",\"value\":\"0010X2Y7GLHZ0Y1JH2\"}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/carts/{cartReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"op\":\"add\",\"path\":\"/accountReference\",\"value\":\"0010X2Y7GLHZ0Y1JH2\"}]")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/carts/{cartReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"op\":\"add\",\"path\":\"/accountReference\",\"value\":\"0010X2Y7GLHZ0Y1JH2\"}]"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "[{\"op\":\"add\",\"path\":\"/accountReference\",\"value\":\"0010X2Y7GLHZ0Y1JH2\"}]"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/carts/{cartReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/carts/{cartReference}",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "[{\"op\":\"add\",\"path\":\"/accountReference\",\"value\":\"0010X2Y7GLHZ0Y1JH2\"}]" 
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```


> The above command returns JSON structured like this:

```json

```

An existing cart can be edited by calling the following endpoint. An example where this would be required is when associating a cart to a specific eSuite account.


### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartResourceReference}</span>
</div>

### PATCH Parameters

 |  |  | 
--------- | ------- | ------- | 
A collection of updates that should be made to the resource| <span class="array">array[objects]</span> | <span class="required">Required</span> | 
`op` <br />The type of change that should be executed. add, replace and remove are available operations.| <span class="string">string</span> | <span class="required">Required</span> | 
`path` <br />The name of the parameter that should be updated.| <span class="string">string</span> | <span class="required">Required</span> | 
`value` <br />The new value to store against the parameter.| <span class="string">string</span> | <span class="required">Required</span> | 


## Delete a Cart

```shell
curl --request DELETE \
--url https://uat.mppglobal.com/api/carts/{cartReference} \
--header 'x-clientId: 1001' \
--header 'x-clientPassword: Str0ngP@ssword' \
--header 'x-version: 9.0.0' \
--data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/carts/{cartReference}");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.delete("https://uat.mppglobal.com/api/carts/{cartReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/carts/{cartReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Delete.new(url)
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

conn.request("DELETE", "/api/carts/{cartReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/carts/{cartReference}",
  "method": "DELETE",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com"
  },
  "processData": false,
  "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:



In order to remove a cart from the eSuite, this endpoint must be called. If the cart is associated to an previous payment, it is deemed immutable and cannot be removed.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartResourceReference}</span>
</div>



## Create a Line-item

```shell
curl --request POST \
--url https://uat.mppglobal.com/api/carts/{cartReference/line-items \
--header 'x-clientId: 1001' \
--header 'x-clientPassword: Str0ngP@ssword' \
--header 'x-version: 9.0.0' \
--header 'content-type: application/json' \
--header 'content-type: application/json' \
--data '{"description":"Example line item","pricing":{"grossAmount":10,"netAmount":8,"taxAmount":2,"currency":"GBP"},"quantity":1}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/carts/{cartReference/line-items");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"description\":\"Example line item\",\"pricing\":{\"grossAmount\":10,\"netAmount\":8,\"taxAmount\":2,\"currency\":\"GBP\"},\"quantity\":1}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/carts/{cartReference/line-items")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"description\":\"Example line item\",\"pricing\":{\"grossAmount\":10,\"netAmount\":8,\"taxAmount\":2,\"currency\":\"GBP\"},\"quantity\":1}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/carts/{cartReference/line-items")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"description\":\"Example line item\",\"pricing\":{\"grossAmount\":10,\"netAmount\":8,\"taxAmount\":2,\"currency\":\"GBP\"},\"quantity\":1}"


response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"description\":\"Example line item\",\"pricing\":{\"grossAmount\":10,\"netAmount\":8,\"taxAmount\":2,\"currency\":\"GBP\"},\"quantity\":1}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json" }

conn.request("POST", "/api/carts/{cartReference/line-items", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/carts/{cartReference/line-items",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",,
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"description\":\"Example line item\",\"pricing\":{\"grossAmount\":10,\"netAmount\":8,\"taxAmount\":2,\"currency\":\"GBP\"},\"quantity\":1}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json

```

In order to add a new item to a cart, this endpoint should be called. This endpoint will allow the addition of single line items, not bulk.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartReference}/line-items</span>
</div>


### POST Parameters

 |  |  | 
--------- | ------- | ------- | 
`description` <br />Description of the line item| <span class="string">string</span> | <span class="required">Required</span> | 
`pricing` <br />Collection of information regarding pricing| <span class="object">object</span> |  | 
`pricing \ grossAmount` <br />The gross amount of the line item| <span style="font-weight:bold;color:#666;">number</span> | <span class="required">Required</span> | 
`pricing \ netAmount`<br />The net amount of the line item| <span style="font-weight:bold;color:#666;">number</span> | <span class="required">Required</span> | 
`pricing \ taxAmount` <br />The tax amount of the line item| <span style="font-weight:bold;color:#666;">number</span> | <span class="required">Required</span> | 
`pricing \ currency` <br />Currency of the transaction| <span class="string">string</span> | <span class="required">Required</span> | 
`pricing \ priceId` <br />The pre-configured eSuite price identifier| <span class="string">string</span> |  | 
`productId` <br />The pre-configured eSuite product identifier| <span class="integer">integer</span> |  | 
`quantity` <br />Number of the line item being purchased| <span class="integer">integer</span> | <span class="required">Required</span> | 
`customLineItemParameters` <br />Collection of custom line item parameters| <span class="dictionary">dictionary</span> |  | 
`customLineItemParameters` > parameterName <br />Name associated to the custom parameter| <span class="string">string</span> |  | 

## Delete a Line-item

```shell
curl --request DELETE \
--url https://uat.mppglobal.com/api/carts/{cartResourceReference}/line-items/{lineItemResourceReference} \
--header 'x-clientId: 1001' \
--header 'x-clientPassword: Str0ngP@ssword' \
--header 'x-version: 9.0.0' \
--data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/carts/{cartResourceReference}/line-items/{lineItemResourceReference}");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.delete("https://uat.mppglobal.com/api/carts/{cartResourceReference}/line-items/{lineItemResourceReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/carts/{cartResourceReference}/line-items/{lineItemResourceReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Delete.new(url)
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

conn.request("DELETE", "/api/carts/{cartResourceReference}/line-items/{lineItemResourceReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/carts/{cartResourceReference}/line-items/{lineItemResourceReference}",
  "method": "DELETE",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com"
  },
  "processData": false,
  "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:


Calling this endpoint will allow you to remove an item from a cart. It will not be possible to remove an line-item from a cart has is deemed immutable due to being involved in a purchase. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartResourceReference}/line-items/{lineItemReference}</span>
</div>

## Retrieve an Account's Cart


```shell
curl --request GET \
--url https://uat.mppglobal.com/api/accounts/{accountId}/carts/{cartReference} \
--header 'x-clientId: 1001' \
--header 'x-clientPassword: Str0ngP@ssword' \
--header 'x-version: 9.0.0' \
--data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/carts/{cartReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/carts/{cartReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/carts/{cartReference}")

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

conn.request("GET", "/api/accounts/{accountId}/carts/{cartReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/carts/{cartReference}",
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
[
    {
        "resourceReference": "0010IP4Y47M3256M51",
        "description": "item description",
        "pricing": {
            "grossAmount": 10.00,
            "netAmount": 8.00,
            "taxAmount": 2.00,
            "currency": "EUR"
        },
        "quantity": 1,
        "productInfo": {},
        "customLineItemParameters": {}
    }
]
```

Calling this endpoint will allow for the retrieval of all carts associated to an account. The response will include those associated to a payment instruction and those which are still pending completion.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/carts/{cartIdentifier}</span>
</div>

### Response Parameters

 |  |  
--------- | ------- | 
`lineItemReference` <br />Line Item Reference| <span class="string">string</span> | 
`description` <br />Description of the line item| <span class="string">string</span> | 
`pricing` <br />Collection of information regarding pricing| <span class="object">object</span> | 
`pricing \ grossAmount` <br />The gross amount of the line item| <span style="font-weight:bold;color:#666;">number</span> | 
`pricing \ netAmount` <br />The net amount of the line item| <span style="font-weight:bold;color:#666;">number</span> | 
`pricing \ taxAmount` <br />The tax amount of the line item| <span style="font-weight:bold;color:#666;">number</span> | 
`pricing \ currency` <br />Currency of the transaction| <span class="string">string</span> | 
`quantity` <br />Number of the line item being purchased| <span class="integer">integer</span> | 
`productInfo` <br />Collection of Product information| <span class="object">object</span> | 
`productInfo > productId` <br />The pre-configured product identifier| <span class="integer">integer</span> | 
`customLineItemParameters` <br />Collection of custom line item parameters| <span class="dictionary">dictionary</span> | 
`customLineItemParameters \ parameterName` <br />Name associated to the custom parameter| <span class="string">string</span> | 












