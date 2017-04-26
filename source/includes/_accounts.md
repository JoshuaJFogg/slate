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
  --url https://uat.mppglobal.com/api/accounts/123456 \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/123456");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/123456")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/123456")

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

conn.request("GET", "/api/accounts/123456", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/123456",
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
  "account": {
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
 }
```

Once an account has been created within the eSuite platform, it is possible to return the account resource using the REST API.
### URL Endpoint

`GET http://uat.mppglobal.com/api/accounts/123456`

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

## Edit Account

```shell
curl --request PUT \
  --url https://uat.mppglobal.com/api/accounts/123456 \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{""email":"john.smith@mppglobal.com","clientUserId":"mpp-123456","salutation":"Mr","firstName":"John","lastName":"Smith","phoneNumber":"01513287445","dateOfBirth":"1991-04-12T00:00:01","gender":"Male","addresses":[{"addressType":"Home","houseName":"Blosson Cottage","houseNumber":"12a","street":"Flower Street","townCity":"Garden","district":"Allotment","county":null,"postCode":"NE21ZZ","country":"United Kingdom"}],"customParameters":{"colour":"Blue","referrer":"Facebook"}}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/123456");
var request = new RestRequest(Method.PUT);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"email\":\"john.smith@mppglobal.com\",\"clientUserId\":\"mpp-123456\",\"salutation\":\"Mr\",\"firstName\":\"John\",\"lastName\":\"Smith\",\"phoneNumber\":\"01513287445\",\"dateOfBirth\":\"1991-04-12T00:00:01\",\"gender\":\"Male\",\"addresses\":[{\"addressType\":\"Home\",\"houseName\":\"Blosson Cottage\",\"houseNumber\":\"12a\",\"street\":\"Flower Street\",\"townCity\":\"Garden\",\"district\":\"Allotment\",\"county\":null,\"postCode\":\"NE21ZZ\",\"country\":\"United Kingdom\"}],\"customParameters\":{\"colour\":\"Blue\",\"referrer\":\"Facebook\"}}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/123456")
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

url = URI("https://uat.mppglobal.com/api/accounts/123456")

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

conn.request("PUT", "/api/accounts/123456", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/123456",
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

`PUT http://uat.mppglobal.com/api/accounts/123456`

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
  --url https://uat.mppglobal.com/api/accounts/123456 \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/123456");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/123456")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/123456")

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

conn.request("DELETE", "/api/accounts/123456", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/123456",
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

`DELETE http://uat.mppglobal.com/api/accounts/123456`


## Trigger Account Verification

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/123456/verify \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/123456/verify");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/123456/verify")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/123456/verify")

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

conn.request("POST", "/api/accounts/123456/verify", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/123456/verify",
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

`POST http://uat.mppglobal.com/api/accounts/123456/verify`

