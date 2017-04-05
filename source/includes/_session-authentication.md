# Session Authentication

## Login using email address

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/authenticate \
  --header 'content-type: application/json' \
  --header 'x-clientid: 1001' \
  --header 'x-tokenid: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"email":"john.smith@mppglobal.com","password":"TheColourRed"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/authenticate");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-clientid", "1001");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"email\":\"john.smith@mppglobal.com\",\"password\":\"TheColourRed\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/authenticate")
  .header("x-clientpassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("x-clientid", "1001")
  .header("content-type", "application/json")
  .body("{\"email\":\"john.smith@mppglobal.com\",\"password\":\"TheColourRed\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/authenticate")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientpassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["x-clientid"] = '1001'
request["content-type"] = 'application/json'
request.body = "{\"email\":\"john.smith@mppglobal.com\",\"password\":\"TheColourRed\"}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"email\":\"john.smith@mppglobal.com\",\"password\":\"TheColourRed\"}"

headers = {
    'x-clientpassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'x-clientid': "1001",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/authenticate", payload, headers)

res = conn.getresponse()
```

> The above command returns JSON structured like this:

```json
  {
    "accountId": 141458,
    "resourceReference": "OO45FTG67GTF",
    "sessionToken": "7c7e316ff9c6453fae5da7b7c26c4c77"
  }
```

This endpoint allows customers to authenticate themselves and gain a session for their eSuite account.

### URL End-point

`POST https://uat.mppglobal.com/api/accounts/authenticate`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
email | string | Yes | The email address associated to the eSuite account.
password | string | Yes | The password the customer has associated to their account.


## Login using client-defined identifiers

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/authenticate/AED34567564 \
  --header 'content-type: application/json' \
  --header 'x-clientid: 1001' \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/authenticate/AED34567564");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("application/json", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/authenticate/AED34567564")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/authenticate/AED34567564")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientpassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{}"

headers = {
    'x-clientid': "1001",
    'x-clientpassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/authenticate/AED34567564", payload, headers)

res = conn.getresponse()
```

> The above command returns JSON structured like this:

```json
  {
    "accountId": 141458,
    "resourceReference": "OO45FTG67GTF",
    "sessionToken": "7c7e316ff9c6453fae5da7b7c26c4c77"
  }
```

This endpoint allows third-party systems gain a session for an account that isn't mastered in eSuite.

### URL End-point

`POST https://uat.mppglobal.com/api/accounts/authenticate/:clientUserId`

<aside class="warning">
Client-defined identifiers (clientUserId) are a single key authentication and as such can only authenticate by a server-side authentication request.
</aside>

## Delete a session

```shell
curl --request DELETE \
  --url https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77 \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-clientid: 1001' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.delete("https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Delete.new(url)
request["x-clientid"] = '1001'
request["x-clientpassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{}"

headers = {
    'x-clientid': "1001",
    'x-clientpassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
    }

conn.request("DELETE", "/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77", payload, headers)

res = conn.getresponse()
```




### URL End-point

`GET https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77`

## Validate a session

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77 \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-clientid: 1001' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-clientid"] = '1001'
request["x-clientpassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{}"

headers = {
    'x-clientid': "1001",
    'x-clientpassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
    }

conn.request("GET", "/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77", payload, headers)

res = conn.getresponse()
```
> The above command returns JSON structured like this:

```json
  {
    "accountId": 141458,
    "resourceReference": "OO45FTG67GTF",
    "sessionToken": "7c7e316ff9c6453fae5da7b7c26c4c77"
  }
```

### URL End-point

`GET https://uat.mppglobal.com/api/sessions/7c7e316ff9c6453fae5da7b7c26c4c77`