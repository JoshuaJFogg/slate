# Bulk Actions

## Create Access

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/bulk/entitlements \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --data '{"entitlementIdentifier":"specific-access","startDate":"2017-07-03T11:31:41.0353603Z","endDate":"2017-07-13T11:31:41.0353603Z","accountIds":[123456,123457,123458],"clientUserIds":["A123456","A123457","A123458"]}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/bulk/entitlements");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"entitlementIdentifier\":\"specific-access\",\"startDate\":\"2017-07-03T11:31:41.0353603Z\",\"endDate\":\"2017-07-13T11:31:41.0353603Z\",\"accountIds\":[123456,123457,123458],\"clientUserIds\":[\"A123456\",\"A123457\",\"A123458\"]}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/bulk/entitlements")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"entitlementIdentifier\":\"specific-access\",\"startDate\":\"2017-07-03T11:31:41.0353603Z\",\"endDate\":\"2017-07-13T11:31:41.0353603Z\",\"accountIds\":[123456,123457,123458],\"clientUserIds\":[\"A123456\",\"A123457\",\"A123458\"]}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/bulk/entitlements")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"entitlementIdentifier\":\"specific-access\",\"startDate\":\"2017-07-03T11:31:41.0353603Z\",\"endDate\":\"2017-07-13T11:31:41.0353603Z\",\"accountIds\":[123456,123457,123458],\"clientUserIds\":[\"A123456\",\"A123457\",\"A123458\"]}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"entitlementIdentifier\":\"specific-access\",\"startDate\":\"2017-07-03T11:31:41.0353603Z\",\"endDate\":\"2017-07-13T11:31:41.0353603Z\",\"accountIds\":[123456,123457,123458],\"clientUserIds\":[\"A123456\",\"A123457\",\"A123458\"]}"

headers = { 
     'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/bulk/entitlements", payload, headers)

res = conn.getresponse()
data = res.read()

```

```javascript
Not available
```

> The above command returns a HTTP 204 upon success:

```json

```

This endpoint is available to allow you to bulk create access for multiple accounts in a single request.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/bulk/entitlements/</span>
</div>

### Request Parameters

 |  |  | 
--------- | ------- | ------- | 
`entitlementIdentifier` <br />The access the account should given| <span class="string">string</span> | <span class="required">Required</span> | 
`startDate` <br />The date at which the access should become active| <span style="font-weight:bold;color:#666;">dateTime</span> | <span class="required">Required</span> | 
`endDate` <br />The date at which access to the content should be deactivated.| <span style="font-weight:bold;color:#666;">dateTime</span> | <span class="required">Required</span> | 
`accountIds` <br />A collection of all accounts that should have access given, based upon accountId.| <span class="array">array[integer]</span> | <span class="required">No*</span> | 
`clientUserIds` <br />A collection of all accounts that should have access given, based upon ClientUserId| <span class="array">array[string]</span> | <span class="required">No*</span> | 


<aside class="info">It is required that either an array of accountIds or clientUserIds must be passed but it is not required to pass both.</aside>
