# Subscription Management

## Retrieve all Subscriptions

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

```

> The above command returns JSON structured like this:

```json

```

Calling this endpoint will return the history of all subscriptions an account has or has previously had.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions</span>
</div>

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- |  ----------- |
`subscriptions` | array[object] |  Subscriptions
`subscriptions` > `accountSubscriptionInfo` | object | Account Subscription Info
`accountSubscriptionInfo` > `expiryDate` | string | Expiry Date
accountSubscriptionInfo > firstNonDiscountedBillingPointUtc | string | First Non Discounted Billing PointUTC
accountSubscriptionInfo > lastDiscountedBillingPointUtc | string | Last Discounted Billing PointUTC
accountSubscriptionInfo > paymentMethod | string | Payment Method
accountSubscriptionInfo > recurringPaymentInfo | object | Recurring Payment Info
recurringPaymentInfo > subscriptionReference | integer | Subscription Reference
recurringPaymentInfo > resourceReference | string | Unique Resource Reference
recurringPaymentInfo > configuredSubscriptionPrice | number | Configured Subscription Price
recurringPaymentInfo > subscribedPrice | number | Subscribed Price
recurringPaymentInfo > currency | string | Currency
recurringPaymentInfo > recurringPaymentEnable | string | Recurring Payment Enable
recurringPaymentInfo > subscriptionLockedIn | string | Subscription LockedIn
recurringPaymentInfo > nextPaymentDate | string | Next Payment Date
recurringPaymentInfo > previousBillingInfo | object | Previous Billing Info
previousBillingInfo > subscriptionPriceId | integer | Subscription Price Id
previousBillingInfo > totalAmount | number | Total Amount
previousBillingInfo > totalTaxAmount | number | Total Tax Amount
previousBillingInfo > totalNetAmount | number | Total Net Amount
previousBillingInfo > billingDate | string |  Billing Date
previousBillingInfo > paymentDate | string | Payment Date
previousBillingInfo > taxInfo | array[object] |Tax info
taxInfo > regionName | string | Region Name
taxInfo > regionType | string | Region Type
taxInfo > displayName | string | Display Name
taxInfo > category | string | Category
taxInfo > rate | number | Rate
taxInfo > amount | number |Amount
previousBillingInfo > priceItems | array[object] |Price Items
priceItems > thirdPartyRef | string |Gets or sets the external reference
priceItems > supplierId | integer |Gets or sets the supplier id
priceItems > price | number |Gets or sets the price
priceItems > description | string |Gets or sets the description
priceItems > isGrossAmount | string |Specify whether is groos amount
priceItems > taxCategoryName | string |Tax Category Name
recurringPaymentInfo > groupSubscriptionInfo | object |Group Subscription Info
groupSubscriptionInfo > licenseLevel | integer |License Level
groupSubscriptionInfo > overflowLevel | integer |Overflow Level
groupSubscriptionInfo > subscriberList | array[object] |Subscriber List
groupSubscriptionInfo > subscriberList > subscriptionId | integer |SubscriptionId
groupSubscriptionInfo > subscriberList > emailAddress | string |Email Address
groupSubscriptionInfo > subscriberList > clientUserId | string |ClientUserId
groupSubscriptionInfo > overFlowCount | integer |Overflow Count
groupSubscriptionInfo > fullSubscriptionsCount | integer |Full Subscriptions Count
groupSubscriptionInfo > currentUserInOverFlow | string |Specify whether Current User In OverFlow
recurringPaymentInfo > voucherCodes | object |Voucher Code
voucherCodes > voucherCode | string |Voucher Code
recurringPaymentInfo > voucherCodes > discountPrice | number |Discount Price
recurringPaymentInfo > statusInfo | object |Status info
statusInfo > statusId | integer |Status id
statusInfo > statusDescription | string |Status description
recurringPaymentInfo > customParameters | object |Custom parameters
customParameters > | string | The name of the parameter
accountSubscriptionInfo > paymentScheduleInfo | object |Payment Schedule Info
paymentScheduleInfo > startDate | string |Start Date
paymentScheduleInfo > frequency | string |Start Date
paymentScheduleInfo > totalAmount | number |Total Amount
paymentScheduleInfo > paymentDayOffset | integer |Payment Day Offset
paymentScheduleInfo > paymentDay | integer |Payment Day
paymentScheduleInfo > currency | string |Currency
paymentScheduleInfo > paymentMethod | string |Payment Method
paymentScheduleInfo > scheduledPayments | array[objects] |Scheduled Payments
scheduledPayments > orderId | integer |Order Id
scheduledPayments > orderDate | string |Order Date
scheduledPayments > status | string |Status
scheduledPayments > priceInfo | object |Price Info
priceInfo > grossAmount | number |Gross Amount
priceInfo > netAmount | number |Net Amount
priceInfo > totalTaxAmount | number |Total Tax Amount
priceInfo > taxInfo | array[object] |Tax Info
taxInfo > regionName | string |Region Name
taxInfo > regionType | string |Region Type
taxInfo > displayName | string |Display Name
taxInfo > category | string |Category
taxInfo > rate | number |Rate
taxInfo > amount | number |Amount
paymentScheduleInfo > statusInfo | object |Status info
paymentScheduleInfo > statusId | integer |Status id
paymentScheduleInfo > statusDescription | string |Status description
subscriptions > defaultSubscriptionInfo | object |Default Subscription Info
defaultSubscriptionInfo > customParameters | object |Custom Parameters
defaultSubscriptionInfo > subscriptionId | integer |Subscription Id
defaultSubscriptionInfo > subscriptionStatus | string |Subscription Status
defaultSubscriptionInfo > subscriptionTitle | string |Subscription Title
defaultSubscriptionInfo > subscriptionGroup | string |Subscription Group




## Cancel a Subscription

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

```

> The above command returns JSON structured like this:

```json

```

Calling this endpoint will allow you to hard cancel a subscription. The successful execution of this call will remove all associated entitlements.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions</span>
</div>

### Patch Parameters

Parameter | Type |  Description | 
--------- | ------- | ----------- |
`name` | string | What does the parameter represent?


## Manage Subscription renewals

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

```

> The above command returns JSON structured like this:

```json

```

Calling this endpoint will allow you to enable or disable the renewal process for a specific subscription.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/status</span>
</div>

### Patch Parameters

Parameter | Type |  Description | 
--------- | ------- | ----------- |
`name` | string | What does the parameter represent?


## Add a Voucher Code

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

```

> The above command returns JSON structured like this:

```json

```

Calling this endpoint will allow you to add a voucher code to an existing subscription that will be applied at the next renewal.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/vouchers</span>
</div>

### POST Parameters

Parameter | Type | Mandatory |Description | 
--------- | ------- | -------- | ----------- |
`name` | string | What does the parameter represent?




## Create a holiday

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"startDate":"2017-07-04T00:00:00","endDate":"2017-07-14T23:59:59"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"startDate\":\"2017-07-04T00:00:00\",\"endDate\":\"2017-07-14T23:59:59\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"startDate\":\"2017-07-04T00:00:00\",\"endDate\":\"2017-07-14T23:59:59\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"startDate\":\"2017-07-04T00:00:00\",\"endDate\":\"2017-07-14T23:59:59\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"startDate\":\"2017-07-04T00:00:00\",\"endDate\":\"2017-07-14T23:59:59\"}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"startDate\":\"2017-07-04T00:00:00\",\"endDate\":\"2017-07-14T23:59:59\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns a HTTP 200 with JSON similar to the below.

```json
{
  "subscriptionHolidayReference": "QIUQIEUQIEU8173",
  "subscriptionReference": "ASJDKAS6712KDASK",
  "startDate": "2017-07-04T00:00:00",
  "endDate": "2017-07-14T23:59:59"
}
```

This endpoint allows you to create a holiday period for a specific subscription. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays</span>
</div>

### Request Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`startDate` | string | Yes | The date at which the holiday period should begin.
`endDate` | string | Yes | The date at which the subscription should become active.



## Retrieve a holiday

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")

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

conn.request("GET", "/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}",
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
  "subscriptionHolidayReference": "QIUQIEUQIEU8173",
  "subscriptionReference": "ASJDKAS6712KDASK",
  "startDate": "2017-07-04T00:00:00",
  "endDate": "2017-07-14T23:59:59"
}
```

This endpoint allows you to retrieve all configured subscription holidays for a specific accounts subscription.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/</span>
</div>

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- |  ----------- |
`subscriptionHolidayReference` | string | Reference to the holiday. 
`subscriptionReference` | string | Reference to the subscription.
`startDate` | string | The date at which the holiday period should begin.
`endDate` | string | The date at which the subscription should become active.

## Update a holiday

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
 --data '[{"op":"replace","path":"/StartDate/","value":"2017-08-04 00:00:00Z"},{"op":"replace","path":"/EndDate/","value":"2017-09-04 00:00:00Z"}]'
 ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}");
var request = new RestRequest(Method.PATCH);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"replace\",\"path\":\"/StartDate/\",\"value\":\"2017-08-04 00:00:00Z\"},{\"op\":\"replace\",\"path\":\"/EndDate/\",\"value\":\"2017-09-04 00:00:00Z\"}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"op\":\"replace\",\"path\":\"/StartDate/\",\"value\":\"2017-08-04 00:00:00Z\"},{\"op\":\"replace\",\"path\":\"/EndDate/\",\"value\":\"2017-09-04 00:00:00Z\"}]")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"op\":\"replace\",\"path\":\"/StartDate/\",\"value\":\"2017-08-04 00:00:00Z\"},{\"op\":\"replace\",\"path\":\"/EndDate/\",\"value\":\"2017-09-04 00:00:00Z\"}]"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "[{\"op\":\"replace\",\"path\":\"/StartDate/\",\"value\":\"2017-08-04 00:00:00Z\"},{\"op\":\"replace\",\"path\":\"/EndDate/\",\"value\":\"2017-09-04 00:00:00Z\"}]"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "[{\"op\":\"replace\",\"path\":\"/StartDate/\",\"value\":\"2017-08-04 00:00:00Z\"},{\"op\":\"replace\",\"path\":\"/EndDate/\",\"value\":\"2017-09-04 00:00:00Z\"}]"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "subscriptionHolidayReference": "QIUQIEUQIEU8173",
  "subscriptionReference": "ASJDKAS6712KDASK",
  "startDate": "2017-07-04T00:00:00",
  "endDate": "2017-07-14T23:59:59"
}
```

In the event you need to update a subscription holiday, this end point should be called to edit those which have not started.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-put">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}</span>
</div>

### PATCH Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
| array[objects] | Yes | A collection of updates that should be made to the resource
`op` | string | Yes | The type of change that should be executed. add, replace and remove are available operations.
`path` | string | Yes | The name of the parameter that should be updated.
`value` | string | Yes | The new value to store against the parameter.

## Delete a holiday

```shell
curl --request DELETE \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.delete("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")

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
    'x-version': "9.0.0"
    }

conn.request("DELETE", "/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}",
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

> The above command returns a HTTP 204 upon completion.


If an account would like to cancel their subscription holiday, this endpoint should be called.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}</span>
</div>

## Retrieve all subscription holidays

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays")

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

conn.request("GET", "/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays",
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
[{
  "subscriptionHolidayReference": "QIUQIEUQIEU8173",
  "subscriptionReference": "ASJDKAS6712KDASK",
  "startDate": "2017-07-04T00:00:00",
  "endDate": "2017-07-14T23:59:59"
}]
```

This endpoint allows you to retrieve all configured subscription holidays for a specific accounts subscription.

### URL Endpoint

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionReference}/holidays/</span>
</div>

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- |  ----------- |
  | array[objects] | The collection of support log entries.
`subscriptionHolidayReference` | string | Reference to the holiday. 
`subscriptionReference` | string | Reference to the subscription.
`startDate` | string | The date at which the holiday period should begin.
`endDate` | string | The date at which the subscription should become active.






