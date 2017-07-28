# External Identity Providers

## Retrieve Available Providers

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/external-providers \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/external-providers");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/external-providers")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/external-providers")

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

conn.request("GET", "/api/accounts/{accountId}/external-providers", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/external-providers",
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
  "availableProviders": [
    {
      "providerName": "Facebook",
      "accountLinked": true
    },
	{
      "providerName": "Twitter",
      "accountLinked": false		
	}
  ]
}
```

This endpoint provides a list of all available external providers that are available to the account on your instance of eSuite. The response also details whether the account has been linked to the external provider also.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/external-providers</span>
</div>

### Response Parameters

Parameter | Type | Description | 
--------- | ------- | ------- | 
`availableProviders` | array[object] | 
`availableProviders` > `providerName` | string | The name of the external provider
`availableProviders` > `accountLinked` | boolean | An indication as to whether the account has been linked to this provider


## Authenticate via Facebook

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/authenticate/external-providers/facebook \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"facebookRedirectURI":"https://uat.mppglobal.com","authorisationCode":"123FRDV56G","accessToken":"EAARUdAzQ9UABAOPiYCyZB","applicationIdentifier":"fc7cc423-dd26-4d38-bd18-52e5dae8a45b"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/facebook");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"facebookRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/facebook")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"facebookRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/facebook")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"facebookRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"facebookRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "api/accounts/authenticate/external-providers/facebook", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "/api/accounts/authenticate/external-providers/facebook",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"facebookRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "status": "NoAccountMatch",
  "sessionToken": "6640ffaf3z954fdf8ba4342b51265e05",
  "providerProfileDetails": {
    "accountId": 123456,
    "resourceReference": "ResourceReference",
    "firstName": "Joe",
    "surname": "Smith",
    "emailAddress": "developers@eSuite.com"
  }
}
```

An account is able to authenticate using their Facebook account and then retrieve information that will allow eSuite to create an account off those details stored with Facebook.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/external-providers/facebook</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`facebookRedirectURI` | string | Yes/No | The location which should be called for validation of the code and token provided
`authorisationCode` | string | Yes/No | Code provided by Facebook
`accessToken` | string | Yes/No | Code provided by Facebook
`applicationIdentifier` | string | Yes/No | The identifier for the eSuite application that the account is using



## Create Account via SSO

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "/api/accounts/external-providers",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
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
  },
  "sessionToken": "702f5c37e2394db785ae1306ecce9750"
}
```

If during the authentication process with Facebook, eSuite deems the Facebook account is not currently registered in eSuite the account is required to be created within eSuite.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/external-providers</span>
</div>

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`email` | string | Yes* | The identifier used when eSuite is primary IDAM.
`clientUserId` | string | Yes* | The identifier used when eSuite is secondary IDAM. Once set this cannot be changed.
`password` | string | Yes | The value provided by the account to pair with the email. 
`salutation` | string | No | Available values: Mr, Mrs, Miss and Ms.
`firstName` | string | Yes | The first name associated to the account.
`lastName` | string | Yes | The last name associated to the account.
`phoneNumber` | string | Yes | The home phone number of the account.
`mobileNumber` | string | Yes | The mobile number of the account (minus country code).
`dateOfBirth` | dateTime | Yes | The birthday of the account.
`gender` | string | Yes | Available values: Male, Female and Unspecified.
`addresses` | array | Yes | A collection of addresses bound to the account.
`address` > `addressType` | string | Yes | Available values: Home and Billing.
`address` > `houseName` | string | Yes | The name associated to the address.
`address` > `houseNumber` | string | Yes | The building number associated to the address.
`address` > `street` | string | Yes | The street associated to the address.
`address` > `townCity` | string | Yes | The town or city associated to the address
`address` > `district` | string | No | The districtassociated to the address
`address` > `state` | string | No | The state associated to the address
`address` > `county` | string | No | The county associated to the address
`address` > `postCode` | string | Yes | The post code associated to the address
`address` > `country` | string | Yes | The country the account resides
`customParameters` | dictionary | No | A collection of custom attributes stored against the account
`sessionToken` | string | No | A session token linked to the account created


## Link to Facebook

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "/api/accounts/{accountId}/link/external-providers/facebook",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"facebookRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "status" : "NewLink"
}
```

This endpoint allows you to link an existing eSuite account to their Facebook profile.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/link/external-providers/facebook</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`facebookRedirectURI` | string | Yes/No | The location which should be called for validation of the code and token provided
`authorisationCode` | string | Yes/No | Code provided by Facebook
`accessToken` | string | Yes/No | Code provided by Facebook
`applicationIdentifier` | string | Yes/No | The identifier for the eSuite application that the account is using