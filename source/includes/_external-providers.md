# External Identity Providers

## Retrieve Available Providers

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/external-providers \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/external-providers");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountReference}/external-providers")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/external-providers")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '10.0.0'
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
    'x-version': '10.0.0'
    }

conn.request("GET", "/api/accounts/{accountReference}/external-providers", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/external-providers",
  "method": "GET",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "10.0.0",
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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/external-providers</span>
</div>

### Response Parameters

 |  |  
--------- | ------- | 
`availableProviders` <br />| <span class="array">array[object]</span> | 
`availableProviders \ providerName` <br />The name of the external provider| <span class="string">string</span> | 
`availableProviders \ accountLinked` <br />An indication as to whether the account has been linked to this provider| <span class="bool">bool</span> |




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
    "x-version": "10.0.0",
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
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/external-providers</span>
</div>

### Response Parameters

 |  |  |  
--------- | ------- | ------- | 
`email` <br />The identifier used when eSuite is primary IDAM.| <span class="string">string</span> | <span class="required">Yes*</span> | 
`clientUserId` <br />The identifier used when eSuite is secondary IDAM. Once set this cannot be changed.| <span class="string">string</span> | <span class="required">Yes*</span> | 
`password` <br />The value provided by the account to pair with the email. | <span class="string">string</span> | <span class="required">Yes</span> | 
`salutation` <br />Available values: Mr, Mrs, Miss and Ms.| <span class="string">string</span> |  | 
`firstName` <br />The first name associated to the account.| <span class="string">string</span> | <span class="required">Yes</span> | 
`lastName` <br />The last name associated to the account.| <span class="string">string</span> | <span class="required">Yes</span> | 
`phoneNumber` <br />The home phone number of the account.| <span class="string">string</span> | <span class="required">Yes</span> | 
`mobileNumber` <br />The mobile number of the account (minus country code).| <span class="string">string</span> | <span class="required">Yes</span> | 
`dateOfBirth` <br />The birthday of the account.| dateTime | <span class="required">Yes</span> | 
`gender` <br />Available values: Male, Female and Unspecified.| <span class="string">string</span> | <span class="required">Yes</span> | 
`addresses` <br />A collection of addresses bound to the account.| <span class="array">array</span> | <span class="required">Yes</span> | 
`address \ addressType` <br />Available values: Home and Billing.| <span class="string">string</span> | <span class="required">Yes</span> | 
`address \ houseName` <br />The name associated to the address.| <span class="string">string</span> | <span class="required">Yes</span> | 
`address \ houseNumber` <br />The building number associated to the address.| <span class="string">string</span> | <span class="required">Yes</span> | 
`address \ street` <br />The street associated to the address.| <span class="string">string</span> | <span class="required">Yes</span> | 
`address \ townCity` <br />The town or city associated to the address| <span class="string">string</span> | <span class="required">Yes</span> | 
`address \ district` <br />The district associated to the address| <span class="string">string</span> |  | 
`address \ state` <br />The state associated to the address| <span class="string">string</span> |  | 
`address \ county` <br />The county associated to the address| <span class="string">string</span> |  | 
`address \ postCode` <br />The post code associated to the address| <span class="string">string</span> | <span class="required">Yes</span> | 
`address \ country` <br />The country the account resides| <span class="string">string</span> | <span class="required">Yes</span> | 
`customParameters` <br />A collection of custom attributes stored against the account| <span class="dictionary">dictionary</span> |  | 
`sessionToken` <br /> A session token linked to the account created| <span class="string">string</span> |  |


## Authenticate via Facebook

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/authenticate/external-providers/facebook \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"facebookRedirectURI":"https://uat.mppglobal.com","authorisationCode":"123FRDV56G",
  "accessToken":"EAARUdAzQ9UABAOPiYCyZB","applicationIdentifier":"fc7cc423-dd26-4d38-bd18-52e5dae8a45b"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/facebook");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"facebookRedirectURI\":\"https://uat.mppglobal.com\"
,\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/facebook")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "10.0.0")
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
request["x-version"] = '10.0.0'
request.body = "{\"facebookRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\"
,\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"

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
    'x-version': '10.0.0',
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
    "x-version": "10.0.0",
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
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/external-providers/facebook</span>
</div>

### POST Parameters

 |  |  |  
--------- | ------- | ------- | 
`facebookRedirectURI` <br />The location which should be called for validation of the code and token provided| <span class="string">string</span> | <span class="required">Required</span> | 
`authorisationCode` <br />Code provided by Facebook| <span class="string">string</span> | <span class="required">Required</span> | 
`accessToken` <br />Code provided by Facebook| <span class="string">string</span> | <span class="required">Required</span> | 
`applicationIdentifier` <br />The identifier for the eSuite application that the account is using| <span class="string">string</span> | <span class="required">Required</span> | 



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
  "url": "/api/accounts/{accountReference}/link/external-providers/facebook",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "10.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"facebookRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\"
  ,\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"
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
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/link/external-providers/facebook</span>
</div>

### POST Parameters

 |  |  |  
--------- | ------- | ------- | 
`facebookRedirectURI` <br />The location which should be called for validation of the code and token provided| <span class="string">string</span> | <span class="required">Yes/No</span> | 
`authorisationCode` <br />Code provided by Facebook| <span class="string">string</span> | <span class="required">Yes/No</span> | 
`accessToken` <br />Code provided by Facebook| <span class="string">string</span> | <span class="required">Yes/No</span> | 
`applicationIdentifier` <br />The identifier for the eSuite application that the account is using| <span class="string">string</span> | <span class="required">Yes/No</span> | 



## Authenticate via Yahoo Japan

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/authenticate/external-providers/yahoo-jp \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"yahooJapanRedirectURL":"https://uat.mppglobal.com","authorisationCode":"123FRDV56G","accessToken":"EAARUdAzQ9UABAOPiYCyZB","applicationIdentifier":"fc7cc423-dd26-4d38-bd18-52e5dae8a45b"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/yahoo-japan");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"yahooJapanRedirectURL\":\"https://uat.mppglobal.com\"
,\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/yahoo-jp")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "10.0.0")
  .header("content-type", "application/json")
  .body("{\"yahooJapanRedirectURL\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/yahoo-jp")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '10.0.0'
request.body = "{\"yahooJapanRedirectURL\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\"
,\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"yahooJapanRedirectURL\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "10.0.0",
    'content-type': "application/json" }

conn.request("POST", "api/accounts/authenticate/external-providers/yahoo-jp", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "/api/accounts/authenticate/external-providers/yahoo-jp",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "10.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"yahooJapanRedirectURL\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"
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
    "resourceReference": "ResourceReference",
    "firstName": "Joe",
    "surname": "Smith",
    "emailAddress": "developers@eSuite.com"
  }
}
```

An account is able to authenticate using their Yahoo Japan account and then retrieve information that will allow eSuite to create an account off those details stored with Yahoo Japan.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/external-providers/yahoo-jp</span>
</div>

### POST Parameters

 |  |  |  
--------- | ------- | ------- | 
`yahooJapanRedirectURL` <br />The location which should be called for validation of the code and token provided| <span class="string">string</span> | <span class="required">Yes/No</span> | 
`authorisationCode` <br />If authorization is obtained by the user, it redirects the user to the previously registered return URL, and passes the authorization code and the specified state to the client| <span class="string">string</span> | <span class="required">Yes/No</span> | 
`accessToken` <br />The Token endpoint authenticates the client and returns an access token | <span class="string">string</span> | <span class="required">Yes/No</span> | 
`applicationIdentifier` <br />The identifier for the eSuite application that the account is using| <span class="string">string</span> | <span class="required">Yes/No</span> | 



## Link to Yahoo Japan

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
  "url": "/api/accounts/link/external-providers/facebook",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "10.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"yahooJapanRedirectURL\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"
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

This endpoint allows you to link an existing eSuite account to their Yahoo Japan profile.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/link/external-providers/yahoo-jp</span>
</div>

### POST Parameters

 |  |  |  
--------- | ------- | ------- | 
`yahooJapanRedirectURL` <br />The location which should be called for validation of the code and token provided| <span class="string">string</span> | <span class="required">Required</span> | 
`authorisationCode` <br />Code provided by Yahoo Japan| <span class="string">string</span> | <span class="required">Required</span> | 
`accessToken` <br />Code provided by Yahoo Japan| <span class="string">string</span> | <span class="required">Required</span> | 
`applicationIdentifier` <br />The identifier for the eSuite application that the account is using| <span class="string">string</span> | <span class="required">Required</span> | 



## Authenticate via Google

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/authenticate/external-providers/google \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"googleRedirectURI":"https://uat.mppglobal.com","authorisationCode":"123FRDV56G",
  "accessToken":"EAARUdAzQ9UABAOPiYCyZB","applicationIdentifier":"fc7cc423-dd26-4d38-bd18-52e5dae8a45b"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/google");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"googleRedirectURI\":\"https://uat.mppglobal.com\"
,\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/google")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "10.0.0")
  .header("content-type", "application/json")
  .body("{\"googleRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/authenticate/external-providers/google")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '10.0.0'
request.body = "{\"googleRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"googleRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\",\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "10.0.0",
    'content-type': "application/json" }

conn.request("POST", "api/accounts/authenticate/external-providers/google", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "/api/accounts/authenticate/external-providers/google",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "10.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"googleRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\"
  ,\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"
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
    "resourceReference": "ResourceReference",
    "firstName": "Joe",
    "surname": "Smith",
    "emailAddress": "developers@eSuite.com"
  }
}
```

An account is able to authenticate using their Google account and then retrieve information that will allow eSuite to create an account off those details stored with Google.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/external-providers/google</span>
</div>

### POST Parameters

 |  |  |  
--------- | ------- | ------- | 
`googleRedirectURI` <br />The location which should be called for validation of the code and token provided| <span class="string">string</span> | <span class="required">Required</span> | 
`authorisationCode` <br />Code provided by Google| <span class="string">string</span> | <span class="required">Required</span> | 
`accessToken` <br />Code provided by Google| <span class="string">string</span> | <span class="required">Required</span> | 
`applicationIdentifier` <br />The identifier for the eSuite application that the account is using| <span class="string">string</span> | <span class="required">Required</span> | 



## Link to Google

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
  "url": "/api/accounts/{accountReference}/link/external-providers/google",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "10.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"googleRedirectURI\":\"https://uat.mppglobal.com\",\"authorisationCode\":\"123FRDV56G\"
  ,\"accessToken\":\"EAARUdAzQ9UABAOPiYCyZB\",\"applicationIdentifier\":\"fc7cc423-dd26-4d38-bd18-52e5dae8a45b\"}"
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

This endpoint allows you to link an existing eSuite account to their Google profile.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/link/external-providers/google</span>
</div>

### POST Parameters

 |  |  |  
--------- | ------- | ------- | 
`googleRedirectURI` <br />The location which should be called for validation of the code and token provided| <span class="string">string</span> | <span class="required">Required</span> | 
`authorisationCode` <br />Code provided by Google| <span class="string">string</span> | <span class="required">Required</span> | 
`accessToken` <br />Code provided by Google| <span class="string">string</span> | <span class="required">Required</span> | 
`applicationIdentifier` <br />The identifier for the eSuite application that the account is using| <span class="string">string</span> | <span class="required">Required</span> | 



