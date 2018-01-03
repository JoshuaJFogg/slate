# Group Accounts

## Create Group

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/groups \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"groupName":"Example Account Group"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/groups");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"groupName\":\"Example Account Group\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/groups")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"groupName\":\"Example Account Group\",\"password\":\"pWzjWktsWN8M\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/groups")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"groupName\":\"Example Account Group\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"groupName\":\"Example Account Group\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/{accountId}/groups", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/groups",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "65e2d8d8c22e49b7b922ef48f9683f13",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"groupName\":\"Example Account Group\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
    "groupToken": "65e2d8d8-c22e-49b7-b922-ef48f9683f13"
}
```

Execution of this action on the API will allow the creation of a new group account. The name provided must be unique to your instance of eSuite.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/groups</span>
</div>

### Request Parameters

 |  |  | 
--------- | ------- | ------- | 
`groupName` <br />The name to be associated to the new group. This group name must be unique.| <span class="string">string</span> | <span class="required">Required</span> | 

### Response Parameters

 |  |  | 
--------- | ------- | ------- | 
`groupToken` <br />The identifier for the new account group.| <span class="string">string</span> |  | 



## Retieve Groups

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/groups \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/groups");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/groups")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/groups")

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

conn.request("GET", "/api/accounts/{accountId}/groups", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/groups",
  "method": "GET",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid" : "65e2d8d8c22e49b7b922ef48f9683f13",
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
  "groups": [
    {
      "role": "Payee",
      "groupInfo": {
        "accountGroupName": "Example Account Group",
        "accountGroupToken": "65e2d8d8-c22e-49b7-b922-ef48f9683f13",
        "created": "2017-09-15T10:48:40.907",
        "lastUpdated": "2017-09-15T12:54:39.687",
        "payeeInfo": {
          "clientUserId": "my-test-012514215",
          "firstName": "John",
          "lastName": "Thoms",
          "email": "john.thoms@mppglobal.com"
        },
        "ipRanges": [
          {
            "start": "192.168.001.001",
            "end": "192.168.001.001"
          },
          {
            "start": "127.000.000.000",
            "end": "127.000.000.001"
          }
        ],
        "emailDomains": [
          "mppglobal.com"
        ],
        "permitUserPayments": false,
        "matchEmailOnlyAfterIpMatch": false
      }
    }
  ]
}
```

This endpoint will return all groups the specific account group is associated to.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/groups</span>
</div>

### Response Parameters
 |  |  | 
--------- | ------- | ------- | 
`role` <br />An indication as to the role which the account in question holds within the group.| <span class="string">string</span> || 
`groupInfo` <br />Object of data specific the instance of the group.| <span class="string">string</span> || 
`groupInfo \ accountGroupName` <br />The identifiable name of the account group.| <span class="string">string</span> || 
`groupInfo \ accountGroupToken` <br />The identifier for the account group.| <span class="string">string</span> || 
`groupInfo \ created` <br />The The date at which the account group was created.| <span class="string">string</span> || 
`groupInfo \ lastUpdated` <br />The The date at which the account group was last updated.| <span class="object">object</span> || 
`groupInfo \ payeeInfo` <br />Object of data relating to the payee of the group.| <span class="string">string</span> || 
`payeeInfo \ clientUserId` <br />The unique identifier for the payee account.| <span class="string">string</span> || 
`payeeInfo \ firstName` <br />The first name associated to the payee account.| <span class="string">string</span> || 
`payeeInfo \ lastName` <br />The last name associated to the payee account.| <span class="string">string</span> || 
`payeeInfo \ email` <br />Email address of the payee account registered on eSuite.| <span class="string">string</span> || 
`groupInfo \ ipRanges` <br />A collection of IPv4 addresses that can be used to automatically join the group.| <span class="array">array[objects]</span> || 
`ipRanges \ start` <br />Start of the allowed IP Range| <span class="string">string</span> ||
`ipRanges \ end` <br />End of the allowed IP Range| <span class="string">string</span> ||
`groupInfo \ emailDomains` <br />A collection of email domains that can be used to automatically join the group.| <span class="array">array[string]</span> || 
`groupInfo \ permitUserPayments` <br />This attribute represents whether the users of this group are able to make purchases on behalf of the payee| <span class="boolean">boolean</span> || 
`groupInfo \ matchEmailOnlyAfterIpMatch` <br />An indication as to whether the email domain should only be checked if the IP has been verified| <span class="boolean">boolean</span> ||


## Update Group

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '[{"op":"replace","path":"/GroupInfo/permitUserPayments/","value":true},{"op":"replace","path":"/GroupInfo/matchEmailOnlyAfterIpMatch/","value":true}]'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}");
var request = new RestRequest(Method.patch);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"replace\",\"path\":\"/GroupInfo/permitUserPayments/\",\"value\":true},{\"op\":\"replace\",\"path\":\"/GroupInfo/matchEmailOnlyAfterIpMatch/\",\"value\":true}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"op\":\"replace\",\"path\":\"/GroupInfo/permitUserPayments/\",\"value\":true},{\"op\":\"replace\",\"path\":\"/GroupInfo/matchEmailOnlyAfterIpMatch/\",\"value\":true}]")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"op\":\"replace\",\"path\":\"/GroupInfo/permitUserPayments/\",\"value\":true},{\"op\":\"replace\",\"path\":\"/GroupInfo/matchEmailOnlyAfterIpMatch/\",\"value\":true}]"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "[{\"op\":\"replace\",\"path\":\"/GroupInfo/permitUserPayments/\",\"value\":true},{\"op\":\"replace\",\"path\":\"/GroupInfo/matchEmailOnlyAfterIpMatch/\",\"value\":true}]"


headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}/groups/{accountGroupToken}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid" : "65e2d8d8c22e49b7b922ef48f9683f13"
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "[{\"op\":\"replace\",\"path\":\"/GroupInfo/permitUserPayments/\",\"value\":true},{\"op\":\"replace\",\"path\":\"/GroupInfo/matchEmailOnlyAfterIpMatch/\",\"value\":true}]"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json

```

Calling this endpoint on the API will allow you to edit the following attributes of an account group: emailDomains, ipRange, permitUserPayments and MatchEmailOnlyAfterIP.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}</span>
</div>

### PATCH Parameters
 |  |  | 
--------- | ------- | ------- | 
A collection of updates that should be made to the resource| <span class="array">array[objects]</span> | <span class="required">Required</span> | 
`op` <br />The type of change that should be executed. add, replace and remove are available operations.| <span class="string">string</span> | <span class="required">Required</span> | 
`path` <br />The name of the parameter that should be updated.| <span class="string">string</span> | <span class="required">Required</span> | 
`value` <br />The new value to store against the parameter.| <span class="string">string</span> | <span class="required">Required</span> | 

## Retieve Candidate Groups

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/groups/candidates \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/groups/candidates");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/groups/candidates")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/groups/candidates")

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

conn.request("GET", "/api/accounts/{accountId}/groups/candidates", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/groups/candidates",
  "method": "GET",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid" : "65e2d8d8c22e49b7b922ef48f9683f13",
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
    "candidateGroups": [
        {
            "name": "Technical Subscriptions",
            "token": "96a9d26e-ddf8-4d54-9dd1-dd4ef505a814",
            "manager": "James Polkowski"
        },
        {
            "name": "Corperate Subscriptions",
            "token": "ad70aaab-f21e-45e5-a87c-a35e2ed2e4b2",
            "manager": "Owen Smith"
        }
    ]
}
```

Executing this API request will return all groups the account is applicable to join based upon IP and email domain restrictions.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/groups</span>
</div>

### Response Parameters
 |  |  | 
--------- | ------- | ------- | 
`candidateGroups` <br />Collection of all groups the account is a candidate to join.| <span class="array">array[objects]</span> ||  
`candidateGroups \ name` <br />Friendly name of the account group.| <span class="string">string</span> || 
`candidateGroups \ token` <br />The identifier for the account group.| <span class="string">string</span> || 
`candidateGroups \ manager` <br />The account manager of the account group.| <span class="string">string</span> || 



## Add Account to Group

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"email":"my-example@mppglobal.com","clientUserId":"GTFGTV456TF5G"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"email\":\"my-example@mppglobal.com\",\"clientUserId\":\"GTFGTV456TF5G\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"email\":\"my-example@mppglobal.com\",\"clientUserId\":\"GTFGTV456TF5G\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"email\":\"my-example@mppglobal.com\",\"clientUserId\":\"GTFGTV456TF5G\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"email\":\"my-example@mppglobal.com\",\"clientUserId\":\"GTFGTV456TF5G\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/groups/{accountGroupToken}/members", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns and empty response upon success

```json

```

Execution of this action on the API will allow the creation of a new group account. The name provided must be unique to your instance of eSuite.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members</span>
</div>

### Request Parameters

 |  |  | 
--------- | ------- | ------- | 
`email` <br />email of the account that should be added to the account group.| <span class="string">string</span> | |
`clientUserID` <br />ClientUserID of the account that should be added to the account group.| <span class="string">string</span> | |  



## Retieve Group Members

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}")

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

conn.request("GET", "/api/accounts/groups/{accountGroupToken}", payload, headers)

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
    "resultsPerPage": 500,
    "items": [
        {
            "groupRole": "Payee",
            "clientUserId": "821430",
            "email": "james.griffin@mppqa.co.uk",
            "firstName": "James",
            "surname": "Griffin"
        }
    ]
}
```

This endpoint will return all accounts that are a member of the specific account group.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}</span>
</div>

### Response Parameters
 |  |  | 
--------- | ------- | ------- | 
`totalNumberOfRecords` <br />Total number of members that have been found | <span class="integer">integer</span> |  |
`pageNumber` <br />The current page of results being show| <span class="integer">integer</span> |  |
`resultsPerPage` <br />The number of results being shown| <span class="integer">integer</span> |  |
`items` <br />Collection of group members| <span class="array">array[objects]</span> |  | 
`items \ groupRole` <br />The role the account has within the group.| <span class="string">string</span> || 
`items \ clientUserId` <br />Technical identifier for the account.| <span class="string">string</span> || 
`items \ email` <br />Email address associated to the account.| <span class="string">string</span> || 
`items \ firstName` <br />The first name of the account.| <span class="string">string</span> || 
`items \ surname` <br />The surname of the account.| <span class="string">string</span> || 

## Update Accounts Group Role

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '[{"op":"replace","path":"/GroupRole","value":"Admin"}]'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}");
var request = new RestRequest(Method.patch);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"replace\",\"path\":\"/GroupRole\",\"value\":\"Admin\"}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"op\":\"replace\",\"path\":\"/GroupRole\",\"value\":\"Admin\"}]")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"op\":\"replace\",\"path\":\"/GroupRole\",\"value\":\"Admin\"}]"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "[{\"op\":\"replace\",\"path\":\"/GroupRole\",\"value\":\"Admin\"}]"


headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/groups/{accountGroupToken}/members/{accountId}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns an empty response on completion.

```json

```

Calling this endpoint on the API will allow you to edit the role the user has on the account

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}</span>
</div>

### PATCH Parameters
 |  |  | 
--------- | ------- | ------- | 
A collection of updates that should be made to the resource| <span class="array">array[objects]</span> | <span class="required">Required</span> | 
`op` <br />The type of change that should be executed. Replace is the only option available on this endpoint.| <span class="string">string</span> | <span class="required">Required</span> | 
`path` <br />The name of the parameter that should be updated.| <span class="string">string</span> | <span class="required">Required</span> | 
`value` <br />The new value to store against the parameter.| <span class="string">string</span> | <span class="required">Required</span> | 

## Delete Accounts from Group

```shell
curl --request DELETE \
  --url https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}")

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

conn.request("DELETE", "/api/accounts/groups/{accountGroupToken}/members/{accountId}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}",
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

Calling this endpoint will remove the account from the associated group. It is not possible to remove and account from the group if they are a Payee or Admin.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}</span>
</div>








## Retieve Group Members

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions")

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

conn.request("GET", "/api/accounts/groups/{accountGroupToken}/subscriptions", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "subscriptions": [
    {
      "accountSubscriptionInfo": {
        "expiryDate": "2017-08-23T14:19:10.817",
        "firstNonDiscountedBillingPointUtc": "0001-01-01T00:00:00",
        "lastDiscountedBillingPointUtc": "0001-01-01T00:00:00",
        "paymentMethod": "CreditDebitCard",
        "recurringPaymentInfo": {
          "subscriptionReference": 317337,
          "resourceReference": "0010SRA891LP0HW231",
          "configuredSubscriptionPrice": 18665,
          "subscribedPrice": 200,
          "currency": "EUR",
          "recurringPaymentEnable": true,
          "subscriptionLockedIn": false,
          "nextPaymentDate": "2017-08-23T14:19:10.817",
          "previousBillingInfo": {
            "subscriptionPriceId": 18665,
            "totalAmount": 180,
            "totalTaxAmount": 150,
            "totalNetAmount": 150,
            "billingDate": "2017-07-23T14:19:15.27",
            "paymentDate": "2017-08-23T14:19:10.817",
            "taxInfo": [
              {
                "regionName": "GBR",
                "regionType": "Country",
                "displayName": "United Kingdom",
                "category": "Standard",
                "rate": 20,
                "amount": 30
              }
            ]
          },
          "groupSubscriptionInfo": {
            "licenseLevel": 10,
            "overflowLevel": 0,
            "overFlowCount": 0,
            "fullSubscriptionsCount": 2,
            "currentUserInOverFlow": false,
            "accountGroupToken": "40271c08-0f7cf1b37d28"
          },
          "voucherCodes": {
            "discountPrice": 0
          },
          "statusInfo": {
            "statusId": 2,
            "statusDescription": "Active"
          },
          "customParameters": {}
        }
      },
      "defaultSubscriptionInfo": {
        "customParameters": {},
        "subscriptionId": 15991,
        "subscriptionStatus": "active",
        "subscriptionTitle": "Account Group Sub",
        "subscriptionGroup": "AGT",
        "licenseLevel": 10
      }
    }
  ]
}

```

This endpoint will return all subscriptions against the account group.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions</span>
</div>

### Response Parameters

 |  |  
--------- | ------- |  
`subscriptions` <br />Collection of all subscription an account has purchased| <span class="array">array[object]</span> |  
`subscriptions \ accountSubscriptionInfo` <br />Collection of subscriptions| <span class="object">object</span> |
`accountSubscriptionInfo \ expiryDate` <br />The date at which the subscription expired or will renew| <span class="string">string</span> | 
`accountSubscriptionInfo \ firstNonDiscountedBillingPointUtc` <br />The first date the account paid full price for the subscription| <span class="string">string</span> | 
`accountSubscriptionInfo \ lastDiscountedBillingPointUtc` <br />The last date the account received a discount| <span class="string">string</span> | 
`accountSubscriptionInfo \ paymentMethod` <br />Payment method used for the subscription| <span class="string">string</span> | 
`accountSubscriptionInfo \ recurringPaymentInfo` <br />Specific information around the subscription recurrence| <span class="object">object</span> |
`recurringPaymentInfo \ subscriptionReference` <br />Subscription Identifier| <span class="integer">integer</span> | 
`recurringPaymentInfo \ configuredSubscriptionPrice` <br />Default Price of the subscription service| <span style="color:#666;font-weight: bold;">number</span> | 
`recurringPaymentInfo \ subscribedPrice` <br />Price of subscription at the point of subscribing| <span style="color:#666;font-weight: bold;">number</span> | 
`recurringPaymentInfo \ currency` <br />The currency the subscription is related| <span class="string">string</span> | 
`recurringPaymentInfo \ recurringPaymentEnable` <br />An indication whether the subscription will renew| <span class="string">string</span> | 
`recurringPaymentInfo \ subscriptionLockedIn` <br />An indication whether the subscription can be cancelled| <span class="string">string</span> | 
`recurringPaymentInfo \ nextPaymentDate` <br />Date at which the next payment will be taken| <span class="string">string</span> | 
`recurringPaymentInfo \ previousBillingInfo` <br />Information relating to the previous payment made| <span class="object">object</span> |
`previousBillingInfo \ subscriptionPriceId` <br />Previous price identifier used| <span class="integer">integer</span> | 
`previousBillingInfo \ totalAmount` <br />Total amount paid by the account| <span style="color:#666;">number</span> | 
`previousBillingInfo \ totalTaxAmount` <br />Total tax amount paid by the account| <span style="color:#666;font-weight: bold;">number</span> | 
`previousBillingInfo \ totalNetAmount` <br />Total net amount paid by the account| <span style="color:#666;font-weight: bold;">number</span> | 
`previousBillingInfo \ billingDate` <br />The date the account was last billed| <span class="string">string</span> |  
`previousBillingInfo \ paymentDate` <br />The date the account was debited| <span class="string">string</span> | 
`previousBillingInfo \ taxInfo` <br />Collection of tax rates applied| <span class="array">array[object]</span> |
`taxInfo \ regionName` <br />Name of the tax region| <span class="string">string</span> | 
`taxInfo \ regionType` <br />The type of region the tax related| <span class="string">string</span> | 
`taxInfo \ displayName` <br />Friendly name of the tax applied| <span class="string">string</span> | 
`taxInfo \ category` <br />The category of tax applied| <span class="string">string</span> | 
`taxInfo \ rate` <br />The tax rate applied| <span style="color:#666;font-weight: bold;">number</span> | 
`taxInfo \ amount` <br />The amount of tax calculated| <span style="color:#666;font-weight: bold;">number</span> |
`previousBillingInfo \ priceItems` <br />Collection of items provided for a dynamic priced subscription| <span class="array">array[object]</span> | 
`priceItems \ thirdPartyRef` <br />An external referenced provided| <span class="string">string</span> | 
`priceItems \ supplierId` <br />An internal supplierId if applicable| <span class="integer">integer</span> | 
`priceItems \ price` <br />The price to charge| <span style="color:#666;font-weight: bold;">number</span> |
`priceItems \ description` <br />The description related to the charge| <span class="string">string</span> | 
`priceItems \ isGrossAmount` <br />An indication whether the price should be charged as gross or net| <span class="string">string</span> |
`priceItems \ taxCategoryName` <br />The category of tax that was applied| <span class="string">string</span> |
`recurringPaymentInfo \ groupSubscriptionInfo` <br />Information related to a group subscription| <span class="object">object</span> |
`groupSubscriptionInfo \ licenseLevel` <br />The number of standard licenses the subscription has| <span class="integer">integer</span> |
`groupSubscriptionInfo \ overflowLevel` <br />The number of overflow licenses the subscription has| <span class="integer">integer</span> |
`groupSubscriptionInfo \ subscriberList` <br />Collection of all associated subscribers| <span class="array">array[object]</span> |
`subscriberList \ subscriptionId` <br />The unique identifier to the subscription for the account| <span class="integer">integer</span> |
`subscriberList \ emailAddress` <br />The email address of the subscribed account| <span class="string">string</span> | 
`subscriberList \ clientUserId` <br />The clientUserId of the subscribed account| <span class="string">string</span> | 
`groupSubscriptionInfo \ overFlowCount` <br />The number of overflow licenses used| <span class="integer">integer</span> |
`groupSubscriptionInfo \ fullSubscriptionsCount` <br />The number of standard licenses used| <span class="integer">integer</span> |
`groupSubscriptionInfo \ currentUserInOverFlow` <br />Indication whether the account is deemed overflow| <span class="string">string</span> |
`recurringPaymentInfo \ voucherCodes` <br />Voucher information associated to the subscription| <span class="object">object</span> |
`voucherCodes \ voucherCode` <br />The current voucher code against the subscription| <span class="string">string</span> | 
`recurringPaymentInfo \ voucherCodes` > discountPrice <br />The price charged to the customer as a result of the voucher| <span style="color:#666;font-weight: bold;">number</span> | 
`recurringPaymentInfo \ statusInfo` <br />Information relating to subscription status| <span class="object">object</span> |
`statusInfo \ statusId` <br />The status identifier for the subscription| <span class="integer">integer</span> | 
`statusInfo \ statusDescription` <br />Description of the subscriptions status| <span class="string">string</span> | 
`recurringPaymentInfo \ customParameters` <br />Custom parameters of the accounts subscription| <span class="object">object</span> |
`customParameters \ ParameterName`<br />Custom parameters of the accounts subscription| <span class="string">string</span> | 
`subscriptions \ defaultSubscriptionInfo` <br />Collection of information relating to the overall subscription service| <span class="object">object</span> |
`defaultSubscriptionInfo \ customParameters` <br />The associated subscription service parameters| <span class="object">object</span> |
`defaultSubscriptionInfo \ subscriptionId` <br />Subscription Service Identifier| <span class="integer">integer</span> | 
`defaultSubscriptionInfo \ subscriptionStatus` <br />The status of the subscription service| <span class="string">string</span> | 
`defaultSubscriptionInfo \ subscriptionTitle` <br />The title of the subscription service purchase| <span class="string">string</span> | 
`defaultSubscriptionInfo \ subscriptionGroup` <br />The group the subscription service belongs| <span class="string">string</span> | 





## Add Account to Subscription

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"clientUserId":"my-example@mppglobal.com","emailAddress":"GTFGTV456TF5G"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"clientUserId\":\"my-example@mppglobal.com\",\"emailAddress\":\"GTFGTV456TF5G\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"clientUserId\":\"my-example@mppglobal.com\",\"emailAddress\":\"GTFGTV456TF5G\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"clientUserId\":\"my-example@mppglobal.com\",\"emailAddress\":\"GTFGTV456TF5G\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"clientUserId\":\"my-example@mppglobal.com\",\"emailAddress\":\"GTFGTV456TF5G\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns and empty response upon success

```json

```

Execution of this API will result in the account being assigned a license to consume the subscription that was purchased as part of the account group.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members</span>
</div>

### Request Parameters

 |  |  | 
--------- | ------- | ------- | 
`email` <br />Email of the account that should be added to the account group.| <span class="string">string</span> |<span class="required">Required</span> |
`clientUserID` <br />ClientUserID of the account that should be added to the account group.| <span class="string">string</span> |<span class="required">Required</span> |  
`useOverFlowLicense` <br />An indication as to whether to use an overflow license if all standard licenses have been allocated.| <span class="bool">boolean</span> | |  
`taxInfo`  <br />Collection of tax information| <span class="object">object</span> | | 
`taxInfo \ zeroRated`  <br />An indication as to whether the addition does not incurr tax| <span class="bool">boolean</span> | |
`taxInfo \ country`  <br />Specification as to which country to tax if different to the default.| <span class="string">string</span> | |
`taxInfo \ state`  <br />Specification of which state tax rate to apply (US only) |<span class="string">string</span> | |
`taxInfo \ county`  <br />Specification of which county tax rate to apply (US only| <span class="string">string</span> | |
`taxInfo \ city`  <br />Specification of which city tax rate to apply (US only| <span class="string">string</span> | |


## Delete Accounts from Group Subscription

```shell
curl --request DELETE \
  --url https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members/{accountId} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members/{accountId}");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.put("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members/{accountId}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members/{accountId}")

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

conn.request("DELETE", "/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members/{accountId}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members/{accountId}",
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

Calling this endpoint will remove the account from the associated group subscription.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members/{accountId}</span>
</div>


## Modify Subscription License Levels

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}/subscriptions/{subscriptionId}/licenses \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"standard":10,"overflow":2}'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}/subscriptions/{subscriptionId}/licenses");
var request = new RestRequest(Method.patch);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"standard\":10,\"overflow\":2}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}/subscriptions/{subscriptionId}/licenses")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"standard\":10,\"overflow\":2}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}/subscriptions/{subscriptionId}/licenses")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"standard\":10,\"overflow\":2}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"standard\":10,\"overflow\":2}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}/groups/{accountGroupToken}/subscriptions/{subscriptionId}/licenses", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns an response

```json

```

Calling this endpoint on the API will update the number of licenses assigned to the subscription. This will set the number of licenses rather than adding on the provided number.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/groups/{accountGroupToken}/subscriptions/{subscriptionId}/licenses</span>
</div>

### PATCH Parameters
 |  |  | 
--------- | ------- | ------- | 
`standard` <br />The new number of licenses that should be assigned to the subscription.| <span class="integer">integer</span> | <span class="required">Required</span> | 
`overflow` <br />The new number of overflow licenses that should be assigned to the subscription.| <span class="integer">integer</span> | <span class="required">Required</span> | 

