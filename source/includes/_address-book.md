# Address Book

## CRUD: Create Address

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/addresses \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"houseName":"Orange House","houseNumber":"119","street":"Colourful Street","townCity":"East Village","district":null,"state":null,"county":"Merseyside","postCode":"CH11 1GV","country":"United Kingdom","isDefault":true}'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/addresses");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"houseName\":\"Orange House\",\"houseNumber\":\"119\",\"street\":\"Colourful Street\",\"townCity\":\"East Village\",\"district\":null,\"state\":null,\"county\":\"Merseyside\",\"postCode\":\"CH11 1GV\",\"country\":\"United Kingdom\",\"isDefault\":true}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/addresses")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"houseName\":\"Orange House\",\"houseNumber\":\"119\",\"street\":\"Colourful Street\",\"townCity\":\"East Village\",\"district\":null,\"state\":null,\"county\":\"Merseyside\",\"postCode\":\"CH11 1GV\",\"country\":\"United Kingdom\",\"isDefault\":true}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/addresses")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"houseName\":\"Orange House\",\"houseNumber\":\"119\",\"street\":\"Colourful Street\",\"townCity\":\"East Village\",\"district\":null,\"state\":null,\"county\":\"Merseyside\",\"postCode\":\"CH11 1GV\",\"country\":\"United Kingdom\",\"isDefault\":true}"
response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"houseName\":\"Orange House\",\"houseNumber\":\"119\",\"street\":\"Colourful Street\",\"townCity\":\"East Village\",\"district\":null,\"state\":null,\"county\":\"Merseyside\",\"postCode\":\"CH11 1GV\",\"country\":\"United Kingdom\",\"isDefault\":true}"

headers = {
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/{accountId}/addresses", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/addresses",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"houseName\":\"Orange House\",\"houseNumber\":\"119\",\"street\":\"Colourful Street\",\"townCity\":\"East Village\",\"district\":null,\"state\":null,\"county\":\"Merseyside\",\"postCode\":\"CH11 1GV\",\"country\":\"United Kingdom\",\"isDefault\":true}"
  }

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
> The resource created is returned in the *Location* header of the response


Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/addresses</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
houseName | string | mandatory* | The name associated to the building |
houseNumber | string |mandatory* | The building number associated to the address |
street | string |mandatory | The street the address is located |
townCity | string |mandatory | The town or city the address is associated |
district | string |optional | The district associated with the address |
state | string |optional | The state that the address is located |
county | string |optional | The county the address is associated |
postCode | string |mandatory | The postcode of the address that has been added |
country | string |mandatory | The country the address is specific to |
isDefault | boolean |optional | An indication as to whether the address is the default address for the account |

*Either houseName or houseNumber is required but both are not mandatory.





## CRUD: Retrieve Address Book

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/addresses \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/addresses");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/addresses")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/addresses")

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

conn.request("GET", "/api/accounts/{accountId}/addresses", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/addresses",
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
  "addressBook": [
    {
      "addressIdentifier": "0010D04D2E807PQ953",
      "houseName": "Orange House",
      "houseNumber": "119",
      "street": "Colourful Street",
      "townCity": "East Village",
      "district": "",
      "state": "",
      "county": "Merseyside",
      "postCode": "CH11 1GV",
      "country": "United Kingdom",
      "isDefault": true
    }
  ]
}
```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/addresses</span>
</div>

### Response Parameters

Parameter | Type | Description | 
--------- | ------- | ------- | 
addressBook | array[object] | The list of addresses |
addressIdentifier | string | The address identifier that should be used to identify which address is required in future API requests |
houseName | string | The name associated to the building |
houseNumber | string | The building number associated to the address |
street | string | The street the address is located |
townCity | string | The town or city the address is associated |
district | string | The district associated with the address |
state | string | The state that the address is located |
county | string | The county the address is associated |
postCode | string | The postcode of the address that has been added |
country | string | The country the address is specific to |
isDefault | boolean | An indication as to whether the address is the default address for the account |





