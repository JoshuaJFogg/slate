# Customer Support Logs

## CRUD: Create Support Log

```json
{
  "logType": "SupportNote",
  "logStatus": "Open",
  "logTitle": "Unable to access content.",
  "logDetails": "Due to the use of cellular data.",
  "systemAccountId": 12548695
}
```

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/support-logs \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"logType":"SupportNote","logStatus":"Open","logTitle":"Unable to access content.","logDetails":"Due to the use of cellular data.","systemAccountId":12548695}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"logType\":\"SupportNote\",\"logStatus\":\"Open\",\"logTitle\":\"Unable to access content.\",\"logDetails\":\"Due to the use of cellular data.\",\"systemAccountId\":12548695}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs")
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

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs")

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/accounts/{accountId}/support-logs", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/support-logs",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"logType\":\"SupportNote\",\"logStatus\":\"Open\",\"logTitle\":\"Unable to access content.\",\"logDetails\":\"Due to the use of cellular data.\",\"systemAccountId\":12548695}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns a HTTP 201 alongside a response Header of Location.


This endpoint allows you to create a support log against a specific account. 

### HTTP Request

`POST https://uat.mppglobal.com/api/accounts/{accountId}/support-logs`

### Request Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
logType | string | Yes | The type of log entry. Only SupportNote is accepted on the POST.
logStatus | string | Yes | Indication whether the log entry is open or closed.
logTitle | string | Yes | A summary of what the log entry details.
logDetails | string | Yes | Specific information about the log entry being added.
systemAccountId | integer | No | This parameter is provided to track the system account who created the log entry.

## CRUD: Retrieve a Support Log

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}")

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

conn.request("GET", "/api/accounts/{accountId}/support-logs/{supportLogReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}",
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
  "logType": "SupportNote",
  "logStatus": "Open",
  "logTitle": "Unable to access content.",
  "logDetails": "Due to the use of cellular data.",
  "systemAccountId": 1634375,
  "supportLogReference": "0010XABJN0X22IVB90",
  "createdDate": "2017-07-04T08:57:14.487",
  "lastUpdatedDate": "2017-07-04T08:57:14.487"
}
```

This endpoint allows you to retrieve a specific support log, for a specific account. 

### URL Endpoint

`GET http://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}/`

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- |  ----------- |
logType | string | The type of log entry. 
logStatus | string | Indication whether the log entry is open or closed.
logTitle | string | A summary of what the log entry details.
logDetails | string | Specific information about the log entry being added.
systemAccountId | integer | This parameter is provided to track the system account who created the log entry.
supportLogReference | string | This parameter is provided to track the system account who created the log entry.
createdDate | string | This parameter is provided to track the system account who created the log entry.
lastUpdatedDate | string | This parameter is provided to track the system account who created the log entry.

## CRUD: Update a Support Log

```shell
curl --request PUT \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '[{"op":"replace","path":"/LogTitle","value":"A new log title"},{"op":"replace","path":"/LogDetails","value":"Re-write of the details"},{"op":"replace","path":"/LogStatus","value":"Closed"}]'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}");
var request = new RestRequest(Method.PUT);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"replace\",\"path\":\"/LogTitle\",\"value\":\"A new log title\"},{\"op\":\"replace\",\"path\":\"/LogDetails\",\"value\":\"Re-write of the details\"},{\"op\":\"replace\",\"path\":\"/LogStatus\",\"value\":\"Closed\"}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"op\":\"replace\",\"path\":\"/LogTitle\",\"value\":\"A new log title\"},{\"op\":\"replace\",\"path\":\"/LogDetails\",\"value\":\"Re-write of the details\"},{\"op\":\"replace\",\"path\":\"/LogStatus\",\"value\":\"Closed\"}]")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"op\":\"replace\",\"path\":\"/LogTitle\",\"value\":\"A new log title\"},{\"op\":\"replace\",\"path\":\"/LogDetails\",\"value\":\"Re-write of the details\"},{\"op\":\"replace\",\"path\":\"/LogStatus\",\"value\":\"Closed\"}]"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "[{\"op\":\"replace\",\"path\":\"/LogTitle\",\"value\":\"A new log title\"},{\"op\":\"replace\",\"path\":\"/LogDetails\",\"value\":\"Re-write of the details\"},{\"op\":\"replace\",\"path\":\"/LogStatus\",\"value\":\"Closed\"}]"

headers = {
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("PUT", "/api/accounts/{accountId}/support-logs/{supportLogReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}",
  "method": "PUT",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "[{\"op\":\"replace\",\"path\":\"/LogTitle\",\"value\":\"A new log title\"},{\"op\":\"replace\",\"path\":\"/LogDetails\",\"value\":\"Re-write of the details\"},{\"op\":\"replace\",\"path\":\"/LogStatus\",\"value\":\"Closed\"}]" 
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json

```

In the event you need to update a support log entry, this end point should be called to edit non-system generated logs.
### URL Endpoint

`PUT http://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}`

### PUT Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
| array[objects] | Yes | A collection of updates that should be made to the resource
op | string | Yes | The type of change that should be executed. add, replace and remove are available operations.
path | string | Yes | The name of the parameter that should be updated.
value | string | Yes | The new value to store against the parameter.

## CRUD: Delete a Support Log

```json
{
  "logType": "SupportNote",
  "logStatus": "Open",
  "logTitle": "Unable to access content.",
  "logDetails": "Due to the use of cellular data.",
  "systemAccountId": 1634375,
  "supportLogReference": "0010XABJN0X22IVB90",
  "createdDate": "2017-07-04T08:57:14.487",
  "lastUpdatedDate": "2017-07-04T08:57:14.487"
}
```

```shell
curl --request DELETE \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.delete("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}")

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
    }

conn.request("DELETE", "/api/accounts/{accountId}/support-logs/{supportLogReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}",
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

> The above command returns a HTTP 204 upon completion.


In the event a support log entry has been added in error, this endpoint will allow you to delete the resource. The endpoint will not allow you to delete a system generated note.

### URL Endpoint

`DELETE http://uat.mppglobal.com/api/accounts/{accountId}/support-logs/{supportLogReference}`

## Retrieve All Support Logs

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/support-logs \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/support-logs")

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

conn.request("GET", "/api/accounts/{accountId}/support-logs", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/support-logs",
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
    "logs": [
        {
            "logType": "SupportNote",
            "logStatus": "Open",
            "logTitle": "Unable to access content.",
            "logDetails": "Due to the use of cellular data.",
            "systemAccountId": 1634375,
            "supportLogReference": "0010XABJN0X22IVB90",
            "createdDate": "2017-07-04T08:57:14.487",
            "lastUpdatedDate": "2017-07-04T08:57:14.487"
        },
        {
            "logType": "SystemAccount",
            "logStatus": "Open",
            "logTitle": "This much",
            "logDetails": "Customer service credits addition. (10.00 EUR credit added to the customers account).",
            "systemAccountId": null,
            "supportLogReference": "0010XAHJ8U41PKNAE2",
            "createdDate": "2017-07-04T09:25:51.927",
            "lastUpdatedDate": "2017-07-04T09:25:51.927"
        }
    ],
    "totalNumberOfRecords": 2,
    "pageNumber": 1
}
```

This endpoint allows you to retrieve all support logs for a specific account. This includes those created via the API and as system generated notes.

### URL Endpoint

`GET http://uat.mppglobal.com/api/accounts/{accountId}/support-logs/`

### Query String Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
pageNumber | integer | No | Indication as to which page of results to return. Will default to 1.
recordsPerPage | integer | No | Indication as to how many results to return. Will default to 50.

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- |  ----------- |
logs | array[objects] | The collection of support log entries.
logs > logType | string | The type of log entry. 
logs > logStatus | string | Indication whether the log entry is open or closed.
logs > logTitle | string | A summary of what the log entry details.
logs > logDetails | string | Specific information about the log entry being added.
logs > systemAccountId | integer | This parameter is provided to track the system account who created the log entry.
logs > supportLogReference | string | This parameter is provided to track the system account who created the log entry.
logs > createdDate | string | This parameter is provided to track the system account who created the log entry.
logs > lastUpdatedDate | string | This parameter is provided to track the system account who created the log entry.
totalNumberOfRecords | integer | An indication as to how many support log entries are against the account.
pageNumber | integer | The current page number.




