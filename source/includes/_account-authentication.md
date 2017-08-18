# Account Authentication

## Authenticate via email and password

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/authenticate/ \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"email":"john.smith@mppglobal.com","password":"pWzjWktsWN8M"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/authenticate/");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"email\":\"john.smith@mppglobal.com\",\"password\":\"pWzjWktsWN8M\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/authenticate/")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"email\":\"john.smith@mppglobal.com\",\"password\":\"pWzjWktsWN8M\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/authenticate/")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"email\":\"john.smith@mppglobal.com\",\"password\":\"pWzjWktsWN8M\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"email\":\"john.smith@mppglobal.com\",\"password\":\"pWzjWktsWN8M\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/authenticate/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/authenticate/",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"email\":\"john.smith@mppglobal.com\",\"password\":\"pWzjWktsWN8M\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "accountId": 19874854,
  "resourceReference": "14BB19DD3A5509",
  "sessionToken": "E79D7A1FC0314BB19DD3A5509B77584C"
}
```

When eSuite is being used as a primary identity platform, authentication is handled via the use of a registered email address and password. These values are provided as part of the registration request and then used on the `POST` of this request to gain a session.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/authenticate/</span>
</div>

### Parameters

 |  |  |  
--------- | ------- | ------- | 
`email` <br />The registered address of the account being logged in| <span class="string">string</span> | <span class="required">Required</span> | 
`password` <br />The password provided as part of registration| <span class="string">string</span> | <span class="required">Required</span> | 


## Authenticate via ClientUserId

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/authenticate/{clientUserId} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/authenticate/{clientUserId}");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"email\":\"john.smith@mppglobal.com\",\"password\":\"pWzjWktsWN8M\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/authenticate/{clientUserId}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/authenticate/{clientUserId}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
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
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/authenticate/{clientUserId}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "accountId": 19874854,
  "resourceReference": "14BB19DD3A5509",
  "sessionToken": "E79D7A1FC0314BB19DD3A5509B77584C"
}
```

Authentication via a ClientUserId is required when eSuite is not the primary identity platform. The ClientUserId will have been set during the registration of the account and will be a unique, non-revocable value.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/authenticate/{clientUserId}</span>
</div>

### Parameters

 |  |  |  
--------- | ------- | ------- | 
`clientUserId` <br />Unique, irrevocable link that was added to the account at the point of registration.| <span class="string">string</span> | <span class="required">Required</span> | 


<aside class="info">
Due to the sensetive nature of a ClientUserId it is not possible to call this endpoint using a client-side language.
</aside>

