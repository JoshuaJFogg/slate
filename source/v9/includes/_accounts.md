# Accounts

## Create Account

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"email":"johnsmith-api@mppglobal.com","password":"4034510a@!","clientUserId":"84AF2AAC-C1BD-4A93-AB08-57D2D7A54274"}"
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"email\":\"johnsmith-api@mppglobal.com\",\"password\":\"4034510a@!\",\"clientUserId\":\"84AF2AAC-C1BD-4A93-AB08-57D2D7A54274\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"email\":\"johnsmith-api@mppglobal.com\",\"password\":\"4034510a@!\",\"clientUserId\":\"84AF2AAC-C1BD-4A93-AB08-57D2D7A54274\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"email\":\"johnsmith-api@mppglobal.com\",\"password\":\"4034510a@!\",\"clientUserId\":\"84AF2AAC-C1BD-4A93-AB08-57D2D7A54274\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"email\":\"johnsmith-api@mppglobal.com\",\"password\":\"4034510a@!\",\"clientUserId\":\"84AF2AAC-C1BD-4A93-AB08-57D2D7A54274\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"email\":\"johnsmith-api@mppglobal.com\",\"password\":\"4034510a@!\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "accountId": 2032774,
  "resourceReference": "0010AL6OI8WQFGYUT0",
  "status": "Active",
  "email": "john.smith@mppglobal.com",
  "clientUserId": "mpp-123456",
  "salutation": "Mr",
  "firstName": "John",
  "lastName": "Smith",
  "phoneNumber": "01513287445",
  "dateOfBirth": "1991-04-12T00:00:01",
  "gender": "Male",
  "addresses": [
    {
      "addressType": "Home",
      "houseName": "Blosson Cottage",
      "houseNumber": "12a",
      "street": "Flower Street",
      "townCity": "Garden",
      "district": "Allotment",
      "county": null,
      "postCode": "NE21ZZ",
      "country": "United Kingdom"
    }
  ],
  "customParameters": {
    "colour": "Blue",
    "referrer": "Facebook"
  },
  "sessionToken": "702f5c37e2394db785ae1306ecce9750"
}
```

It is a requirement of the eSuite platform that an account be created in order to perform future actions such as payments and subscription purchases.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts</span>
</div>

### POST Parameters

 |  |  | 
--------- | ------- | ------- | 
`email` <br />The identifier used when eSuite is primary IDAM.| <span class="string">string</span> | <span class="required">Required</span> | 
`clientUserId` <br />The identifier used when eSuite is secondary IDAM. Once set this cannot be changed.| <span class="string">string</span> | <span class="required">Required</span> | 
`password` <br />The value provided by the account to pair with the email. | <span class="string">string</span> | <span class="required">Required</span> | 
`salutation` <br />Available values: Mr, Mrs, Miss and Ms.| <span class="string">string</span> |  | 
`firstName` <br />The first name associated to the account.| <span class="string">string</span> |  | 
`lastName` <br />The last name associated to the account.| <span class="string">string</span> |  | 
`phoneNumber` <br />The home phone number of the account.| <span class="string">string</span> |  | 
`mobileNumber` <br />The mobile number of the account (minus country code).| <span class="string">string</span> |  | 
`dateOfBirth` <br />The birthday of the account.| <span class="string">string</span> |  | 
`gender` <br />Available values: Male, Female and Unspecified.| <span class="string">string</span> |  | 
`addresses` <br />A collection of addresses bound to the account.| <span class="array">array</span> |  | 
`address \ addressType` <br />Available values: Home and Billing.| <span class="string">string</span> |  | 
`address \ houseName` <br />The name associated to the address.| <span class="string">string</span> |  | 
`address \ houseNumber` <br />The building number associated to the address.| <span class="string">string</span> |  | 
`address \ street` <br />The street associated to the address.| <span class="string">string</span> |  | 
`address \ townCity` <br />The town or city associated to the address| <span class="string">string</span> |  | 
`address \ district` <br />The district associated to the address| <span class="string">string</span> |  | 
`address \ state` <br />The state associated to the address| <span class="string">string</span> |  | 
`address \ county` <br />The county associated to the address| <span class="string">string</span> |  | 
`address \ postCode` <br />The post code associated to the address| <span class="string">string</span> |  | 
`address \ country` <br />The country the account resides| <span class="string">string</span> |  | 
`customParameters` <br />A collection of custom attributes stored against the account| <span class="dictionary">dictionary</span> |  | 

_* It is Required to pass either a email address or a clientUserId. It is possible to provide both._


## Retrieve Account

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}")

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

conn.request("GET", "/api/accounts/{accountId}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}",
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
    "accountId": 2032774,
    "resourceReference": "0010AL6OI8WQFGYUT0",
    "status": "Active",
    "email": "john.smith@mppglobal.com",
    "clientUserId": "mpp-123456",
    "salutation": "Mr",
    "firstName": "John",
    "lastName": "Smith",
    "phoneNumber": "01513287445",
    "dateOfBirth": "1991-04-12T00:00:01",
    "gender": "Male",
    "addresses": [
      {
        "addressType": "Home",
        "houseName": "Blosson Cottage",
        "houseNumber": "12a",
        "street": "Flower Street",
        "townCity": "Garden",
        "district": "Allotment",
        "county": null,
        "postCode": "NE21ZZ",
        "country": "United Kingdom"
      }
    ],
    "customParameters": {
      "colour": "Blue",
      "referrer": "Facebook"
    }
 }
```

Once an account has been created within the eSuite platform, it is possible to return the account resource using the REST API.
### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}</span>
</div>


### Response Parameters

 |  |  |  
--------- | ------- | ------- | 
`accountId` <br />AccountId referring to the account requested| <span class="integer">integer</span> |  | 
`resourceReferece` <br />Computational value of the accountId and the resource type| <span class="string">string</span> |  | 
`status` <br />The current status of the account.| <span class="string">string</span> |  | 
`email` <br />The identifier used when eSuite is primary IDAM.| <span class="string">string</span> |  | 
`clientUserId` <br />The identifier used when eSuite is secondary IDAM. Once set this cannot be changed.| <span class="string">string</span> |  | 
`password` <br />The value provided by the account to pair with the email. | <span class="string">string</span> |  | 
`salutation` <br />Available values: Mr, Mrs, Miss and Ms.| <span class="string">string</span> |  | 
`firstName` <br />The first name associated to the account.| <span class="string">string</span> |  | 
`lastName` <br />The last name associated to the account.| <span class="string">string</span> |  | 
`phoneNumber` <br />The home phone number of the account.| <span class="string">string</span> |  | 
`mobileNumber` <br />The mobile number of the account (minus country code).| <span class="string">string</span> |  | 
`dateOfBirth` <br />The birthday of the account.| <span class="string">string</span> |  | 
`gender` <br />Available values: Male, Female and Unspecified.| <span class="string">string</span> | | 
`addresses` <br />A collection of addresses bound to the account.| <span class="array">array</span> |  | 
`address \ addressType` <br />Available values: Home and Billing.| <span class="string">string</span> | | 
`address \ houseName` <br />The name associated to the address.| <span class="string">string</span> || 
`address \ houseNumber` <br />The building number associated to the address.| <span class="string">string</span> |  | 
`address \ street` <br />The street associated to the address.| <span class="string">string</span> |  | 
`address \ townCity` <br />The town or city associated to the address| <span class="string">string</span> | | 
`address \ district` <br />The district associated to the address| <span class="string">string</span> |  | 
`address \ state` <br />The state associated to the address| <span class="string">string</span> |  | 
`address \ county` <br />The county associated to the address| <span class="string">string</span> |  | 
`address \ postCode` <br />The post code associated to the address| <span class="string">string</span> | | 
`address \ country` <br />The country the account resides| <span class="string">string</span> |  | 
`customParameters` <br />A collection of custom attributes stored against the account| <span class="dictionary">dictionary</span> |  | 

## Update Account

```shell
curl --request PUT \
  --url https://uat.mppglobal.com/api/accounts/{accountId} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"email":"johnsmith-api+1@mppglobal.com","currentPassword":"4034510a@!","newPassword":"4034510aRFT453","firstName":"John","surname":"Smith"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}");
var request = new RestRequest(Method.PUT);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"email\":\"johnsmith-api+1@mppglobal.com\",\"currentPassword\":\"4034510a@!\",\"newPassword\":\"4034510aRFT453\",\"firstName\":\"John\",\"surname\":\"Smith\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/{accountId}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"email\":\"johnsmith-api+1@mppglobal.com\",\"currentPassword\":\"4034510a@!\",\"newPassword\":\"4034510aRFT453\",\"firstName\":\"John\",\"surname\":\"Smith\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"email\":\"johnsmith-api+1@mppglobal.com\",\"currentPassword\":\"4034510a@!\",\"newPassword\":\"4034510aRFT453\",\"firstName\":\"John\",\"surname\":\"Smith\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"email\":\"johnsmith-api+1@mppglobal.com\",\"currentPassword\":\"4034510a@!\",\"newPassword\":\"4034510aRFT453\",\"firstName\":\"John\",\"surname\":\"Smith\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("PUT", "/api/accounts/{accountId}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}",
  "method": "PUT",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"email\":\"johnsmith-api+1@mppglobal.com\",\"currentPassword\":\"4034510a@!\",\"newPassword\":\"4034510aRFT453\",\"firstName\":\"John\",\"surname\":\"Smith\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "accountId": 2032774,
  "resourceReference": "0010AL6OI8WQFGYUT0",
  "status": "Active",
  "email": "john.smith@mppglobal.com",
  "clientUserId": "mpp-123456",
  "salutation": "Mr",
  "firstName": "John",
  "lastName": "Smith",
  "phoneNumber": "01513287445",
  "dateOfBirth": "1991-04-12T00:00:01",
  "gender": "Male",
  "addresses": [
    {
      "addressType": "Home",
      "houseName": "Blosson Cottage",
      "houseNumber": "12a",
      "street": "Flower Street",
      "townCity": "Garden",
      "district": "Allotment",
      "county": null,
      "postCode": "NE21ZZ",
      "country": "United Kingdom"
    }
  ],
  "customParameters": {
    "colour": "Blue",
    "referrer": "Facebook"
  },
  "sessionToken": "702f5c37e2394db785ae1306ecce9750"
}
```

It is a requirement of the eSuite platform that an account be created in order to perform future actions such as payments and subscription purchases.

### URL Endpoint
<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-put">PUT</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}</span>
</div>


### PUT Parameters

 |  |  | 
--------- | ------- | ------- | 
`email` <br />The identifier used when eSuite is primary IDAM.| <span class="string">string</span> | <span class="required">Required</span> | 
`clientUserId` <br />The identifier used when eSuite is secondary IDAM. Once set this cannot be changed.| <span class="string">string</span> | <span class="required">Required</span> | 
`password` <br />The value provided by the account to pair with the email. | <span class="string">string</span> | <span class="required">Required</span> | 
`salutation` <br />Available values: Mr, Mrs, Miss and Ms.| <span class="string">string</span> |  | 
`firstName` <br />The first name associated to the account.| <span class="string">string</span> |  | 
`lastName` <br />The last name associated to the account.| <span class="string">string</span> |  | 
`phoneNumber` <br />The home phone number of the account.| <span class="string">string</span> |  | 
`mobileNumber` <br />The mobile number of the account (minus country code).| <span class="string">string</span> |  | 
`dateOfBirth` <br />The birthday of the account.| <span class="string">string</span> |  | 
`gender` <br />Available values: Male, Female and Unspecified.| <span class="string">string</span> |  | 
`addresses` <br />A collection of addresses bound to the account.| <span class="array">array</span> |  | 
`address \ addressType` <br />Available values: Home and Billing.| <span class="string">string</span> |  | 
`address \ houseName` <br />The name associated to the address.| <span class="string">string</span> |  | 
`address \ houseNumber` <br />The building number associated to the address.| <span class="string">string</span> |  | 
`address \ street` <br />The street associated to the address.| <span class="string">string</span> |  | 
`address \ townCity` <br />The town or city associated to the address| <span class="string">string</span> |  | 
`address \ district` <br />The district associated to the address| <span class="string">string</span> |  | 
`address \ state` <br />The state associated to the address| <span class="string">string</span> |  | 
`address \ county` <br />The county associated to the address| <span class="string">string</span> |  | 
`address \ postCode` <br />The post code associated to the address| <span class="string">string</span> |  | 
`address \ country` <br />The country the account resides| <span class="string">string</span> |  | 
`customParameters` <br />A collection of custom attributes stored against the account| <span class="dictionary">dictionary</span> |  | 




## Delete Account

```shell
curl --request DELETE \
  --url https://uat.mppglobal.com/api/accounts/{accountId} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/{accountId}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}")

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

conn.request("DELETE", "/api/accounts/{accountId}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}",
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

Calling this endpoint will result in the account being removed from the eSuite platform.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}</span>
</div>

## Search Accounts

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/ \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/")

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

conn.request("GET", "/api/accounts/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "totalNumberOfRecords": 1,
  "pageNumber": 1,
  "resultsPerPage": 50,
  "items": [
    {
      "account": {
        "accountId": 500000001,
        "resourceReference": "0010A3EL3S2MKRSGI1",
        "status": "Active",
        "email": "my-test@specsavers.com",
        "clientUserId": "014785487",
        "salutation": "Mr",
        "firstName": "Joshua",
        "lastName": "Fogg",
        "phoneNumber": "PhoneNumber",
        "mobileNumber": "",
        "dateOfBirth": "0001-01-01T00:00:00",
        "gender": "NotKnown",
        "addresses": [
          {
            "addressType": "Home",
            "houseName": "HouseName",
            "houseNumber": "HouseNumber",
            "street": "Street",
            "townCity": "TownCity",
            "district": "District",
            "county": "County",
            "postCode": "PostCode",
            "country": "Country"
          }
        ],
        "customParameters": {
          "StoreNumber": "42"
        }
      }
    }
  ]
}
```

This endpoint allows you to search for an account using the REST API. This is typically used when integrated into another system or managment console. It is not recommended that this endpoint be utilised using client-side authentiation.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/</span>
</div>

### Query Parameters
 |  |  |  
--------- | ------- | ------- | 
`emailAddress` <br />The email associated with an account| <span class="string">string</span> | | 
`clientUserId` <br />The unique identifier associated with one or more accounts| <span class="string">string</span> | | 
`accountName` <br />The name associated to an account. This should be first and surname concatenated.| <span class="string">string</span> | | 
`street` <br />Street associated to one or more accounts| <span class="string">string</span> | | 
`postCode` <br />Post code associated to one or more accounts| <span class="string">string</span> | | 
`country` <br />Country associated to one or more accounts| <span class="string">string</span> | | 
`state` <br />State associated to one or more accounts (US only)| <span class="string">string</span> | | 
`phoneNumber` <br />Street associated to one or more accounts| <span class="string">string</span> | | 
`dateOfBirth` <br />Street associated to one or more accounts| <span class="string">string</span> | | 
`rowsPerPage` <br />The number of account results to be returned| <span class="string">string</span> | | 
`pageNumber` <br />The result set requested| <span class="string">string</span> | | 

### Response Parameters

 |  |  |  
--------- | ------- | ------- | 
`totalNumberOfRecords` <br />Total number of accounts that have been found based on the request criteria| <span class="integer">integer</span> |  |
`pageNumber` <br />The current page of results being show| <span class="integer">integer</span> |  |
`resultsPerPage` <br />The number of results being shown| <span class="integer">integer</span> |  |
`items` <br />Collection of account resources| <span class="integer">integer</span> |  | 
`accountId` <br />AccountId referring to the account requested| <span class="integer">integer</span> |  | 
`resourceReferece` <br />Computational value of the accountId and the resource type| <span class="string">string</span> |  | 
`status` <br />The current status of the account.| <span class="string">string</span> |  | 
`email` <br />The identifier used when eSuite is primary IDAM.| <span class="string">string</span> |  | 
`clientUserId` <br />The identifier used when eSuite is secondary IDAM. Once set this cannot be changed.| <span class="string">string</span> |  | 
`password` <br />The value provided by the account to pair with the email. | <span class="string">string</span> |  | 
`salutation` <br />Available values: Mr, Mrs, Miss and Ms.| <span class="string">string</span> |  | 
`firstName` <br />The first name associated to the account.| <span class="string">string</span> |  | 
`lastName` <br />The last name associated to the account.| <span class="string">string</span> |  | 
`phoneNumber` <br />The home phone number of the account.| <span class="string">string</span> |  | 
`mobileNumber` <br />The mobile number of the account (minus country code).| <span class="string">string</span> |  | 
`dateOfBirth` <br />The birthday of the account.| <span class="string">dateTime</span> |  | 
`gender` <br />Available values: Male, Female and Unspecified.| <span class="string">string</span> | | 
`addresses` <br />A collection of addresses bound to the account.| <span class="array">array</span> |  | 
`address \ addressType` <br />Available values: Home and Billing.| <span class="string">string</span> | | 
`address \ houseName` <br />The name associated to the address.| <span class="string">string</span> || 
`address \ houseNumber` <br />The building number associated to the address.| <span class="string">string</span> |  | 
`address \ street` <br />The street associated to the address.| <span class="string">string</span> |  | 
`address \ townCity` <br />The town or city associated to the address| <span class="string">string</span> | | 
`address \ district` <br />The district associated to the address| <span class="string">string</span> |  | 
`address \ state` <br />The state associated to the address| <span class="string">string</span> |  | 
`address \ county` <br />The county associated to the address| <span class="string">string</span> |  | 
`address \ postCode` <br />The post code associated to the address| <span class="string">string</span> | | 
`address \ country` <br />The country the account resides| <span class="string">string</span> |  | 
`customParameters` <br />A collection of custom attributes stored against the account| <span class="dictionary">dictionary</span> |  | 



## Trigger Account Verification

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/verify \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/verify");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/verify")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/verify")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
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

conn.request("POST", "/api/accounts/{accountId}/verify", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/verify",
  "method": "POST",
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

It is a requirement of the eSuite platform that an account be created in order to perform future actions such as payments and subscription purchases.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/verify</span>
</div>

## Complete Account Verification

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/verify \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"verificationToken":"BE52ADA2064C4F9A9D90F28D066D1RFT"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/verify");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"verificationToken\":\"BE52ADA2064C4F9A9D90F28D066D1RFT\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/verify")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{\"verificationToken\":\"BE52ADA2064C4F9A9D90F28D066D1RFT\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/verify")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"verificationToken\":\"BE52ADA2064C4F9A9D90F28D066D1RFT\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"verificationToken\":\"BE52ADA2064C4F9A9D90F28D066D1RFT\"}"


headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0'
    }

conn.request("PATCH", "/api/accounts/verify", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/verify",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com"
  },
   "data": "{\"verificationToken\":\"BE52ADA2064C4F9A9D90F28D066D1RFT\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns a HTTP 204 confirming verification.


Following the receiving of a verification email, the link contained within will take the customer to a page which has integrated this API methods and pass the verification token to eSuite to verifiy the account.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/verify</span>
</div>


### Request Parameters

 |  |  |  
--------- | ------- | ------- | 
`verificationToken` <br />This parameter represents the token that was contained within the email sent to the account.| <span class="string">string</span> | <span class="required">Required</span> | 

## Trigger Forgotten Password

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/forgotten-password \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"emailAddress":"john.smith@mppglobal.com"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/forgotten-password");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json","{\"emailAddress\":\"john.smith@mppglobal.com\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/forgotten-password")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"emailAddress\":\"john.smith@mppglobal.com\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/forgotten-password")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"emailAddress\":\"john.smith@mppglobal.com\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"emailAddress\":\"john.smith@mppglobal.com\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/forgotten-password", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/forgotten-password",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"emailAddress\":\"john.smith@mppglobal.com\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns a HTTP 204 confirming verification.


In the event a customer is unable to access their account due to forgetting their credentials, this API method should be called to trigger an email to be sent to the customers which contains a link that will allow them to reset their password.
### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/forgotten-password</span>
</div>

### Request Parameters

 |  |  |
--------- | ------- | ------- |
`emailAddress` <br />The email address associated to the customers account | <span class="string">string</span> | <span class="required">Required</span> |

## Reset Password

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/update-password \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-sessionid: BE52ADA2064C4F9A9D90F28D066D1RFT' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --data '{"password":"ReallyStr0ngP@ss0rd","login":true}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/update-password");
var request = new RestRequest(Method.PATCH);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT");
request.AddParameter("application/json", "{\"password\":\"ReallyStr0ngP@ss0rd\",\"login\":true}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/update-password")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"password\":\"ReallyStr0ngP@ss0rd\",\"login\":true}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/update-password")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword',
request["x-sessionid"] = 'BE52ADA2064C4F9A9D90F28D066D1RFT',
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"password\":\"ReallyStr0ngP@ss0rd\",\"login\":true}"


response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"password\":\"ReallyStr0ngP@ss0rd\",\"login\":true}"


headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    "x-sessionid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/update-password", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/update-password",
  "method": "PATCH",
  "headers": {
    "x-sessionid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"password\":\"ReallyStr0ngP@ss0rd\",\"login\":true}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns the following JSON document if login was provided as true:

```json
{
  "sessionToken" : "b6dab2afbc4d42a385746a51b3bd2ed6"
}
```
If an account has requested to reset their password, they will have recieved and email with a session token. This token should be provided into this endpoint to allow the resetting of the password. This endpoint cannot be used for general password updated. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/update-password</span>
</div>

### Request Parameters

 |  |  |  
--------- | ------- | ------- | 
`password` <br />The new password for the account.| <span class="string">string</span> | <span class="required">Required</span> | 
`login` <br />An indication as to whether the customer should be provided a session following password update.| <span class="bool">bool</span> |  | 

## Retrieve Transaction Summary

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/transaction-summary \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/transaction-summary");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/transaction-summary")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/transaction-summary")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword',
request["x-sessionid"] = 'BE52ADA2064C4F9A9D90F28D066D1RFT',
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

conn.request("GET", "/api/accounts/{accountId}/transaction-summary", payload)

res = conn.getresponse()
data = res.read()
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/transaction-summary",
  "method": "GET",
  "headers": {
    "x-sessionid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
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
  "totalCustomerValue": [
    {
      "totalValue": 56.20,
      "currency": "USD"
    }
  ],
  "totalPaymentsToDate": [
    {
      "currency": "USD",
      "quantity": 2,
      "totalValue": 18.00,
      "averageValue": 9.00
    }
  ],
  "totalRefundsToDate": [
    {
      "currency": "USD",
      "quantity": 3,
      "totalValue": 21.00,
      "averageValue": 7.00
    }
  ],
  "outstandingPaymentsToDate": [
    {
      "currency": "USD",
      "quantity": 2,
      "totalValue": 21.00,
      "averageValue": 11.50
    }
  ],
  "outstandingCreditBalance": [
    {
      "totalValue": 6.27,
      "currency": "USD"
    }
  ]
}
```

Calling this endpoint will provide a breakdown of the accounts transaction summary both historically and future dated.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/accounts/{accountId}/transaction-summary</span>
</div>

### Response Parameters
 |  |  |  
--------- | ------- | ------- | 
`totalCustomerValue` <br />Customer value broken down by currency | <span class="object">object</span> |
`totalCustomerValue \ totalValue` <br /> The sum of all payments minus any refunds | <span class="decimal">decimal</span> |
`totalCustomerValue \ currency`<br /> The currency the value represents | <span class="string">string</span> |
`totalPaymentsToDate`<br /> Total number of payments taken, broken down by currency | <span class="integer">integer</span>|
`totalPaymentsToDate \ totalValue`<br /> The sum of all payments taken against the account |<span class="decimal">decimal</span>|
`totalPaymentsToDate \ averageValue`<br /> The average transaction amount |<span class="decimal">decimal</span>|
`totalPaymentsToDate \ currency`<br /> The currency the value represents | <span class="string">string</span> |
`totalPaymentsToDate \ quantity`<br /> The number of payments which have been taken against the account | <span class="integer">integer</span>|
`totalRefundsToDate`<br /> All refunds applied, broken down by currency | <span class="object">object</span> |
`totalRefundsToDate \ totalValue`<br /> The sum of all refunds against the account |<span class="decimal">decimal</span>|
`totalRefundsToDate \ averageValue`<br /> The average transaction refund amount |<span class="decimal">decimal</span>|
`totalRefundsToDate \ currency`<br /> The currency the value represents | <span class="string">string</span> |
`totalRefundsToDate \ quantity`<br /> Number of refunds that have taken place | <span class="integer">integer</span>|
`outstandingPaymentsToDate` <br />All outstanding payments, broken down by currency | <span class="object">object</span> |
`outstandingPaymentsToDate \ totalValue`<br /> The sum of all payments yet to be taken against the account  |<span class="decimal">decimal</span>|
`outstandingPaymentsToDate \ averageValue`<br /> The average transaction amount |<span class="decimal">decimal</span>|
`outstandingPaymentsToDate \ currency`<br /> The currency the value represents | <span class="string">string</span> |
`outstandingPaymentsToDate \ quantity`<br /> Total number of outstanding payments | <span class="integer">integer</span>|
`outstandingCreditBalance`<br /> All outstanding credit balances broken down by currency |<span class="object">object</span> |
`outstandingCreditBalance \ totalValue`<br /> The total amount credit on the account |<span class="decimal">decimal</span>|
`outstandingCreditBalance \ currency`<br /> The currency the value represents | <span class="string">string</span> |



