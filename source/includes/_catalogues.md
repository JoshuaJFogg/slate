# Catalogue Management

## Retrieve All Subscription Services


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
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/subscriptions")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/subscriptions/")

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
{
  "subscriptionsInfo": [
    {
      "subscriptionId": "11165",
      "resourceReference": "0010SGFC5SYCG6AEM3",
      "subscriptionGroup": "Monthly Magazine",
      "subscriptionGroupTag": "Monthly Subscription",
      "subscriptionGroupStatus": "Active",
      "subscriptionDescription": "Day Digital Monthly Subscription",
      "subscriptionTitle": "Monthly",
      "subscriptionType": "SubscriptionPeriod",
      "subscriptionStatus": "Active",
      "initialPricingEnabled": false,
      "trialInfo": {
        "trialEnabled": false,
        "trialUnit": "Month",
        "trialPeriod": 0,
        "discountPercentage": 0,
        "nonPaymentTrial": false
      },
      "contractInfo": {
        "contractUnit": "Minutes",
        "contractPeriod": 5,
        "autoRenewDefault": "Enabled"
      },
      "pricingInfo": [
        {
          "currency": "GBP",
          "initialPrice": 0,
          "priceIsGross": true,
          "renewalPrice": 2.5,
          "priceId": 16889,
          "taxCategory": "Standard",
          "resourceReference": "0010NWR3QDGG734QM2",
          "paymentMethod": "eWallet"
        }
      ],
      "allowedPaymentMethods": [
        "CreditCard",
        "PayPal",
        "DirectDebit"
      ],
      "customParameters": [
        {
          "parameterName": "ThirdPartyRef",
          "parameterType": "String",
          "parameterValue": "1221332525"
        }
      ],
      "images": [
        {
          "imageId": 14,
          "displayName": "TestImage",
          "fileName": "433_62c5f972-80ad-4239-97fc-428eb93916e8",
          "default": true,
          "location": "https://s3-eu-west-1.amazonaws.com/mpp-dev-one/433_62c5f972-80ad-4239-97fc-428eb93916e8"
        }
      ],
      "groupLicensing": {
        "standard": 1,
        "overflow": 0
      }
    }
  ]
}
```

This endpoint will return all configured subscription services for your instance of eSuite.

### HTTP Request

`GET http://uat.mppglobal.com/api/subscriptions`

### Response Parameters

Parameter | Type | Description | 
--------- | ------- |  ----------- |
subscriptionsInfo | array[object] | Object containing all subscription services on the Client
subscriptionsInfo > subscriptionId | string | The identifier of the subscription
subscriptionsInfo > resourceReference | string | The reference of the subscription
subscriptionsInfo > subscriptionGroup | string | The subscription group the subscription belongs
subscriptionsInfo > subscriptionGroupTag | string | The subscription group tag the subscription belongs
subscriptionsInfo > subscriptionGroupStatus | string | The status of the subscription group
subscriptionsInfo > subscriptionDescription | string | A description of the subscription service
subscriptionsInfo > subscriptionTitle | string | A title of the subscription service
subscriptionsInfo > subscriptionType | string | The type of subscription service
subscriptionsInfo > subscriptionStatus | string | The status of the subscription service
subscriptionsInfo > initialPricingEnabled | boolean | An indication whether initial pricing is enabled
subscriptionsInfo > trialInfo | object | Object containing trial information
subscriptionsInfo > trialInfo > trialEnabled | boolean | An indication whether trials are enabled
subscriptionsInfo > trialInfo > trialUnit | string | Duration type (month, day, year, etc.)
subscriptionsInfo > trialInfo > trialPeriod | integer | How long the duration should be
subscriptionsInfo > trialInfo > discountPercentage | number | How much the price will be discounted
subscriptionsInfo > trialInfo > nonPaymentTrial | boolean | An indication to whether payment details are required
subscriptionsInfo > contractInfo | object | Object containing contract information
subscriptionsInfo > contractInfo > contractUnit | string | Type of contract (day, week, month, etc.)
subscriptionsInfo > contractInfo > contractPeriod | integer | Number of units the contract runs
subscriptionsInfo > contractInfo > autoRenewDefault | string | Indication whether the subscription service will renew
subscriptionsInfo > pricingInfo | array[object] | The collection of all prices configured for the subscription service
subscriptionsInfo > pricingInfo > currency | string | The currency the price is associated to
subscriptionsInfo > pricingInfo > initialPrice | number | The price that will be paid on sign-up of the subscription service
subscriptionsInfo > pricingInfo > priceIsGross | boolean | An indication as to whether the price returned is the gross or net price
subscriptionsInfo > pricingInfo > renewalPrice | number | The price that will be paid on subsequent renewal purchases
subscriptionsInfo > pricingInfo > priceId | integer | The eSuite Identifer for the price
subscriptionsInfo > pricingInfo > taxCategory | string | Tax category
subscriptionsInfo > pricingInfo > resourceReference | string | The identifier for the price that should be used on purchase calls
subscriptionsInfo > pricingInfo > paymentMethod | string | The payment method associated to the specific price
subscriptionsInfo > allowedPaymentMethods | array[string] | The collection of payment methods available on the subscription service
subscriptionsInfo > customParameters | array[object] | Custom parameters
subscriptionsInfo > customParameters > parameterName | string | Name of the custom parameter
subscriptionsInfo > customParameters > parameterType | string | An indication as to what data type the parameter should be displayed e.g. HTML, Decimal
subscriptionsInfo > customParameters > parameterValue | string | Value of the custom parameter
subscriptionsInfo > images | array[object] | The overarching object which contains all images for the subscription service
subscriptionsInfo > images > imageId | integer | The eSuite identifier for the image
subscriptionsInfo > images > displayName | string | Display name
subscriptionsInfo > images > fileName | string | The file name associated to the image
subscriptionsInfo > images > default | boolean | An indication as to whether the image is the default image for the subscription service 
subscriptionsInfo > images > location | string | The URL location the image is hosted at
subscriptionsInfo > groupLicensing | object | A breakdown of how many group licenses are associated to the subscription service
subscriptionsInfo > groupLicensing > standard | integer | The number of standard licenses associated to the subscription service
subscriptionsInfo > groupLicensing > overflow | integer | The number of overflow licenses associated to the subscription service


## Retrieve Filtered Subscription Services

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/subscriptions/search \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/subscriptions/search");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/subscriptions/search")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/subscriptions/search")

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
    }

conn.request("GET", "/api/subscriptions/search", payload)

res = conn.getresponse()
data = res.read()
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/subscriptions/search",
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
  "subscriptionsInfo": [
    {
      "subscriptionId": "11165",
      "resourceReference": "0010SGFC5SYCG6AEM3",
      "subscriptionGroup": "Monthly Magazine",
      "subscriptionGroupTag": "Monthly Subscription",
      "subscriptionGroupStatus": "Active",
      "subscriptionDescription": "Day Digital Monthly Subscription",
      "subscriptionTitle": "Monthly",
      "subscriptionType": "SubscriptionPeriod",
      "subscriptionStatus": "Active",
      "initialPricingEnabled": false,
      "trialInfo": {
        "trialEnabled": false,
        "trialUnit": "Month",
        "trialPeriod": 0,
        "discountPercentage": 0,
        "nonPaymentTrial": false
      },
      "contractInfo": {
        "contractUnit": "Minutes",
        "contractPeriod": 5,
        "autoRenewDefault": "Enabled"
      },
      "pricingInfo": [
        {
          "currency": "GBP",
          "initialPrice": 0,
          "priceIsGross": true,
          "renewalPrice": 2.5,
          "priceId": 16889,
          "taxCategory": "Standard",
          "resourceReference": "0010NWR3QDGG734QM2",
          "paymentMethod": "eWallet"
        }
      ],
      "allowedPaymentMethods": [
        "CreditCard",
        "PayPal",
        "DirectDebit"
      ],
      "customParameters": [
        {
          "parameterName": "ThirdPartyRef",
          "parameterType": "String",
          "parameterValue": "1221332525"
        }
      ],
      "images": [
        {
          "imageId": 14,
          "displayName": "TestImage",
          "fileName": "433_62c5f972-80ad-4239-97fc-428eb93916e8",
          "default": true,
          "location": "https://s3-eu-west-1.amazonaws.com/mpp-dev-one/433_62c5f972-80ad-4239-97fc-428eb93916e8"
        }
      ],
      "groupLicensing": {
        "standard": 1,
        "overflow": 0
      }
    }
  ]
}
```

This endpoint will return you a subset of your configured subscription services, based on the query parameters provided.

### HTTP Request

`GET http://uat.mppglobal.com/api/subscriptions/search`

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
serviceIds | Array[integer] | Optional | A collection of subscription service Identifiers
subscriptionGroupTagName | string | Optional | Subscription service group name



### Response Parameters

Parameter | Type | Description | 
--------- | ------- |  ----------- |
subscriptionsInfo | array[object] | Object containing all subscription services on the Client
subscriptionsInfo > subscriptionId | string | The identifier of the subscription
subscriptionsInfo > resourceReference | string | The reference of the subscription
subscriptionsInfo > subscriptionGroup | string | The subscription group the subscription belongs
subscriptionsInfo > subscriptionGroupTag | string | The subscription group tag the subscription belongs
subscriptionsInfo > subscriptionGroupStatus | string | The status of the subscription group
subscriptionsInfo > subscriptionDescription | string | A description of the subscription service
subscriptionsInfo > subscriptionTitle | string | A title of the subscription service
subscriptionsInfo > subscriptionType | string | The type of subscription service
subscriptionsInfo > subscriptionStatus | string | The status of the subscription service
subscriptionsInfo > initialPricingEnabled | boolean | An indication whether initial pricing is enabled
subscriptionsInfo > trialInfo | object | Object containing trial information
subscriptionsInfo > trialInfo > trialEnabled | boolean | An indication whether trials are enabled
subscriptionsInfo > trialInfo > trialUnit | string | Duration type (month, day, year, etc.)
subscriptionsInfo > trialInfo > trialPeriod | integer | How long the duration should be
subscriptionsInfo > trialInfo > discountPercentage | number | How much the price will be discounted
subscriptionsInfo > trialInfo > nonPaymentTrial | boolean | An indication to whether payment details are required
subscriptionsInfo > contractInfo | object | Object containing contract information
subscriptionsInfo > contractInfo > contractUnit | string | Type of contract (day, week, month, etc.)
subscriptionsInfo > contractInfo > contractPeriod | integer | Number of units the contract runs
subscriptionsInfo > contractInfo > autoRenewDefault | string | Indication whether the subscription service will renew
subscriptionsInfo > pricingInfo | array[object] | The collection of all prices configured for the subscription service
subscriptionsInfo > pricingInfo > currency | string | The currency the price is associated to
subscriptionsInfo > pricingInfo > initialPrice | number | The price that will be paid on sign-up of the subscription service
subscriptionsInfo > pricingInfo > priceIsGross | boolean | An indication as to whether the price returned is the gross or net price
subscriptionsInfo > pricingInfo > renewalPrice | number | The price that will be paid on subsequent renewal purchases
subscriptionsInfo > pricingInfo > priceId | integer | The eSuite Identifer for the price
subscriptionsInfo > pricingInfo > taxCategory | string | Tax category
subscriptionsInfo > pricingInfo > resourceReference | string | The identifier for the price that should be used on purchase calls
subscriptionsInfo > pricingInfo > paymentMethod | string | The payment method associated to the specific price
subscriptionsInfo > allowedPaymentMethods | array[string] | The collection of payment methods available on the subscription service
subscriptionsInfo > customParameters | array[object] | Custom parameters
subscriptionsInfo > customParameters > parameterName | string | Name of the custom parameter
subscriptionsInfo > customParameters > parameterType | string | An indication as to what data type the parameter should be displayed e.g. HTML, Decimal
subscriptionsInfo > customParameters > parameterValue | string | Value of the custom parameter
subscriptionsInfo > images | array[object] | The overarching object which contains all images for the subscription service
subscriptionsInfo > images > imageId | integer | The eSuite identifier for the image
subscriptionsInfo > images > displayName | string | Display name
subscriptionsInfo > images > fileName | string | The file name associated to the image
subscriptionsInfo > images > default | boolean | An indication as to whether the image is the default image for the subscription service 
subscriptionsInfo > images > location | string | The URL location the image is hosted at
subscriptionsInfo > groupLicensing | object | A breakdown of how many group licenses are associated to the subscription service
subscriptionsInfo > groupLicensing > standard | integer | The number of standard licenses associated to the subscription service
subscriptionsInfo > groupLicensing > overflow | integer | The number of overflow licenses associated to the subscription service








## Retrieve All Products

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/products \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/products/");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/products")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/products/")

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
    }

conn.request("GET", "/api/products/", payload)

res = conn.getresponse()
data = res.read()
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/products/",
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
  "products": [
    {
      "productId": 0,
      "status": "Active",
      "title": "string",
      "description": "string",
      "pricing": [
        {
          "currency": "string",
          "purchaseInfo": [
            {
              "paymentMethod": [
                {
                  "grossAmount": 0,
                  "paymentMethod": "CreditDebitCard",
                  "priceId": "string",
                  "resourceReference": "string"
                }
              ],
              "roleInfo": {
                "roleId": "string",
                "clientRef": "string",
                "title": "string"
              }
            }
          ]
        }
      ],
      "images": [
        {
          "imageId": 0,
          "displayName": "string",
          "fileName": "string",
          "default": true,
          "location": "string"
        }
      ],
      "supplier": {
        "suppliedId": 0,
        "name": "string"
      },
      "type": {
        "typeId": 0,
        "name": "string"
      },
      "customParameters": [
        {
          "parameterName": "string",
          "parameterValue": "string"
        }
      ],
      "resourceReference": "string"
    }
  ]
}

```

To return all configured products within your instance of eSuite, this endpoint should be called.

### HTTP Request

`GET http://uat.mppglobal.com/api/products`

### Response Parameters

Parameter | Type | Description | 
--------- | ------- | ----------- |
products | array[object] | List of products
products > productId | integer | Product identifier
products > status | string | Product status
products > title | string | Title
products > description | string | Description
products > pricing | array[object] | Pricing
products > pricing > currency | string | IsoCode
products > pricing > purchaseInfo | array[object] | Purchase info
products > pricing > purchaseInfo > paymentMethod | array[object] | Payment method
products > pricing > purchaseInfo > paymentMethod > grossAmount | number | Gross amount
products > pricing > purchaseInfo > paymentMethod > paymentMethod | string | Payment method
products > pricing > purchaseInfo > paymentMethod > priceId | string | Price id
products > pricing > purchaseInfo > paymentMethod > resourceReference | string | Resource Reference for the PriceId
products > pricing > purchaseInfo > roleInfo | object | Pricing role
products > pricing > purchaseInfo > roleInfo > roleId | string | Role identifier
products > pricing > purchaseInfo > roleInfo > clientRef | string | Client reference
products > pricing > purchaseInfo > roleInfo > title | string | Title
products > images | array[object] | Images of the product
products > images > imageId | integer | Image identifier
products > images > displayName | string | Display name
products > images > fileName | string | File name
products > images > default | boolean | Specify if image is default
products > images > location | string | Path to the image
products > supplier | object | Suplier details
products > supplier > suppliedId | integer | Suplier identifier
products > supplier > name | string | Name
products > type | object | Product type
products > type > typeId | integer | Type id
products > type > name | string | Type name
products > customParameters | array[object] | Custom parameters
products > customParameters > parameterName | string | Name of the custom parameter
products > customParameters > parameterValue | string | Value of the custom parameter
products > resourceReference | string | Resource Reference for the ProductId







## Retrieve Filtered Products

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/products/search \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/products/search");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/products/search")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/products/search")

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
    'x-tokenid': "1001",
    'x-clientPassword': "Str0ngP@ssword",
    'x-version': "9.0.0"
    }

conn.request("GET", "/api/products/search", payload)

res = conn.getresponse()
data = res.read()
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://uat.mppglobal.com/api/products/search",
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
  "products": [
    {
      "productId": 0,
      "status": "Active",
      "title": "string",
      "description": "string",
      "pricing": [
        {
          "currency": "string",
          "purchaseInfo": [
            {
              "paymentMethod": [
                {
                  "grossAmount": 0,
                  "paymentMethod": "CreditDebitCard",
                  "priceId": "string",
                  "resourceReference": "string"
                }
              ],
              "roleInfo": {
                "roleId": "string",
                "clientRef": "string",
                "title": "string"
              }
            }
          ]
        }
      ],
      "images": [
        {
          "imageId": 0,
          "displayName": "string",
          "fileName": "string",
          "default": true,
          "location": "string"
        }
      ],
      "supplier": {
        "suppliedId": 0,
        "name": "string"
      },
      "type": {
        "typeId": 0,
        "name": "string"
      },
      "customParameters": [
        {
          "parameterName": "string",
          "parameterValue": "string"
        }
      ],
      "resourceReference": "string"
    }
  ]
}

```

To return only a subset of your product catalogoue, this endpoint should be called with the appropriate query string parameters.

### HTTP Request

`GET http://uat.mppglobal.com/api/products/search`

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
productIds | array[integer] | Optional | A collection of product Identifiers
currency | string | Optional | The currency prices should be returned


### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
products | array[object] | List of products
products > productId | integer | Product identifier
products > status | string | Product status
products > title | string | Title
products > description | string | Description
products > pricing | array[object] | Pricing
products > pricing > currency | string | IsoCode
products > pricing > purchaseInfo | array[object] | Purchase info
products > pricing > purchaseInfo > paymentMethod | array[object] | Payment method
products > pricing > purchaseInfo > paymentMethod > grossAmount | number | Gross amount
products > pricing > purchaseInfo > paymentMethod > paymentMethod | string | Payment method
products > pricing > purchaseInfo > paymentMethod > priceId | string | Price id
products > pricing > purchaseInfo > paymentMethod > resourceReference | string | Resource Reference for the PriceId
products > pricing > purchaseInfo > roleInfo | object | Pricing role
products > pricing > purchaseInfo > roleInfo > roleId | string | Role identifier
products > pricing > purchaseInfo > roleInfo > clientRef | string | Client reference
products > pricing > purchaseInfo > roleInfo > title | string | Title
products > images | array[object] | Images of the product
products > images > imageId | integer | Image identifier
products > images > displayName | string | Display name
products > images > fileName | string | File name
products > images > default | boolean | Specify if image is default
products > images > location | string | Path to the image
products > supplier | object | Suplier details
products > supplier > suppliedId | integer | Suplier identifier
products > supplier > name | string | Name
products > type | object | Product type
products > type > typeId | integer | Type id
products > type > name | string | Type name
products > customParameters | array[object] | Custom parameters
products > customParameters > parameterName | string | Name of the custom parameter
products > customParameters > parameterValue | string | Value of the custom parameter
products > resourceReference | string | Resource Reference for the ProductId





