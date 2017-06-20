# Vouchers

## Add a Voucher to a Subscription

```shell
curl --request POST \
  --url http://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{"voucherCode":"TWOFORONE"}'
```

```csharp
var client = new RestClient("http://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("application/json", "{\"voucherCode\":\"TWOFORONE\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("http://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers")
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

url = URI("http://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers")

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
    'x-tokenid': "1001",
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
  "url": "http://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers",
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


Description of what the endpoint does.

### HTTP Request

`POST http://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/{subscriptionId}/vouchers`

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
voucherCode | string | Optional | The voucher to be added to the subscription







## Validate a voucher code

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

`GET http://uat.mppglobal.com/api/vouchers/{voucherCode}/validate`

### Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
purchaseInfo | object | Optional | Voucher purchase info
purchasePrice | number | Optional | Purchase price
discountPrice | number | Optional | Discount price
renewalPrice | number | Optional | Renewal price
nextPaymentsDates | array[string] | Optional | Next payments dates
voucherInfo | object | Optional | Voucher info
startDate | string | Optional | Start date
expiryDate | string | Optional | Expiry date
offerInfo | object | Optional | Voucher offer info
name | string | Optional | Gets or sets the Name
description | string | Optional | Gets or sets the Description
usageType | integer | Optional | Gets or sets the UsageType
applicationData | object | Optional | Application data
name | string | Optional | Gets or sets the Name
message | string | Optional | Gets or sets the Message
message2 | string | Optional | Gets or sets the Message2
addCredits | object | Optional | Add credits
amount | integer | Optional | Gets or sets the Amount
currency | string | Optional | Gets or sets the Currency
paymentDetailsRequired | boolean | Optional | Gets or sets the PaymentDetailsRequired
lowStart | object | Optional | Low start
percentage | number | Optional | Gets or sets the Percentage
numberOfPeriods | integer | Optional | Gets or sets the NumberOfPeriods
lockInPeriods | integer | Optional | Gets or sets the lockInPeriods
closeSubOnExpiry | boolean | Optional | Gets or sets the CloseSubOnExpiry
serviceIds | array[integer] | Optional | Gets or sets the ServiceIds
paymentDetailsRequired | boolean | Optional | Gets or sets the PaymentDetailsRequired
percentageDiscount | object | Optional | Percentage discount
percentage | number | Optional | Gets or sets the Percentage
paymentDetailsRequired | boolean | Optional | Gets or sets the PaymentDetailsRequired
freePeriod | object | Optional | Free period
numberOfPeriods | integer | Optional | Gets or sets the NumberOfPeriods
serviceIds | array[integer] | Optional | Gets or sets the ServiceIds
paymentDetailsRequired | boolean | Optional | Gets or sets the PaymentDetailsRequired
groupDiscount | object | Optional | Group discount
activationCodeActivated | boolean | Optional | Activation code activated
metaData | object | Optional | Group discount offer type
qualifyingItemCount | integer | Optional | Qualifying item count
freeItemCountOrDiscountAmount | number | Optional | Free item count or discount amount
productIds | array[integer] | Optional | Product ids
configurationType | string | Optional | Configuration type
productSource | string | Optional | Product source
customParameters | object | Optional | Custom parameters
