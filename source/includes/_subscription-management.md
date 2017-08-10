# Subscription Management

## Retrieve all Subscriptions

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions")

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

conn.request("GET", "/api/accounts/{accountId}/subscriptions", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions",
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

Calling this endpoint will return the history of all subscriptions an account has or has previously had.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions</span>
</div>

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- |  ----------- |
`subscriptions` | array[object] |  Collection of all subscription an account has purchased
`subscriptions` > `accountSubscriptionInfo` | object | Collection of subscriptions
`accountSubscriptionInfo` > `expiryDate` | string | The date at which the subscription expired or will renew
`accountSubscriptionInfo` > `firstNonDiscountedBillingPointUtc` | string | The first date the account paid full price for the subscription
`accountSubscriptionInfo` > `lastDiscountedBillingPointUtc` | string | The last date the account received a discount
`accountSubscriptionInfo` > `paymentMethod` | string | Payment method used for the subscription
`accountSubscriptionInfo` > `recurringPaymentInfo` | object | Specific information around the subscription recurrance
`recurringPaymentInfo` > `subscriptionReference` | integer | Subscription Identifier
`recurringPaymentInfo` > `configuredSubscriptionPrice` | number | Default Price of the subscription service
`recurringPaymentInfo` > `subscribedPrice` | number | Price of subscription at the point of subscribing
`recurringPaymentInfo` > `currency` | string | The currency the subscription is related
`recurringPaymentInfo` > `recurringPaymentEnable` | string | An indication whether the subscription will renew
`recurringPaymentInfo` > `subscriptionLockedIn` | string | An indication whether the subscription can be cancelled
`recurringPaymentInfo` > `nextPaymentDate` | string | Date at which the next payment will be taken
`recurringPaymentInfo` > `previousBillingInfo` | object | Information relating to the previous payment made
`previousBillingInfo` > `subscriptionPriceId` | integer | Previous price identifier used
`previousBillingInfo` > `totalAmount` | number | Total amount paid by the account
`previousBillingInfo` > `totalTaxAmount` | number | Total tax amount paid by the account
`previousBillingInfo` > `totalNetAmount` | number | Total net amount paid by the account
`previousBillingInfo` > `billingDate` | string |  The date the account was last billed
`previousBillingInfo` > `paymentDate` | string | The date the account was debited
`previousBillingInfo` > `taxInfo` | array[object] |Collection of tax rates applied
`taxInfo` > `regionName` | string | Name of the tax region
`taxInfo` > `regionType` | string | The type of region the tax related
`taxInfo` > `displayName` | string | Friendly name of the tax applied
`taxInfo` > `category` | string | The category of tax applied
`taxInfo` > `rate` | number | The tax rate applied
`taxInfo` > `amount` | number |The amount of tax calculated
`previousBillingInfo` > `priceItems` | array[object] | Collection of items provided for a dynamic priced subscription
`priceItems` > `thirdPartyRef` | string | An external referenced provided
`priceItems` > `supplierId` | integer | An internal supplierId if applicable
`priceItems` > `price` | number |G The price to charge
`priceItems` > `description` | string | The description related to the charge
`priceItems` > `isGrossAmount` | string |An indication whether the price should be charged as gross or net
`priceItems` > `taxCategoryName` | string |The category of tax that was applied
`recurringPaymentInfo` > `groupSubscriptionInfo` | object |Information related to a group subscription
`groupSubscriptionInfo` > `licenseLevel` | integer |The number of standard licenses the subscription has
`groupSubscriptionInfo` > `overflowLevel` | integer |The number of overflow licenses the subscription has
`groupSubscriptionInfo` > `subscriberList` | array[object] |Collection of all associated subscribers
`subscriberList` > `subscriptionId` | integer |The unique identifier to the subscription for the account
`subscriberList` > `emailAddress` | string | The email address of the subscribed account
`subscriberList` > `clientUserId` | string | The clientUserId of the subscribed account
`groupSubscriptionInfo` > `overFlowCount` | integer |The number of overflow licenses used
`groupSubscriptionInfo` > `fullSubscriptionsCount` | integer |The number of standard licenses used
`groupSubscriptionInfo` > `currentUserInOverFlow` | string |Indication whether the account is deemed overflow
`recurringPaymentInfo` > `voucherCodes` | object | Voucher information associated to the subscription
`voucherCodes` > `voucherCode` | string | The current voucher code against the subscription
`recurringPaymentInfo` > `voucherCodes` > discountPrice | number | The price charged to the customer as a result of the voucher
`recurringPaymentInfo` > `statusInfo` | object | Information relating to subscription status
`statusInfo` > `statusId` | integer | The status identifier for the subscription
`statusInfo` > `statusDescription` | string | Description of the subscriptions status
`recurringPaymentInfo` > `customParameters` | object | Custom parameters of the accounts subscription
`customParameters` > `ParameterName`| string | Custom parameters of the accounts subscription
`subscriptions` > `defaultSubscriptionInfo` | object | Collection of information relating to the overall subscription service
`defaultSubscriptionInfo` > `customParameters` | object |The associated subscription service parameters
`defaultSubscriptionInfo` > `subscriptionId` | integer | Subscription Service Identifier
`defaultSubscriptionInfo` > `subscriptionStatus` | string | The status of the subscription service
`defaultSubscriptionInfo` > `subscriptionTitle` | string | The title of the subscription service purchase
`defaultSubscriptionInfo` > `subscriptionGroup` | string | The group the subscription service belongs


## Cancel a Subscription

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"status":"cancel"}'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}");
var request = new RestRequest(Method.patch);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"status\":\"replace\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"status\":\"cancel\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"status\":\"cancel\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"status\":\"cancel\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}/subscriptions/{subscriptionId}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "[{\"status\":\"cancel\"}]"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns a HTTP 204

```json

```

Calling this endpoint will allow you to hard cancel a subscription. The successful execution of this call will remove all associated entitlements. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}</span>
</div>

### Patch Parameters

Parameter | Type |  Description | 
--------- | ------- | ----------- |
`status` | string | Passing `cancel` will cancel the subscription and remove entitlements


## Manage Subscription renewals

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/status \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"renewals":"enable"}'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/status");
var request = new RestRequest(Method.patch);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"renewals\":\"enable\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/status")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("[{\"renewals\":\"enable\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/status")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "[{\"renewals\":\"enable\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"renewals\":\"enable\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountId}/subscriptions/{subscriptionId}/status", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/status",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "[{\"renewals\":\"enable\"}]"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns a HTTP 204


Calling this endpoint will allow you to enable or disable the renewal process for a specific subscription. The available values to be set are `enable` and `disable`

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions//{subscriptionId}/status</span>
</div>

### Patch Parameters

Parameter | Type |  Description | 
--------- | ------- | ----------- |
`renewals` | string | Passing `enable` to activate renewals, and `disable` to deactivate.


## Add a Voucher Code

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"voucherCode":"ABC45FDR"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"voucherCode\":\"ABC45FDR\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"voucherCode\":\"ABC45FDR\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request.body = "{\"voucherCode\":\"ABC45FDR\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"voucherCode\":\"ABC45FDR\"}"

headers = { 
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json" }

conn.request("POST", "/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"voucherCode\":\"ABC45FDR\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns a HTTP 204:

```json

```

Calling this endpoint will allow you to add a voucher code to an existing subscription that will be applied at the next renewal.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/vouchers</span>
</div>

### POST Parameters

Parameter | Type | Mandatory |Description | 
--------- | ------- | -------- | ----------- |
`voucherCode` | string | Yes | Preconfigured eSuite voucher code




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
  | array[objects] | The collection of subscription holidays.
`subscriptionHolidayReference` | string | Reference to the holiday. 
`subscriptionReference` | string | Reference to the subscription.
`startDate` | string | The date at which the holiday period should begin.
`endDate` | string | The date at which the subscription should become active.






