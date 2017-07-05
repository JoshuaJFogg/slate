# Subscription Services

## Purchase a Subscription

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/subscriptions \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/subscriptions/");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/subscriptions/")
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

url = URI("https://uat.mppglobal.com/api/subscriptions")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword',
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

conn.request("GET", "/api/subscriptions/", payload)

res = conn.getresponse()
data = res.read()
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/subscriptions/",
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

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
voucherCode | string | Optional | Gets or sets the Voucher code
cvv | string | Optional | Gets or sets the CVV
renewalDay | integer | Optional | Gets or sets the renewal day
renewalDayOffset | integer | Optional | Gets or sets the renewal day offset
startDate | string | Optional | Gets or sets the start date
pricing | object | Optional | Price for add subscription direct.
pricing > subscriptionId | integer | Optional | Gets or sets the price id
pricing > priceId | integer | Optional | Gets or sets the price id
pricing > paymentMethod | string | Optional | Gets or sets the payment method
pricing > currency | string | Optional | Gets or sets the currency
pricing > price | number | Optional | Gets or sets the price
pricing > taxInfo | object | Optional |  Tax region info class
pricing > taxInfo > zeroRated | string | Optional | Gets or sets the zero rated
pricing > taxInfo > country | string | Optional | Gets or sets the country
pricing > taxInfo > state | string | Optional | Gets or sets the state
pricing > taxInfo > county | string | Optional | Gets or sets the county
pricing > taxInfo > city | string | Optional | Gets or sets the city
pricing > priceItems | array[object] | Optional |  Gets or sets the price items
pricing > priceItems > externalReference | string | Optional | Gets or sets the external reference
pricing > priceItems > supplierId | integer | Optional | Gets or sets the supplier id
pricing > priceItems > price | number | Optional | Gets or sets the price
pricing > priceItems > description | string | Optional | Gets or sets the description
entitlements | array[object] | Optional |  Gets or sets the entitlements
entitlements > identifier | string | Optional | Gets or sets the identifier of the entitlement
entitlements > startDate | string | Optional | Gets or sets the create date of the entitlement
entitlements > expiryDate | string | Optional | Gets or sets the expire date of the entitlement
customOrderParameters | object | Optional | Gets or sets the custom order parameters
customSubscriptionParameters | object | Optional | Gets or sets the custom subscription parameters
groupSubscriptionInfo | object | Optional |  Group subscription info summary
groupSubscriptionInfo > groupToken | string | Optional | Gets or sets the group token
groupSubscriptionInfo > subscriberAccounts | array[object] | Optional | Gets or sets the subscriber accounts
 > subscriberAccounts > clientUserId | string | Optional | Gets or sets the client user id
 > subscriberAccounts > emailAddress | string | Optional | Email Address
 > subscriberAccounts > taxInfo | object | Optional | Tax region info class
 > taxInfo > zeroRated | string | Optional | Gets or sets the zero rated
 > taxInfo > country | string | Optional | Gets or sets the country
 > taxInfo > state | string | Optional | Gets or sets the state
 > taxInfo > county | string | Optional | Gets or sets the county
 > taxInfo > city | string | Optional | Gets or sets the city






## Retrieve an Account's Subscriptions

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions</span>
</div>

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
subscriptions | array[object] | optional | Subscriptions
subscriptions > accountSubscriptionInfo | object | optional | Account Subscription Info
subscriptions > accountSubscriptionInfo > expiryDate | string | optional | Expiry Date
subscriptions > accountSubscriptionInfo > firstNonDiscountedBillingPointUtc | string | optional | First Non Discounted Billing PointUTC
subscriptions > accountSubscriptionInfo > lastDiscountedBillingPointUtc | string | optional | Last Discounted Billing PointUTC
subscriptions > accountSubscriptionInfo > paymentMethod | string | optional | Payment Method
subscriptions > accountSubscriptionInfo > recurringPaymentInfo | object | optional | Recurring Payment Info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > subscriptionReference | integer | optional | Subscription Reference
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > resourceReference | string | optional | Unique Resource Reference
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > configuredSubscriptionPrice | number | optional | Configured Subscription Price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > subscribedPrice | number | optional | Subscribed Price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > currency | string | optional | Currency
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > recurringPaymentEnable | string | optional | Recurring Payment Enable
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > subscriptionLockedIn | string | optional | Subscription LockedIn
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > nextPaymentDate | string | optional | Next Payment Date
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo | object | optional | Previous Billing Info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > subscriptionPriceId | integer | optional | Subscription Price Id
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > totalAmount | number | optional | Total Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > totalTaxAmount | number | optional | Total Tax Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > totalNetAmount | number | optional | Total Net Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > billingDate | string | optional | Billing Date
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > paymentDate | string | optional | Payment Date
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo | array[object] | optional | Tax info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > regionName | string | optional | Region Name
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > regionType | string | optional | Region Type
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > displayName | string | optional | Display Name
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > category | string | optional | Category
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > rate | number | optional | Rate
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > amount | number | optional | Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems | array[object] | optional | Price Items
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > thirdPartyRef | string | optional | Gets or sets the external reference
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > supplierId | integer | optional | Gets or sets the supplier id
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > price | number | optional | Gets or sets the price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > description | string | optional | Gets or sets the description
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > isGrossAmount | string | optional | Specify whether is groos amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > taxCategoryName | string | optional | Tax Category Name
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo | object | optional | Group Subscription Info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > licenseLevel | integer | optional | License Level
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > overflowLevel | integer | optional | Overflow Level
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList | array[object] | optional | Subscriber List
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList > subscriptionId | integer | optional | SubscriptionId
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList > emailAddress | string | optional | Email Address
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList > clientUserId | string | optional | ClientUserId
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > overFlowCount | integer | optional | Overflow Count
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > fullSubscriptionsCount | integer | optional | Full Subscriptions Count
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > currentUserInOverFlow | string | optional | Specify whether Current User In OverFlow
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > voucherCodes | object | optional | Voucher Code
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > voucherCodes > voucherCode | string | optional | Voucher Code
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > voucherCodes > discountPrice | number | optional | Discount Price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > statusInfo | object | optional | Status info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > statusInfo > statusId | integer | optional | Status id
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > statusInfo > statusDescription | string | optional | Status description
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > customParameters | object | optional | Custom parameters
subscriptions > accountSubscriptionInfo > paymentScheduleInfo | object | optional | Payment Schedule Info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > startDate | string | optional | Start Date
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > frequency | string | optional | Start Date
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > totalAmount | number | optional | Total Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > paymentDayOffset | integer | optional | Payment Day Offset
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > paymentDay | integer | optional | Payment Day
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > currency | string | optional | Currency
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > paymentMethod | string | optional | Payment Method
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments | string | optional | Scheduled Payments
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > orderId | integer | optional | Order Id
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > orderDate | string | optional | Order Date
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > status | string | optional | Status
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo | object | optional | Price Info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > grossAmount | number | optional | Gross Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > netAmount | number | optional | Gross Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > totalTaxAmount | number | optional | Total Tax Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo | array[object] | optional | Tax Info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > regionName | string | optional | Region Name
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > regionType | string | optional | Region Type
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > displayName | string | optional | Display Name
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > category | string | optional | Category
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > rate | number | optional | Rate
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > amount | number | optional | Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > statusInfo | object | optional | Status info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > statusId | integer | optional | Status id
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > statusDescription | string | optional | Status description
subscriptions > defaultSubscriptionInfo | object | optional | Default Subscription Info
subscriptions > defaultSubscriptionInfo > customParameters | object | optional | Custom Parameters
subscriptions > defaultSubscriptionInfo > subscriptionId | integer | optional | Subscription Id
subscriptions > defaultSubscriptionInfo > subscriptionStatus | string | optional | Subscription Status
subscriptions > defaultSubscriptionInfo > subscriptionTitle | string | optional | Subscription Title
subscriptions > defaultSubscriptionInfo > subscriptionGroup | string | optional | Subscription Group







## Complete Asynchronous Subscription Purchase

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions</span>
</div>

### PATCH Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
amountCharged | number | Optional | Amount charged
currency | string | Optional | Currency
paymentType | string | Optional | Payment type
subscriptionStatus | string | Optional | Subscription status
renewalDay | integer | Optional | Renewal day
renewalDayOffset | integer | Optional | Renewal day offset
startDate | string | Optional | Start date
renewalDate | string | Optional | Renewal date
orderReference | integer | Optional | Order reference
subscriptionId | integer | Optional | Subscription id
subscriptionPriceId | integer | Optional | Subscription price id
subscriptionReference | object | Optional | Subscription reference
resourceReference | object | Optional | Resource reference
asynchronousProcessingParameters | object | Optional | Asynchronous Processing Parameters
sessionToken | object | Optional | Session token








## Edit Status

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/status</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
renewals | string | Optional | Renewals






## Cancel Subscription

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
status | string | Optional | The status of the subscription





