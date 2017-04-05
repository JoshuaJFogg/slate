# Payment Details

## Add a Credit/Debit Card

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/123456/payment-details/card \
  --header 'content-type: application/json' \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-clientid: 1001' \
  --data '{"cardNumber":"4111111111111111","cardType":"Visa",
  "expiryDate":"01/19",  "issueCode":null,"securityCode":"123", 
  "billingHouseName":"Lilac Cottage","billingHouseFlatNumber":"12",
  "billingStreet":"Windermere Road","billingDistrict":null,
  "billingTownCity":"Chester","billingCounty":"Cheshire",
  "billingPostcode":"CH638BF","billingCountry":"United Kingdom",
  "setDefault":true,"associatedName":"My Visa Card","skipPreAuth":false}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/123456/payment-details/card");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("application/json", "{\"cardNumber\":\"4111111111111111\",\"cardType\":\"Visa\",
  + "\"expiryDate\":\"01/19\",\"issueCode\":null,\"securityCode\":\"123\",
  + "\"billingHouseName\":\"Lilac Cottage\",\"billingHouseFlatNumber\":\"12\",\"billingStreet\":\"Windermere Road\",
  + "\"billingDistrict\":null,\"billingTownCity\":\"Chester\",\"billingCounty\":\"Cheshire\",
  + "\"billingPostcode\":\"CH638BF\",\"billingCountry\":\"United Kingdom\",\"setDefault\":true,
  + "\"associatedName\":\"My Visa Card\",\"skipPreAuth\":false}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/123456/payment-details/card")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .header("content-type", "application/json")
  .body("{\"cardNumber\":\"4111111111111111\",\"cardType\":\"Visa\",\"expiryDate\":\"01/19\",\"issueCode\":null,\"securityCode\":\"123\",\"billingHouseName\":\"Lilac Cottage\",\"billingHouseFlatNumber\":\"12\",\"billingStreet\":\"Windermere Road\",\"billingDistrict\":null,\"billingTownCity\":\"Chester\",\"billingCounty\":\"Cheshire\",\"billingPostcode\":\"CH638BF\",\"billingCountry\":\"United Kingdom\",\"setDefault\":true,\"associatedName\":\"My Visa Card\",\"skipPreAuth\":false}").asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/123456/payment-details/card")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-tokenid"] = '1001'
request["x-sessionid"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"cardNumber\":\"4111111111111111\",\"cardType\":\"Visa\",\"expiryDate\":\"01/19\",\"issueCode\":null,\"cvv\":\"123\",\"billingHouseName\":\"Lilac House\",\"billingHouseFlatNumber\":\"12\",\"billingStreet\":\"Windermere Road\",\"billingDistrict\":null\"billingTownCity\":\"Chester\",\"billingCounty\":\"Cheshire\",\"billingPostcode\":\"CH638BF\",\"billingCountry\":\"United Kingdom\",\"setDefault\":true,\"associatedName\":\"My Visa Card\",\"skipPreAuth\":false}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"cardNumber\":\"4111111111111111\",\"cardType\":\"Visa\",\"expiryDate\":\"01/19\",\"issueCode\":null,\"cvv\":\"123\",\"billingHouseName\":\"Lilac House\",\"billingHouseFlatNumber\":\"12\",\"billingStreet\":\"Windermere Road\",\"billingDistrict\":null,\"billingTownCity\":\"Chester\"\"billingCounty\":\"Cheshire\",\"billingPostcode\":\"CH638BF\",\"billingCountry\":\"United Kingdom\",\"setDefault\":true,\"associatedName\":\"My Visa Card\",\"skipPreAuth\":false}"

headers = {
    'x-tokenid': "1001",
    'x-sessionid': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/123456/payment-details/card", payload, headers)

res = conn.getresponse()
```

> The above command returns JSON structured like this:

```json
{
  "paymentDetailId": "604DB6C40EAA4C04BC6E65C4E4135069"
}
```

In order to make a purchase using a credit or debit card, a card must be added to the eSuite platform.

### URL End-point

`POST https://uat.mppglobal.com/api/accounts/:accountId/payment-details/card`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
cardNumber | string | Yes | The 13-19 digit number on the face of a credit or debit card.
cardType | string | Yes | The type of card the account is adding, Visa, Mastercard, Amex, Diners, Discover.
expiryDate | string | Yes | The date at which the card will expire, mm-yy.
issueCode | string | No | The number of cards the acquirer has issues for the account.
securityCode | string | Yes | 3-4 digit code on the rear of a card.
billingHouseName | string | No | The building name in which the card is registered.
billingHouseFlatNumber | string | No | The building number at which the card is registered.
billingStreet | string | No | The street in which the card is registered.
billingDistrict | string | No | The district in which the card is registered.
billingTownCity | string | No | The town or city in which the card is registered.
billingPostcode | string | No | The post code in which the card is registered.
billingCountry | string | No | The country in which the card is registered.
setDefault | boolean | No | An indication as to whether this card will be the customers default card.
associatedName | string | No | A friendly name to identify the payment card to the account.
skipPreAuth | boolean | No | An indication as to whether the card should be authorised as part of the addition process.


<aside class="error">
Remember — you must authorise a card before it can be used
</aside>

## Add a BACS Direct Debit Wallet

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/123456/payment-details/bacs \
  --header 'content-type: application/json' \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-clientid: 1001' \
  --data '{"accountHolderName":"Steven Smith","accountNumber":"11111111","sortCode":"000000",
  "bacsReference":"AE34567LZ","serviceId":124875}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/123456/payment-details/bacs");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-sessionid", "Str0ngP@ssword");
request.AddHeader("x-tokenid", "1001");
request.AddParameter("application/json", "{\"accountHolderName\":\"Steven Smith\",
  "\"accountNumber\":\"11111111\",\"sortCode\":\"000000\",\"bacsReference\":\"AE34567LZ\",\"serviceId\":124875}", 
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/123456/payment-details/bacs")
  .header("x-tokenid", "1001")
  .header("x-sessionid", "Str0ngP@ssword")
  .header("content-type", "application/json")
  .body("{\"accountHolderName\":\"Steven Smith\",\"accountNumber\":\"11111111\",\"sortCode\":\"000000\",
    "\"bacsReference\":\"AE34567LZ\",\"serviceId\":124875}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/123456/payment-details/bacs")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-tokenid"] = 'Str0ngP@ssword'
request["x-sessionid"] = '1001'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"accountHolderName\":\"Steven Smith\",\"accountNumber\":\"11111111\",\"sortCode\":\"000000\",\"bacsReference\":\"AE34567LZ\",\"serviceId\":124875}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"accountHolderName\":\"Steven Smith\",\"accountNumber\":\"11111111\",\"sortCode\":\"000000\",\"bacsReference\":\"AE34567LZ\",\"serviceId\":124875}"

headers = {
    'x-clientpassword': "Str0ngP@ssword",
    'x-clientid': "1001",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/123456/payment-details/bacs", payload, headers)

res = conn.getresponse()
```

> The above command returns an empty response alongside a HTTP 204


In order to make a purchase using BACS Direct Debit, a BACS wallet must be added to the eSuite platform.

### URL End-point

`POST https://uat.mppglobal.com/api/accounts/:accountId/payment-details/bacs`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
accountHolderName | string | Yes | The name associated to the bank account.
accountNumber | string | Yes | The UK bank account number.
sortCode | string | Yes | The bank sort code associated to the account.
bacsReference | string | No | The existing mandate reference if the account is coming from another system.
serviceId | integer | Yes | The eSuite ServiceId that this BACS wallet will be used for.


## Add a SEPA Direct Debit Wallet

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/%7BaccountId%7D/payment-details/sepa \
  --header 'content-type: application/json' \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-clientid: 1001' \
  --data '{"accountHolderName":"Steve Smith","iban":"IE64BOFI90583812345678",
  "bic":"BOFIIE2D","serviceId":148754}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/%7BaccountId%7D/payment-details/sepa");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("application/json", "{\"accountHolderName\":\"Steve Smith\",
 "\"iban\":\"IE64BOFI90583812345678\",\"bic\":\"BOFIIE2D\",\"serviceId\":148754}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/accounts/123456/payment-details/sepa")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .header("content-type", "application/json")
  .body("{\"accountHolderName\":\"Steve Smith\",\"iban\":\"IE64BOFI90583812345678\",\"bic\":\"BOFIIE2D\",
   "\"serviceId\":148754}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/123456/payment-details/sepa")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["x-clientid"] = '1001'
request["x-clientpassword"] = 'Str0ngP@ssword'
request["x-version"] = '9.0.0'
request["content-type"] = 'application/json'
request.body = "{\"accountHolderName\":\"Steve Smith\",\"iban\":\"IE64BOFI90583812345678\",\"bic\":\"BOFIIE2D\",\"serviceId\":\"148754\"}"

response = http.request(request)
```

```python
import http.client

conn = http.client.HTTPSConnection("uat.mppglobal.com")

payload = "{\"accountHolderName\":\"Steve Smith\",\"iban\":\"IE64BOFI90583812345678\",\"bic\":\"BOFIIE2D\",\"serviceId\":\"148754\"}"

headers = {
    'x-clientid': "1001",
    'x-clientpassword': "Str0ngP@ssword",
    'x-version': "9.0.0",
    'content-type': "application/json"
    }

conn.request("POST", "/api/accounts/123456/payment-details/sepa", payload, headers)

res = conn.getresponse()
```
> The above command returns an empty response alongside a HTTP 204


In order to make a purchase using SEPA Direct Debit, a SEPA wallet must be added to the eSuite platform.

### URL End-point

`POST https://uat.mppglobal.com/api/accounts/:accountId/payment-details/sepa`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
accountHolderName | string | Yes | The name associated to the bank account.
iban | string | Yes | The bank account number.
bic | string | Yes | The bank identification code associated to the account.
serviceId | integer | Yes | The eSuite ServiceId that this BACS wallet will be used for.



## Get payment details

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/accounts/123456/payment-details \
  --header("x-clientid", "1001") \
  --header("x-clientpassword", "Str0ngP@ssword")\
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/accounts/123456/payment-details");
var request = new RestRequest(Method.GET);
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/accounts/123456/payment-details")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/accounts/123456/payment-details")

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
    'x-tokenid': "1001",
    'x-sessionid': "Str0ngP@ssword",
    'x-version': "9.0.0"
    }

conn.request("GET", "/api/accounts/123456/payment-details", payload, headers)

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
        "cardNumber": "4111111111111111",
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

<aside class="warning">Only credit/debit cards and repeatable PayPal tokens are returned via this end-point.</aside>

### HTTP Request

`GET https://uat.mppglobal.com/api/accounts/:accountId/payment-details`


