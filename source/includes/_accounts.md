# Accounts

## Create Account

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{""email":"john.smith@mppglobal.com","clientUserId":"mpp-123456","salutation":"Mr","firstName":"John","lastName":"Smith","phoneNumber":"01513287445","dateOfBirth":"1991-04-12T00:00:01","gender":"Male","addresses":[{"addressType":"Home","houseName":"Blosson Cottage","houseNumber":"12a","street":"Flower Street","townCity":"Garden","district":"Allotment","county":null,"postCode":"NE21ZZ","country":"United Kingdom"}],"customParameters":{"colour":"Blue","referrer":"Facebook"}}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}")
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
request.body = "{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}"

headers = {
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
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
  "data": "{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}"
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

`POST http://uat.mppglobal.com/api/accounts`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
email | string | Yes* | The identifier used when eSuite is primary IDAM.
clientUserId | string | Yes* | The identifier used when eSuite is secondary IDAM. Once set this cannot be changed.
password | string | Yes | The value provided by the account to pair with the email. 
salutation | string | No | Available values: Mr, Mrs, Miss and Ms.
firstName | string | Yes | The first name associated to the account.
lastName | string | Yes | The last name associated to the account.
phoneNumber | string | Yes | The home phone number of the account.
mobileNumber | string | Yes | The mobile number of the account (minus country code).
dateOfBirth | dateTime | Yes | The birthday of the account.
gender | string | Yes | Available values: Male, Female and Unspecified.
addresses | array | Yes | A collection of addresses bound to the account.
address > addressType | string | Yes | Available values: Home and Billing.
address > houseName | string | Yes | The name associated to the address.
address > houseNumber | string | Yes | The building number associated to the address.
address > street | string | Yes | The street associated to the address.
address > townCity | string | Yes | The town or city associated to the address
address > district | string | No | The districtassociated to the address
address > state | string | No | The state associated to the address
address > county | string | No | The county associated to the address
address > postCode | string | Yes | The post code associated to the address
address > country | string | Yes | The country the account resides
customParameters | dictionary | No | A collection of custom attributes stored against the account

_* It is mandatory to pass either an email address or a clientUserId. It is possible to provide both._


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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
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

`GET http://uat.mppglobal.com/api/accounts/{accountId}`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
email | string | Yes* | The identifier used when eSuite is primary IDAM.
clientUserId | string | Yes* | The identifier used when eSuite is secondary IDAM. Once set this cannot be changed.
password | string | Yes | The value provided by the account to pair with the email. 
salutation | string | No | Available values: Mr, Mrs, Miss and Ms.
firstName | string | Yes | The first name associated to the account.
lastName | string | Yes | The last name associated to the account.
phoneNumber | string | Yes | The home phone number of the account.
mobileNumber | string | Yes | The mobile number of the account (minus country code).
dateOfBirth | dateTime | Yes | The birthday of the account.
gender | string | Yes | Available values: Male, Female and Unspecified.
addresses | array | Yes | A collection of addresses bound to the account.
address > addressType | string | Yes | Available values: Home and Billing.
address > houseName | string | Yes | The name associated to the address.
address > houseNumber | string | Yes | The building number associated to the address.
address > street | string | Yes | The street associated to the address.
address > townCity | string | Yes | The town or city associated to the address
address > district | string | No | The districtassociated to the address
address > state | string | No | The state associated to the address
address > county | string | No | The county associated to the address
address > postCode | string | Yes | The post code associated to the address
address > country | string | Yes | The country the account resides
customParameters | dictionary | No | A collection of custom attributes stored against the account

## Update Account

```shell
curl --request PUT \
  --url https://uat.mppglobal.com/api/accounts/{accountId} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{""email":"john.smith@mppglobal.com","clientUserId":"mpp-123456","salutation":"Mr","firstName":"John","lastName":"Smith","phoneNumber":"01513287445","dateOfBirth":"1991-04-12T00:00:01","gender":"Male","addresses":[{"addressType":"Home","houseName":"Blosson Cottage","houseNumber":"12a","street":"Flower Street","townCity":"Garden","district":"Allotment","county":null,"postCode":"NE21ZZ","country":"United Kingdom"}],"customParameters":{"colour":"Blue","referrer":"Facebook"}}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}");
var request = new RestRequest(Method.PUT);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/{accountId}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}")
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
request.body = "{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}"

headers = {
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
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
  "data": "{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}"
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

`PUT http://uat.mppglobal.com/api/accounts/{accountId}`

### PUT Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
email | string | Yes* | The identifier used when eSuite is primary IDAM.
clientUserId | string | Yes* | The identifier used when eSuite is secondary IDAM. Once set this cannot be changed.
password | string | Yes | The value provided by the account to pair with the email. 
salutation | string | No | Available values: Mr, Mrs, Miss and Ms.
firstName | string | Yes | The first name associated to the account.
lastName | string | Yes | The last name associated to the account.
phoneNumber | string | Yes | The home phone number of the account.
mobileNumber | string | Yes | The mobile number of the account (minus country code).
dateOfBirth | dateTime | Yes | The birthday of the account.
gender | string | Yes | Available values: Male, Female and Unspecified.
addresses | array | Yes | A collection of addresses bound to the account.
address > addressType | string | Yes | Available values: Home and Billing.
address > houseName | string | Yes | The name associated to the address.
address > houseNumber | string | Yes | The building number associated to the address.
address > street | string | Yes | The street associated to the address.
address > townCity | string | Yes | The town or city associated to the address
address > district | string | No | The districtassociated to the address
address > state | string | No | The state associated to the address
address > county | string | No | The county associated to the address
address > postCode | string | Yes | The post code associated to the address
address > country | string | Yes | The country the account resides
customParameters | dictionary | No | A collection of custom attributes stored against the account

_* It is mandatory to pass either an email address or a clientUserId. It is possible to provide both._


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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
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

It is a requirement of the eSuite platform that an account be created in order to perform future actions such as payments and subscription purchases.

### URL Endpoint

`DELETE http://uat.mppglobal.com/api/accounts/{accountId}`


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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
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

`POST http://uat.mppglobal.com/api/accounts/{accountId}/verify`

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
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

`PATCH http://uat.mppglobal.com/api/accounts/verify`

### Request Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
verificationToken | string | Yes | This parameter represents the token that was contained within the email sent to the account.

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
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

`POST http://uat.mppglobal.com/api/accounts/forgotten-password`

### Request Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
emailAddress | string | Yes | The email address associated to the customers account

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    "x-sessionid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    'x-version': "9.0.0",
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

### HTTP Request

`PATCH http://uat.mppglobal.com/api/accounts/update-password`

### Request Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
password | string | Yes | The new password for the account.
login | boolean | Yes | An indication as to whether the customer should be provided a session following password update.

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
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
      "totalValue": 56.2,
      "currency": "USD"
    }
  ],
  "totalPaymentsToDate": [
    {
      "currency": "USD",
      "quantity": 2,
      "totalValue": 18,
      "averageValue": 9
    }
  ],
  "totalRefundsToDate": [
    {
      "currency": "USD",
      "quantity": 3,
      "totalValue": 21,
      "averageValue": 7
    }
  ],
  "outstandingPaymentsToDate": [
    {
      "currency": "USD",
      "quantity": 2,
      "totalValue": 21,
      "averageValue": 11.5
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

`GET http://uat.mppglobal.com/accounts/{accountId}/transaction-summary`

### Parameters

Parameter | Description | 
--------- | ------- | 
totalCustomerValue | Customer value broken down by currency | 
totalCustomerValue > totalValue | The sum of all payments minus any refunds |
totalCustomerValue > currency | The currency the value represents | 
totalPaymentsToDate | Total number of payments taken, broken down by currency | 
totalPaymentsToDate > totalValue | The sum of all payments taken against the account |
totalPaymentsToDate > averageValue | The average transaction amount |
totalPaymentsToDate > currency | The currency the value represents | 
totalPaymentsToDate > quantity | The number of payments which have been taken against the account | 
totalRefundsToDate | All refunds applied, broken down by currency | 
totalRefundsToDate > totalValue | The sum of all refunds against the account |
totalRefundsToDate > averageValue | The average transaction refund amount |
totalRefundsToDate > currency | The currency the value represents | 
totalRefundsToDate > quantity | integer | 
outstandingPaymentsToDate | All outstanding payments, broken down by currency | 
outstandingPaymentsToDate > totalValue | The sum of all payments yet to be taken against the account  |
outstandingPaymentsToDate > averageValue | The average transaction amount |
outstandingPaymentsToDate > currency | The currency the value represents | 
outstandingPaymentsToDate > quantity | Total number of outstanding payments | 
outstandingCreditBalance | All outstanding credit balances broken down by currency |
outstandingCreditBalance > totalValue | The total amount credit on the account |
outstandingCreditBalance > currency | The currency the value represents | 


