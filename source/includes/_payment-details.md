# Payment Details

## Add a Credit/Debit Card

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/card \
  --header 'content-type: application/json' \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-clientid: 1001' \
  --data '{"cardNumber":"4111111111111111","cardType":"visa","expiryDate":"11/17","cvv":"123","setDefault":true,"skipPreAuth":false}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/card");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("application/json", "{\"cardNumber\":\"4111111111111111\",\"cardType\":\"visa\",\"expiryDate\":\"11/17\",\"cvv\":\"123\",\"setDefault\":true,\"skipPreAuth\":false}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/card")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .header("content-type", "application/json")
  .body("{\"cardNumber\":\"4111111111111111\",\"cardType\":\"visa\",\"expiryDate\":\"11/17\",\"cvv\":\"123\",\"setDefault\":true,\"skipPreAuth\":false}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/card")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-tokenid"] = '1001'
request["x-sessionid"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"cardNumber\":\"4111111111111111\",\"cardType\":\"visa\",\"expiryDate\":\"11/17\",\"cvv\":\"123\",\"setDefault\":true,\"skipPreAuth\":false}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"cardNumber\":\"4111111111111111\",\"cardType\":\"visa\",\"expiryDate\":\"11/17\",\"cvv\":\"123\",\"setDefault\":true,\"skipPreAuth\":false}"

headers = {
    'x-clientid' : '1001',
    'x-sessionid': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/{accountId}/payment-details/card", payload, headers)

res = conn.getresponse()
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/card",
  "method": "PUT",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "4034510a90854b1a887beec9c5675ff5",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"cardNumber\":\"4111111111111111\",\"cardType\":\"visa\",\"expiryDate\":\"11/17\",\"cvv\":\"123\",\"setDefault\":true,\"skipPreAuth\":false}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
{
  "paymentDetailId": "604DB6C40EAA4C04BC6E65C4E4135069"
}
```

In order to make a purchase using a credit or debit card, a card must be added to the eSuite platform.

### URL End-point

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/:accountId/payment-details/card</span>
</div>

### POST Parameters

 |  |  | 
--------- | ------- | ------- | 
`cardNumber` <br />The 13-19 digit number on the face of a credit or debit card.| <span class="string">string</span> | <span class="required">Required</span> | 
`cardType` <br />The type of card the account is adding, Visa, Mastercard, Amex, Diners, Discover.| <span class="string">string</span> | <span class="required">Required</span> | 
`expiryDate` <br />The date at which the card will expire, mm-yy.| <span class="string">string</span> | <span class="required">Required</span> | 
`issueCode` <br />The number of cards the acquirer has issues for the account.| <span class="string">string</span> |  | 
`securityCode` <br />3-4 digit code on the rear of a card.| <span class="string">string</span> | <span class="required">Required</span> | 
`billingHouseName` <br />The building name in which the card is registered.| <span class="string">string</span> |  | 
`billingHouseFlatNumber` <br />The building number at which the card is registered.| <span class="string">string</span> |  | 
`billingStreet` <br />The street in which the card is registered.| <span class="string">string</span> |  | 
`billingDistrict` <br />The district in which the card is registered.| <span class="string">string</span> |  | 
`billingTownCity` <br />The town or city in which the card is registered.| <span class="string">string</span> |  | 
`billingPostcode` <br />The post code in which the card is registered.| <span class="string">string</span> |  | 
`billingCountry` <br />The country in which the card is registered.| <span class="string">string</span> |  | 
`setDefault` <br />An indication as to whether this card will be the customers default card.| <span class="bool">bool</span> |  | 
`associatedName` <br />A friendly name to identify the payment card to the account.| <span class="string">string</span> |  | 
`skipPreAuth` <br />An indication as to whether the card should be authorised as part of the addition process.| <span class="bool">bool</span> |  | 


<aside class="error">
Remember — you must authorise a card before it can be used
</aside>

## Add a BACS Direct Debit Wallet

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/bacs \
  --header 'content-type: application/json' \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-clientid: 1001' \
  --data '{"accountHolderName":"Steven Smith","accountNumber":"11111111","sortCode":"000000"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/bacs");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-sessionid", "Str0ngP@ssword");
request.AddHeader("x-tokenid", "1001");
request.AddParameter("application/json", "{\"accountHolderName\":\"John Smith\",  "\"accountNumber\":\"11111111\",\"sortCode\":\"000000\"}", 
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/bacs")
  .header("x-tokenid", "1001")
  .header("x-sessionid", "Str0ngP@ssword")
  .header("content-type", "application/json")
  .body("{\"accountHolderName\":\"Steven Smith\",\"accountNumber\":\"11111111\",\"sortCode\":\"000000\"}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/bacs")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-tokenid"] = 'Str0ngP@ssword'
request["x-sessionid"] = '1001'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"accountHolderName\":\"John Smith\",\"accountNumber\":\"11111111\"}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"accountHolderName\":\"John Smith\",\"accountNumber\":\"11111111\",\"sortCode\":\"000000\"}"

headers = {
    'x-clientpassword': "Str0ngP@ssword",
    'x-clientid': "1001",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/{accountId}/payment-details/bacs", payload, headers)

res = conn.getresponse()
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/bacs",
  "method": "PUT",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "4034510a90854b1a887beec9c5675ff5",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"accountHolderName\":\"John Smith\",\"accountNumber\":\"11111111\",\"sortCode\":\"000000\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns an empty response alongside a HTTP 204


In order to make a purchase using BACS Direct Debit, a BACS wallet must be added to the eSuite platform.

### URL End-point

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/:accountId/payment-details/bacs</span>
</div>

### POST Parameters

 |  |  | 
--------- | ------- | ------- | 
`accountHolderName` <br />The name associated to the bank account.| <span class="string">string</span> | <span class="required">Required</span> | 
`accountNumber` <br />The UK bank account number.| <span class="string">string</span> | <span class="required">Required</span> | 
`sortCode` <br />The bank sort code associated to the account.| <span class="string">string</span> | <span class="required">Required</span> | 
`bacsReference` <br />The existing mandate reference if the account is coming from another system.| <span class="string">string</span> |  | 
`serviceId` <br />The eSuite ServiceId that this BACS wallet will be used for.| <span class="integer">integer</span> | <span class="required">Required</span> | 


## Add a SEPA Direct Debit Wallet

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/%7BaccountId%7D/payment-details/sepa \
  --header 'content-type: application/json' \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-clientid: 1001' \
  --data '{"accountHolderName":"Steve Smith","iban":"IE64BOFI90583812345678",
  "bic":"BOFIIE2D"}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/%7BaccountId%7D/payment-details/sepa");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("application/json", "{\"accountHolderName\":\"Steve Smith\", "\"iban\":\"IE64BOFI90583812345678\",\"bic\":\"BOFIIE2D\"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/sepa")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .header("content-type", "application/json")
  .body("{\"accountHolderName\":\"John Smith\",\"iban\":\"IE64BOFI90583812345678\",\"bic\":\"BOFIIE2D\")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/sepa")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientpassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"accountHolderName\":\"John Smith\",\"iban\":\"IE64BOFI90583812345678\",\"bic\":\"BOFIIE2D\"}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"accountHolderName\":\"John Smith\",\"iban\":\"IE64BOFI90583812345678\",\"bic\":\"BOFIIE2D\"}"

headers = {
    'x-clientid': "1001",
    'x-clientpassword': "Str0ngP@ssword",
    'x-version': '9.0.0',
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/{accountId}/payment-details/sepa", payload, headers)

res = conn.getresponse()
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/accounts/{accountId}/payment-details/sepa",
  "method": "PUT",
  "headers": {
    "x-tokenid": "BE52ADA2064C4F9A9D90F28D066D1RFT",
    "x-sessionid": "4034510a90854b1a887beec9c5675ff5",
    "x-version": "9.0.0",
    "origin": "https://www.mppglobal.com",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\"accountHolderName\":\"John Smith\",\"iban\":\"IE64BOFI90583812345678\",\"bic\":\"BOFIIE2D\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns an empty response alongside a HTTP 204


In order to make a purchase using SEPA Direct Debit, a SEPA wallet must be added to the eSuite platform.

### URL End-point

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/:accountId/payment-details/sepa</span>
</div>

### POST Parameters

 |  |  | 
--------- | ------- | ------- | 
`accountHolderName` <br />The name associated to the bank account.| <span class="string">string</span> | <span class="required">Required</span> | 
`iban` <br />The bank account number.| <span class="string">string</span> | <span class="required">Required</span> | 
`bic` <br />The bank identification code associated to the account.| <span class="string">string</span> | <span class="required">Required</span> | 
`serviceId` <br />The eSuite ServiceId that this BACS wallet will be used for.| <span class="integer">integer</span> | <span class="required">Required</span> | 



## Get payment details

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/{accountId}/payment-details \
  --header("x-clientid", "1001") \
  --header("x-clientpassword", "Str0ngP@ssword")\
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details");
var request = new RestRequest(Method.GET);
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/{accountId}/payment-details")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-tokenid"] = '1001'
request["x-sessionid"] = 'Str0ngP@ssword'
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
    'x-sessionid': "Str0ngP@ssword",
    'x-version': '9.0.0'
    }

conn.request("GET", "/api/accounts/{accountId}/payment-details", payload, headers)

res = conn.getresponse()
```
> The above command returns JSON structured like this:

```json
{
  "paymentDetails": {
    "cards": [
      {
        "associatedName": "Joe Bloggs",
        "billingHouseName": "Joe",
        "billingHouseFlatNumber": "100",
        "billingStreet": "Wigan",
        "billingDistrict": "Manchester",
        "billingTownCity": "Bolton",
        "billingCounty": "Manchester",
        "billingPostcode": "111111",
        "billingCountry": "United Kindom",
        "cardNumber": "****-****-****-1111",
        "cardType": "visa",
        "expiryDate": "01/20",
        "isDefault": true,
        "issueCode": "123",
        "paymentDetailId": "604DB6C40EAA4C04BC6E65C4E4135069"
      }
    ],
    "payPal": {
      "paymentDetailId": "604DB6C40EAA4C04BC6E65C4E4135785"
    }
  }
}
```

This endpoint retrieves the payment details stored against an eSuite account.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/:accountId/payment-details</span>
</div>

### Response Parameters

 |  |  
--------- | ------- | 
`paymentDetails` <br />The collection of payment details available for the account. | <span class="array">array[object]</span> | 
`cards` <br />The collection of payment cards available for the account. | <span class="array">array[object]</span> | 
`cards \ associatedName` <br />Associated name to identify the card. | <span class="string">string</span> | 
`cards \ billingHouseName` <br />The name of the house the card is associated to. | <span class="string">string</span> | 
`cards \ billingHouseFlatNumber` <br />The number of the house the card is associated to. | <span class="string">string</span> | 
`cards \ billingStreet` <br />The street associated to the card. | <span class="string">string</span> | 
`cards \ billingDistrict` <br />The district associated to the card. | <span class="string">string</span> | 
`cards \ billingTownCity`<br />The town or city associated to the card. | <span class="string">string</span> | 
`cards \ billingCounty` <br />The county associated to the card. | <span class="string">string</span> | 
`cards \ billingPostcode` <br />The postcode associated to the card. | <span class="string">string</span> | 
`cards \ billingCountry` <br />The country associated to the card. | <span class="string">string</span> | 
`cards \ cardNumber` <br />A masked representation of the card. | <span class="string">string</span> | 
`cards \ cardType` <br />The card brand associated to the card. | <span class="string">string</span> | 
`cards \ expiryDate` <br />The date at which the card is due to expire. | <span class="string">string</span> | 
`cards \ isDefault` <br />An indication as to whether this card is the default for the account. | <span class="bool">bool</span> | 
`cards \ issueCode` <br />Issue number typically found on debit and bank cards. | <span class="string">string</span> | 
`cards \ paymentDetailId` <br />The identifier of the card within eSuite. | <span class="string">string</span> | 
`payPal` <br />PayPal object detailing information about the customers PayPal account. | <span class="object">object</span> | 
`paymentDetailId` <br />The identifier of the PayPal wallet within eSuite. | <span class="string">string</span> | 

<aside class="warning">Only credit/debit cards and repeatable PayPal tokens are returned via this endpoint.</aside>
