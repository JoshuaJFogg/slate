# Subscriber Management

## Retrieve all Subscriptions

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions")

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

conn.request("GET", "/api/accounts/{accountReference}/subscriptions", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions",
  "method": "GET",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions</span>
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


## Edit

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --data '{"status":"cancel"}'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}");
var request = new RestRequest(Method.patch);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"status\":\"replace\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
  .header("content-type", "application/json")
  .body("[{\"status\":\"cancel\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '10.0.0'
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
    'x-version': '10.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountReference}/subscriptions/{subscriptionReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "10.0.0",
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

Calling this endpoint will allow you to edit certain attributes of a subscription.

It is possible to change the status of a subscription, most often this will be as a result of the customer wishing to cancel their subscription. The available options for this action are `CancelledByUser` and `CancelledByCustomerSupport`.

This endpoint also allows customers to change the address that is associated to the shipping and/or invoice of the subscription. The parameters accept an addressReference which can be gained from creating a new address or retrieving existing addresses.


### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}</span>
</div>

### PATCH Parameters

 |  |  | 
--------- | ------- | ------- | 
A collection of updates that should be made to the resource| <span class="array">array[objects]</span> | <span class="required">Required</span> | 
`op` <br />The type of change that should be executed. add, replace and remove are available operations.| <span class="string">string</span> | <span class="required">Required</span> | 
`path` <br />The name of the parameter that should be updated.| <span class="string">string</span> | <span class="required">Required</span> | 
`value` <br />The new value to store against the parameter.| <span class="string">string</span> | <span class="required">Required</span> | 


### Available Parameter Values

 |  |  
--------- | ------- | 
`status` <br />Passing `CancelledByUser` or `CancelledByCustomerSupport` will cancel the subscription and remove entitlements| <span class="string">string</span> | 
`invoiceAddress` <br />This is the addressReference where the subscription should be invoiced t| <span class="string">string</span> | 
`shippingAddress` <br />This is the addressReference where the subscription should be shipped| <span class="string">string</span> | 

## Manage Subscription renewals

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/status \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --data '{"renewals":"enable"}'
  ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/status");
var request = new RestRequest(Method.patch);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"renewals\":\"enable\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/status")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
  .header("content-type", "application/json")
  .body("[{\"renewals\":\"enable\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/status")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '10.0.0'
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
    'x-version': '10.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountReference}/subscriptions/{subscriptionId}/status", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/status",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "10.0.0",
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
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/status</span>
</div>

### PATCH Parameters

 |  |  
--------- | ------- | 
`renewals` <br />Passing `enable` to activate renewals, and `disable` to deactivate.| <span class="string">string</span> | 


## Add a Voucher Code

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/vouchers \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"voucherCode":"ABC45FDR"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/vouchers");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"voucherCode\":\"ABC45FDR\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/vouchers")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "10.0.0")
  .header("content-type", "application/json")
  .body("{\"voucherCode\":\"ABC45FDR\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/vouchers")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '10.0.0'
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
    'x-version': '10.0.0',
    'content-type': "application/json" }

conn.request("POST", "/api/accounts/{accountReference}/subscriptions/{subscriptionId}/vouchers", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionId}/vouchers",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "10.0.0",
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
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionid}/vouchers</span>
</div>

### POST Parameters

 |  |  |
--------- | ------- | -------- | 
`voucherCode` <br />Preconfigured eSuite voucher code| <span class="string">string</span> | <span class="required">Required</span> | 




## Create a holiday

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --header 'content-type: application/json' \
  --header 'content-type: application/json' \
  --data '{"startDate":"2017-07-04T00:00:00","endDate":"2017-07-14T23:59:59"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\"startDate\":\"2017-07-04T00:00:00\",\"endDate\":\"2017-07-14T23:59:59\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-sessionid", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "10.0.0")
  .header("content-type", "application/json")
  .body("{\"startDate\":\"2017-07-04T00:00:00\",\"endDate\":\"2017-07-14T23:59:59\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '10.0.0'
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
    'x-version': '10.0.0',
    'content-type': "application/json" }

conn.request("POST", "/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays",
  "method": "POST",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "a0c595bd26004ff4bb7d4cb1b1c81a6d",
    "x-version": "10.0.0",
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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays</span>
</div>

### Request Parameters

 |  |  | 
--------- | ------- | ------- | 
`startDate` <br />The date at which the holiday period should begin.| <span class="string">string</span> | <span class="required">Required</span> | 
`endDate` <br />The date at which the subscription should become active.| <span class="string">string</span> | <span class="required">Required</span> | 



## Retrieve a holiday

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")

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

conn.request("GET", "/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}",
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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/</span>
</div>

### Response Parameters

 |  |  
--------- | ------- |  
`subscriptionHolidayReference` <br />Reference to the holiday. | <span class="string">string</span> | 
`subscriptionReference` <br />Reference to the subscription.| <span class="string">string</span> | 
`startDate` <br />The date at which the holiday period should begin.| <span class="string">string</span> | 
`endDate` <br />The date at which the subscription should become active.| <span class="string">string</span> | 

## Update a holiday

```shell
curl --request PATCH \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference} \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
 --data '[{"op":"replace","path":"/StartDate/","value":"2017-08-04 00:00:00Z"},{"op":"replace","path":"/EndDate/","value":"2017-09-04 00:00:00Z"}]'
 ```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}");
var request = new RestRequest(Method.PATCH);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "[{\"op\":\"replace\",\"path\":\"/StartDate/\",\"value\":\"2017-08-04 00:00:00Z\"},{\"op\":\"replace\",\"path\":\"/EndDate/\",\"value\":\"2017-09-04 00:00:00Z\"}]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.patch("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
  .header("content-type", "application/json")
  .body("[{\"op\":\"replace\",\"path\":\"/StartDate/\",\"value\":\"2017-08-04 00:00:00Z\"},{\"op\":\"replace\",\"path\":\"/EndDate/\",\"value\":\"2017-09-04 00:00:00Z\"}]")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::patch.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '10.0.0'
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
    'x-version': '10.0.0',
    'content-type': "application/json"
    }

conn.request("PATCH", "/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}",
  "method": "PATCH",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "10.0.0",
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
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}</span>
</div>

### PATCH Parameters

 |  |  | 
--------- | ------- | ------- | 
A collection of updates that should be made to the resource| <span class="array">array[objects]</span> | <span class="required">Required</span> | 
`op` <br />The type of change that should be executed. add, replace and remove are available operations.| <span class="string">string</span> | <span class="required">Required</span> | 
`path` <br />The name of the parameter that should be updated.| <span class="string">string</span> | <span class="required">Required</span> | 
`value` <br />The new value to store against the parameter.| <span class="string">string</span> | <span class="required">Required</span> | 

## Delete a holiday

```shell
curl --request DELETE \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}");
var request = new RestRequest(Method.DELETE);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.delete("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Delete.new(url)
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

conn.request("DELETE", "/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}",
  "method": "DELETE",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-version": "10.0.0",
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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/{subscriptionHolidayReference}</span>
</div>

## Retrieve all subscription holidays

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays")

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

conn.request("GET", "/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays",
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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountReference}/subscriptions/{subscriptionReference}/holidays/</span>
</div>

### Response Parameters

 |  | 
--------- | ------- |  
The collection of subscription holidays.| <span class="array">array[objects]</span> |
`subscriptionHolidayReference` <br />Reference to the holiday. | <span class="string">string</span> | 
`subscriptionReference` <br />Reference to the subscription.| <span class="string">string</span> | 
`startDate` <br />The date at which the holiday period should begin.| <span class="string">string</span> | 
`endDate` <br />The date at which the subscription should become active.| <span class="string">string</span> | 




