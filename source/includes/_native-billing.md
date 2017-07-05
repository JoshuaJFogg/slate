# Native Billing

## Validate a Roku Purchase

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/native-billing/roku \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \

  --data '{"rokuTransactionId":"1244567865","email":"john.smith@mppglobal.com","password":"SuperStrongP@ssword01","newAccountDetails":{"firstName":"John","lastName":"Smith"}}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/native-billing/roku");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"rokuTransactionId\":\"1244567865\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"SuperStrongP@ssword01\",\"newAccountDetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/native-billing/roku")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"rokuTransactionId\":\"1244567865\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"SuperStrongP@ssword01\",\"newAccountDetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/native-billing/roku")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"rokuTransactionId\":\"1244567865\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"SuperStrongP@ssword01\",\"newAccountDetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"rokuTransactionId\":\"1244567865\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"SuperStrongP@ssword01\",\"newAccountDetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"}}"

headers = {
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/native-billing/roku", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/native-billing/roku",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"rokuTransactionId\":\"1244567865\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"SuperStrongP@ssword01\",\"newAccountDetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"}}"
  }

$.ajax(settings).done(function (response) {
  console.log(response);
});
```


This endpoint allows you to pass through the Roku transactionId alongside customer information and the eSuite platform will create an account before adding the subscription.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/native-billing/roku/</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
rokuTransactionId | string | Optional | The roku transaction ID that is to be validated
email | string | Optional | Email address of the customer's Roku billing account
password | string | Optional | Customer's password
newAccountDetails | object | Optional | A sub-object of RokuValidateTransactionRequest, containing additional customer information
newAccountDetails > firstName | string | Optional | The customer's first name, as forwarded from Roku's native billing
newAccountDetails > lastName | string | Optional | The customer's last name, as forwarded from Roku's native billing







## Validate Existing Account's Roku Purchase

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/roku \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \

  --data '{"rokuTransactionId":"1244567865"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/roku");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"rokuTransactionId\":\"1244567865\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/roku")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"rokuTransactionId\":\"1244567865\"}}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/roku")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"rokuTransactionId\":\"1244567865\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"rokuTransactionId\":\"1244567865\"}}"

headers = {
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/{accountId}/subscriptions/native-billing/roku", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/roku",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"rokuTransactionId\":\"1244567865 \"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```


this endpoint should be called when an existing account has made a purchase via Roku. Calling this endpoint will add the Roku subscription to their eSuite account.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/roku</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
rokuTransactionId | string | Optional | The roku transaction ID that is to be validated







## Validate iTunes Purchase

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/native-billing/itunes \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"receipt":"AsedRFTCDsd....TGFESSCGcxcsd484","email":"john.smith@mppglobal.com","password":"@ReallyStrongP@ssw0rd","newaccountdetails":{"firstName":"John","lastName":"Smith"},"currency":"GBP","price":12.5}'
 ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/native-billing/itunes");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"@ReallyStrongP@ssw0rd\",\"newaccountdetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"},\"currency\":\"GBP\",\"price\":12.5}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/native-billing/itunes")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"@ReallyStrongP@ssw0rd\",\"newaccountdetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"},\"currency\":\"GBP\",\"price\":12.5}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/native-billing/itunes")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"@ReallyStrongP@ssw0rd\",\"newaccountdetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"},\"currency\":\"GBP\",\"price\":12.5}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"@ReallyStrongP@ssw0rd\",\"newaccountdetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"},\"currency\":\"GBP\",\"price\":12.5}"

headers = {
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/native-billing/itunes", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/native-billing/itunes",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"email\":\"john.smith@mppglobal.com\",\"password\":\"@ReallyStrongP@ssw0rd\",\"newaccountdetails\":{\"firstName\":\"John\",\"lastName\":\"Smith\"},\"currency\":\"GBP\",\"price\":12.5}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

For first time sign-up and subscribers, calling this endpoint containing information about the iTunes purchase and details of the customer will create and account as well as the subscription within eSuite.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/native-billing/itunes</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
receipt | string | Yes | The encrypted receipt returned from the iTunes stored when the app was purchased
price | number | No | An indication as to the price paid within iTunes
currency | string | No | The currency used to purchase the iTunes subscription
email | string | Optional | Email address of the customer's Roku billing account
password | string | Optional | Customer's password
newAccountDetails | object | Optional | A sub-object of request, containing additional customer information
newAccountDetails > firstName | string | Optional | The customer's first name, as forwarded from iTunes's native billing
newAccountDetails > lastName | string | Optional | The customer's last name, as forwarded from iTunes's native billing








## Validate Existing Account's iTunes Purchase

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/itunes \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"receipt":"AsedRFTCDsd....TGFESSCGcxcsd484","currency":"GBP","price":12.5}
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/itunes");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"currency\":\"GBP\",\"price\":12.5}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/itunes")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"currency\":\"GBP\",\"price\":12.5}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/itunes")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"currency\":\"GBP\",\"price\":12.5}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"currency\":\"GBP\",\"price\":12.5}"

headers = {
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/{accountId}/subscriptions/native-billing/itunes", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/itunes",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"receipt\":\"AsedRFTCDsd....TGFESSCGcxcsd484\",\"currency\":\"GBP\",\"price\":12.5}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

For existing accounts.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/itunes</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
receipt | string | Yes | The encrypted receipt returned from the iTunes stored when the app was purchased
price | number | No | An indication as to the price paid within iTunes
currency | string | No | The currency used to purchase the iTunes subscription



