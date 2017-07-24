# Standard Workflows

## Get a Subscription session

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference}")

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

conn.request("GET", "/api/workflows/configurations/subscriptions/{resourceReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflows/configurations/subscriptions/{resourceReference}",
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
    "sessionToken": "7a39758cbf084f65a192ad39378f7e1b"
}
```

For the most simple integration, calling this endpoint will generate a payment session token that can be used for the client-side application (eSuite SDK) to purchase a pre-configured subscription service.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/configurations/subscriptions</span>
</div>

### Query Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`resourceReference` | string | Yes | Reference to the subscription service being purchased.
`returnUrl` | string | No | The URL location the account should be redirected to following a purchase attempt.
`processUpdateURL` | string | No | The endpoint that should be notified of the successful purchase.


## Get a Product session

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference}")

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

conn.request("GET", "/api/workflows/configurations/products/{resourceReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflows/configurations/products/{resourceReference}",
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
    "sessionToken": "7a39758cbf084f65a192ad39378f7e1b"
}
```

For the most simple integration, calling this endpoint will generate a payment session token that can be used for the client-side application (eSuite SDK) to purchase a pre-configured product.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/configurations/products</span>
</div>

### Query Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`resourceReference` | string | Yes | Reference to the subscription service being purchased.
`returnUrl` | string | No | The URL location the account should be redirected to following a purchase attempt.
`processUpdateURL` | string | No | The endpoint that should be notified of the successful purchase.


## Retrieve a Session Configuration

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflows/configurations/",
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
  "clientId": 433,
  "clientName": "Prospect Sandbox",
  "clientDefaultTimeZone": "GMT Standard Time",
  "clientDefaultUICulture": "en-GB",
  "createSessionInfo": {
    "bypassConfirmationPage": false,
    "clientUserId": "",
    "currency": "GBP",
    "cancelPaymentOnProcessUpdateFailure": false,
    "function": "AddSubscription",
    "orderItems": [
      {
        "description": "Access to great content on a week by week basis.",
        "grossAmount": 4.99,
        "netAmount": 0.0,
        "taxInfo": {
          "taxAmount": 0.0,
          "category": "Standard",
          "region": {
            "zeroRated": "",
            "country": "GBR",
            "state": "",
            "county": "",
            "city": ""
          }
        }
      }
    ],
    "requiresDelivery": true,
    "paymentMethod": "NotSet",
    "productId": 0,
    "returnUrl": "NotSet",
    "serviceId": 16026,
    "voucherCode": ""
  },
  "newAccount": true,
  "paymentOptions": {
    "cardTypes": [
      {
        "name": "Visa",
        "allowRepeats": true,
        "use3DSecureForAllTransactions": true,
        "use3DSecureOnFirstTransaction": true
      },
      {
        "name": "Mastercard",
        "allowRepeats": false,
        "use3DSecureForAllTransactions": false,
        "use3DSecureOnFirstTransaction": true
      }
    ],
    "directDebitTypes": [
      {
        "name": "Bacs",
        "allowed": false
      },
      {
        "name": "Sepa",
        "allowed": true
      }
    ]
  }
}
```

For the most simple integration, calling this endpoint will generate a payment session token that can be used for the client-side application (eSuite SDK) to purchase a pre-configured product.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/configurations/</span>
</div>

### Response Parameters

Parameter | Type  | Description | 
--------- | ------- | ------- | 
`clientId` | integer | The associated ClientId to your eSuite instance.
`clientName` | string | The name associated to your eSuite instance.
`clientDefaultTimeZone` | string | Friendly name of your configured time zone.
`clientDefaultUICulture` | string | ISO representation of the configured culture.
`createSessionInfo ` &#709; | object | string.
&#62; `bypassConfirmationPage` | string | string.
&#62; `clientUserId` | string | string.
&#62; `currency` | string | string.
&#62; `cancelPaymentOnProcessUpdateFailure` | string | string.
&#62; `function` | string | string.
&#62; `orderItems`  &#709; | string | string.
&#62;`description` | string | string.
 &#62;`grossAmount` | string | string.
 &#62;`netAmount` | string | string.
 &#62;`taxInfo`  &#709; | object | string.
 &#62;`taxAmount` | string | string.
 &#62;`category` | string | string.
 &#62;`region` &#709;| object | string.
 &#62;`zeroRated` | string | string.
 &#62;`country` | string | string.
 &#62;`state` | string | string.
 &#62;`county` | string | string.
 &#62;`city` | string | string.
&#62; &#32; &#32;`requiresDelivery` | string | string.
&#62; `paymentMethod` | string | string.
&#62; `productId` | string | string.
&#62; `returnUrl` | string | string.
&#62;`serviceId` | string | string.
&#62; `voucherCode` | string | string.
`newAccount` | bool | An indication as to whether the flow is for a new or existing account.
`paymentOptions`  &#709; | object | A collection of payment options and their configuration.
&#62;  `cardTypes`  &#709; | array[object] | string.
 &#62;  `name` | string | string.
 &#62;   `allowRepeats` | bool | An indication as to whether the card type can be used for one-click payments.
 &#62;  `use3DSecureForAllTransactions` | bool | An indication as to whether the card type requires 3D Secure.
 &#62;   `use3DSecureOnFirstTransaction` | bool | An indication as to whether the card type requires 3D Secure on first use only.
  `directDebitTypes`  &#709; | array[object] | string.
 &#62;   `name` | string | Type fo direct debit.
 &#62;  `allowed` | bool | An indication as to whether it is available.

## Complete a Subscription Purchase

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/workflow/purchases/subscriptions",
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
  "amountCharged": 10,
  "currency": "GBP",
  "paymentType": "eWallet",
  "subscriptionStatus": "Active",
  "renewalDay": 1,
  "renewalDayOffset": 0,
  "startDate": "2015-01-01T00:00:00",
  "renewalDate": "2017-01-01T00:00:00",
  "orderReference": 12548,
  "subscriptionId": 4555888,
  "subscriptionPriceId": 568845,
  "subscriptionReference": "458845",
  "resourceReference": "ResourceReference",
  "asynchronousProcessingParameters": {
    "name1": "value1"
  }
}
```

For the most simple integration, calling this endpoint will generate a payment session token that can be used for the client-side application (eSuite SDK) to purchase a pre-configured product.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflow/configurations/</span>
</div>

### Request Parameters

Parameter | Type  | Description | 
--------- | ------- | ------- | 
`voucherCode` | integer | The associated ClientId to your eSuite instance.
`cvv` | string | The name associated to your eSuite instance.
`renewalDay` | string | Friendly name of your configured time zone.
`renewalDayOffset` | string | ISO representation of the configured culture.
`startDate` | string | ISO representation of the configured culture.
`paymentMethod` | string | ISO representation of the configured culture.
`entitlements` | object | ISO representation of the configured culture.
`entitlements` > `identifier` | string | ISO representation of the configured culture.
`entitlements` > `startDate` | string | ISO representation of the configured culture.
`entitlements` > `expiryDate` | string | ISO representation of the configured culture.
`customOrderParameters` | dictionary | ISO representation of the configured culture.
`customOrderParameters` > `parameterName` | string | ISO representation of the configured culture.
`customSubscriptionParameters` | string | ISO representation of the configured culture.
`customSubscriptionParameters` > `parameterName` | string | ISO representation of the configured culture.
`taxInfo` | object | ISO representation of the configured culture.
`taxInfo` > `zeroRated` | string | ISO representation of the configured culture.
`taxInfo` > `country` | string | ISO representation of the configured culture.
`taxInfo` > `state` | string | ISO representation of the configured culture.
`taxInfo` > `county` | string | ISO representation of the configured culture.
`taxInfo` > `city` | string | ISO representation of the configured culture.
`groupSubscriptionInfo` | string | ISO representation of the configured culture.
`groupSubscriptionInfo` > `groupToken` | string | ISO representation of the configured culture.
`groupSubscriptionInfo` > `subscriberAccounts` | array[object] | ISO representation of the configured culture.
`subscriberAccounts` > `clientUserId` | string | ISO representation of the configured culture.
`subscriberAccounts` > `emailAddress` | string | ISO representation of the configured culture.
`subscriberAccounts` > `taxInfo` | object | ISO representation of the configured culture.
`taxInfo` > `zeroRated` | string | ISO representation of the configured culture.
`taxInfo` > `country` | string | ISO representation of the configured culture.
`taxInfo` > `state` | string | ISO representation of the configured culture.
`taxInfo` > `county` | string | ISO representation of the configured culture.
`taxInfo` > `city` | string | ISO representation of the configured culture.

  
