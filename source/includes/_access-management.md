# Access Management

## CRUD: Create Access

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/%7BaccountId%7D/entitlements \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"name":"Open Access to the Tribune","identifier":"TheTribuneOpen","startDate":"2015-01-01T00:00:00","endDate":"2019-01-01T00:00:00"}'```
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"name\":\"Open Access to the Tribune\",\"identifier\":\"TheTribuneOpen\",\"startDate\":\"2015-01-01T00:00:00\",\"endDate\":\"2019-01-01T00:00:00\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"name\":\"Open Access to the Tribune\",\"identifier\":\"TheTribuneOpen\",\"startDate\":\"2015-01-01T00:00:00\",\"endDate\":\"2019-01-01T00:00:00\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"name\":\"Open Access to the Tribune\",\"identifier\":\"TheTribuneOpen\",\"startDate\":\"2015-01-01T00:00:00\",\"endDate\":\"2019-01-01T00:00:00\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"name\":\"Open Access to the Tribune\",\"identifier\":\"TheTribuneOpen\",\"startDate\":\"2015-01-01T00:00:00\",\"endDate\":\"2019-01-01T00:00:00\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/{accountId}/entitlements", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
Unavailable
```

> The above command will return a HTTP 204 and an empty response body:

```json

```

In addition to gaining entitlements via purchasing content, it is possible to provide access to an account directly via the API.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/entitlements</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`name` | string | Optional | The name of entitlement
`identifier` | string | Yes | The identifier of entitlement
`startDate` | string | Yes | The create date of the entitlement
`endDate` | string | Yes | The expiry of the entitlement


## CRUD: Retrieve Access

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/entitlements \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements")

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

conn.request("GET", "/api/accounts/{accountId}/entitlements", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/entitlements",
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
  "entitlements": [
    {
      "name": "Open Access to the Tribune",
      "identifier": "TheTribuneOpen",
      "startDate": "2015-01-01T00:00:00",
      "endDate": "2019-01-01T00:00:00"
    }
  ]
}
```

This endpoint is available for retrieving all active access for a specific account.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/entitlements</span>
</div>

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`entitlements` | string | Optional | The list of current account entitlements
`name` | string | Optional | The name of entitlement
`identifier` | string | Required | The identifier of entitlement
`startDate` | string | Required | The create date of the entitlement
`endDate` | string | Required | The expire date of the entitlement

## CRUD: Delete Access

```shell
curl --request DELETE \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}")

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
    'x-version': "9.0.0"
    }

conn.request("DELETE", "/api/accounts/{accountId}/entitlements/{entitlementIdentifier}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}",
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

> The above command returns an empty JSON document:

```json

```

In the event access should be removed from an account, this API method should be triggered

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}</span>
</div>

<aside class="warning">Executing this API will not remove access from the account until the access rights of the account are checked again.</aside>



## Validate Access


```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}?incrementUsage=true&deviceIdentifier=iPad \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}?incrementUsage=true&deviceIdentifier=iPad");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}?incrementUsage=true&deviceIdentifier=iPad")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}?incrementUsage=true&deviceIdentifier=iPad")

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

conn.request("GET", "/api/accounts/{accountId}/entitlements/{entitlementIdentifier}?incrementUsage=true&deviceIdentifier=iPad", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}?incrementUsage=true&deviceIdentifier=iPad",
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
  "remainingTime" : "584.15:18:54",
  "deviceLimitExceeded" : true,
  "entitlementAvailable" : false
}
```

In order to check if an account has access to content, this API method should be executed. Passing through the incrementUsage parameter will add one onto the entitlement count and passing a deviceIdentifier will allow you to make use of eSuite device concurrency functionality.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}</span>
</div>

### Query Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`incrementUsage` | boolean | Optional | This option will default to false if not provided. 
`deviceIdentifier` | string | Optional | If device concurrency is being used, this value must be populated.

### Response Parameters

Parameter | Type | Description | 
--------- | ------- | ------- | 
`remainingTime` | string | The remaining amount of time the customer has access (DD.HH:MM:SS)
`deviceLimitExceeded` | boolean | An indication as to whether the customer is consuming content on the maximum number of devices
`entitlementAvailable` | boolean | An indication as to whether the customer has access to the entitlement


## Search Access

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/search?rowsPerPage=10&currentPage=1&exactMatch=false \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/search?rowsPerPage=10&currentPage=1&exactMatch=false");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/search?rowsPerPage=10&currentPage=1&exactMatch=false")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/search?rowsPerPage=10&currentPage=1&exactMatch=false")

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

conn.request("GET", "/api/accounts/{accountId}/entitlements/search?rowsPerPage=10&currentPage=1&exactMatch=false", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/search?rowsPerPage=10&currentPage=1&exactMatch=false",
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
    "totalNumberOfRecords": 2973,
    "pageNumber": 1,
    "resultsPerPage": 10,
    "items": [
      {
        "name": "Open Access to the Tribune",
        "identifier": "TheTribuneOpen",
        "startDate": "2015-01-01T00:00:00",
        "endDate": "2019-01-01T00:00:00"
      }
    ]
}
```

This endpoint is available for all access for a specific account, regardless of whether it is active.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/entitlements/search</span>
</div>

### Query Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`createDateMin` | string | Optional | Earliest creation date to search 
`createDateMax` | string | Optional | Latest creation date to search
`startDateMin`| string | Optional | Earliest Entitlement start date to search
`startDateMax` | string | Optional | Latest Entitlement start date to search
`endDateMin` | string | Optional | Earliest Entitlement expiration date to search
`endDateMax` | string | Optional | Latest Entitlement expiration date to search
`entitlementIdentifier` | string | Optional | The name of entitlement
`rowsPerPage` | integer | Optional | Number of items to return in the response
`currentPage` | integer | Optional | Page to return
`exactMatch` | boolean | Optional | Indication whether to exactly match the entitlementIdentifer (default to false)

<aside class="info">Passing no query parameters will return a 204.</aside>


### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`entitlements` | string | Optional | The list of current account entitlements
`name` | string | Optional | The name of entitlement
`identifier` | string | Required | The identifier of entitlement
`startDate` | string | Required | The create date of the entitlement
`endDate` | string | Required | The expire date of the entitlement

