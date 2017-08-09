# Vouchers

## Add a Voucher to a Subscription

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"voucherCode":"TWOFORONE"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"voucherCode\":\"TWOFORONE\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .header("content-type", "application/json")
  .body("{\"voucherCode\":\"TWOFORONE\"}")
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
request["x-clientid"] = '1001'
request["x-clientPassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"voucherCode\":\"TWOFORONE\"}"
response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"voucherCode\":\"TWOFORONE\"}"

headers = {
    'x-clientid' : '1001',
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

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
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"voucherCode\":\"TWOFORONE\"}"}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
> The above command returns JSON structured like this:

```json

```

For an existing subscription, calling this endpoint will allow the addition of a voucher code that will take effect on the next renewal.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`voucherCode` | string | No | The voucher to be added to the subscription







## Validate a voucher code

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

This endpoint will allow the validation of a voucher against a specific client-side purchase.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/vouchers/{voucherCode}/validate</span>
</div>

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
purchaseInfo | object | No | Voucher purchase info
purchasePrice | number | No | Purchase price
discountPrice | number | No | Discount price
renewalPrice | number | No | Renewal price
nextPaymentsDates | array[string] | No | Next payments dates
voucherInfo | object | No | Voucher info
startDate | string | No | Start date
expiryDate | string | No | Expiry date
offerInfo | object | No | Voucher offer info
name | string | No | Gets or sets the Name
description | string | No | Gets or sets the Description
usageType | integer | No | Gets or sets the UsageType
applicationData | object | No | Application data
name | string | No | Gets or sets the Name
message | string | No | Gets or sets the Message
message2 | string | No | Gets or sets the Message2
addCredits | object | No | Add credits
amount | integer | No | Gets or sets the Amount
currency | string | No | Gets or sets the Currency
paymentDetailsRequired | Bool | No | Gets or sets the PaymentDetailsRequired
lowStart | object | No | Low start
percentage | number | No | Gets or sets the Percentage
numberOfPeriods | integer | No | Gets or sets the NumberOfPeriods
lockInPeriods | integer | No | Gets or sets the lockInPeriods
closeSubOnExpiry | Bool | No | Gets or sets the CloseSubOnExpiry
serviceIds | array[integer] | No | Gets or sets the ServiceIds
paymentDetailsRequired | Bool | No | Gets or sets the PaymentDetailsRequired
percentageDiscount | object | No | Percentage discount
percentage | number | No | Gets or sets the Percentage
paymentDetailsRequired | Bool | No | Gets or sets the PaymentDetailsRequired
freePeriod | object | No | Free period
numberOfPeriods | integer | No | Gets or sets the NumberOfPeriods
serviceIds | array[integer] | No | Gets or sets the ServiceIds
paymentDetailsRequired | Bool | No | Gets or sets the PaymentDetailsRequired
groupDiscount | object | No | Group discount
activationCodeActivated | Bool | No | Activation code activated
metaData | object | No | Group discount offer type
qualifyingItemCount | integer | No | Qualifying item count
freeItemCountOrDiscountAmount | number | No | Free item count or discount amount
productIds | array[integer] | No | Product ids
configurationType | string | No | Configuration type
productSource | string | No | Product source
customParameters | object | No | Custom parameters
