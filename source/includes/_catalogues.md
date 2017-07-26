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
    'x-clientid' : '1001',
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

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/subscriptions</span>
</div>

### Response Parameters

Parameter | Type | Description | 
--------- | ------- |  ----------- |
`subscriptionsInfo` | array[object] | Object containing all subscription services on the Client
`subscriptionsInfo` > `subscriptionId` | string | The identifier of the subscription
`subscriptionsInfo` > `resourceReference` | string | The reference of the subscription
`subscriptionsInfo` > `subscriptionGroup` | string | The subscription group the subscription belongs
`subscriptionsInfo` > `subscriptionGroupTag` | string | The subscription group tag the subscription belongs
`subscriptionsInfo` > `subscriptionGroupStatus` | string | The status of the subscription group
`subscriptionsInfo` > `subscriptionDescription` | string | A description of the subscription service
`subscriptionsInfo` > `subscriptionTitle` | string | A title of the subscription service
`subscriptionsInfo` > `subscriptionType` | string | The type of subscription service
`subscriptionsInfo` > `subscriptionStatus` | string | The status of the subscription service
`subscriptionsInfo` > `initialPricingEnabled` | boolean | An indication whether initial pricing is enabled
`subscriptionsInfo` > `trialInfo` | object | Object containing trial information
`trialInfo` > `trialEnabled` | boolean | An indication whether trials are enabled
`trialInfo` > `trialUnit` | string | Duration type (month, day, year, etc.)
`trialInfo` > `trialPeriod` | integer | How long the duration should be
`trialInfo` > `discountPercentage` | number | How much the price will be discounted
`trialInfo` > `nonPaymentTrial` | boolean | An indication to whether payment details are required
`subscriptionsInfo` > `contractInfo` | object | Object containing contract information
`contractInfo` > `contractUnit` | string | Type of contract (day, week, month, etc.)
`contractInfo` > `contractPeriod` | integer | Number of units the contract runs
`contractInfo` > `autoRenewDefault` | string | Indication whether the subscription service will renew
`subscriptionsInfo` > `pricingInfo` | array[object] | The collection of all prices configured for the subscription service
`pricingInfo` > `currency` | string | The currency the price is associated to
`pricingInfo` > `initialPrice` | number | The price that will be paid on sign-up of the subscription service
`pricingInfo` > `priceIsGross` | boolean | An indication as to whether the price returned is the gross or net price
`pricingInfo` > `renewalPrice` | number | The price that will be paid on subsequent renewal purchases
`pricingInfo` > `priceId` | integer | The eSuite Identifer for the price
`pricingInfo` > `taxCategory` | string | Tax category
`pricingInfo` > `resourceReference` | string | The identifier for the price that should be used on purchase calls
`pricingInfo` > `paymentMethod` | string | The payment method associated to the specific price
`subscriptionsInfo` > `allowedPaymentMethods` | array[string] | The collection of payment methods available on the subscription service
`customParameters` | array[object] | Custom parameters
`customParameters` > `parameterName` | string | Name of the custom parameter
`customParameters` > `parameterType` | string | An indication as to what data type the parameter should be displayed e.g. HTML, Decimal
`customParameters` > `parameterValue` | string | Value of the custom parameter
`subscriptionsInfo` > `images` | array[object] | The overarching object which contains all images for the subscription service
`images` > `imageId` | integer | The eSuite identifier for the image
`images` > `displayName` | string | Display name
`images` > `fileName` | string | The file name associated to the image
`images` > `default` | boolean | An indication as to whether the image is the default image for the subscription service 
`images` > `location` | string | The URL location the image is hosted at
`subscriptionsInfo` > `groupLicensing` | object | A breakdown of how many group licenses are associated to the subscription service
`groupLicensing` > `standard` | integer | The number of standard licenses associated to the subscription service
`groupLicensing` > `overflow` | integer | The number of overflow licenses associated to the subscription service


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
    'x-clientid' : '1001',
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

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/subscriptions/search</span>
</div>

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
serviceIds | Array[integer] | Optional | A collection of subscription service Identifiers
subscriptionGroupTagName | string | Optional | Subscription service group name



### Response Parameters

Parameter | Type | Description | 
--------- | ------- |  ----------- |
`subscriptionsInfo` | array[object] | Object containing all subscription services on the Client
`subscriptionsInfo` > subscriptionId | string | The identifier of the subscription
`subscriptionsInfo` > resourceReference | string | The reference of the subscription
`subscriptionsInfo` > subscriptionGroup | string | The subscription group the subscription belongs
`subscriptionsInfo` > subscriptionGroupTag | string | The subscription group tag the subscription belongs
`subscriptionsInfo` > subscriptionGroupStatus | string | The status of the subscription group
`subscriptionsInfo` > subscriptionDescription | string | A description of the subscription service
`subscriptionsInfo` > subscriptionTitle | string | A title of the subscription service
`subscriptionsInfo` > subscriptionType | string | The type of subscription service
`subscriptionsInfo` > subscriptionStatus | string | The status of the subscription service
`subscriptionsInfo` > initialPricingEnabled | boolean | An indication whether initial pricing is enabled
`subscriptionsInfo` > trialInfo | object | Object containing trial information
`trialInfo` > trialEnabled | boolean | An indication whether trials are enabled
`trialInfo` > trialUnit | string | Duration type (month, day, year, etc.)
`trialInfo` > trialPeriod | integer | How long the duration should be
`trialInfo` > discountPercentage | number | How much the price will be discounted
`trialInfo` > nonPaymentTrial | boolean | An indication to whether payment details are required
`subscriptionsInfo` > contractInfo | object | Object containing contract information
`contractInfo` > contractUnit | string | Type of contract (day, week, month, etc.)
`contractInfo` > contractPeriod | integer | Number of units the contract runs
`contractInfo` > autoRenewDefault | string | Indication whether the subscription service will renew
`subscriptionsInfo` > pricingInfo | array[object] | The collection of all prices configured for the subscription service
`pricingInfo` > currency | string | The currency the price is associated to
`pricingInfo` > initialPrice | number | The price that will be paid on sign-up of the subscription service
`pricingInfo` > priceIsGross | boolean | An indication as to whether the price returned is the gross or net price
`pricingInfo` > renewalPrice | number | The price that will be paid on subsequent renewal purchases
`pricingInfo` > priceId | integer | The eSuite Identifer for the price
`pricingInfo` > taxCategory | string | Tax category
`pricingInfo` > resourceReference | string | The identifier for the price that should be used on purchase calls
`pricingInfo` > paymentMethod | string | The payment method associated to the specific price
`subscriptionsInfo` > allowedPaymentMethods | array[string] | The collection of payment methods available on the subscription service
`subscriptionsInfo` > customParameters | array[object] | Custom parameters
`customParameters` > parameterName | string | Name of the custom parameter
`customParameters` > parameterType | string | An indication as to what data type the parameter should be displayed e.g. HTML, Decimal
`customParameters` > parameterValue | string | Value of the custom parameter
`subscriptionsInfo` > images | array[object] | The overarching object which contains all images for the subscription service
`images` > imageId | integer | The eSuite identifier for the image
`images` > displayName | string | Display name
`images` > fileName | string | The file name associated to the image
`images` > default | boolean | An indication as to whether the image is the default image for the subscription service 
`images` > location | string | The URL location the image is hosted at
`subscriptionsInfo` > groupLicensing | object | A breakdown of how many group licenses are associated to the subscription service
`groupLicensing` > standard | integer | The number of standard licenses associated to the subscription service
`groupLicensing` > overflow | integer | The number of overflow licenses associated to the subscription service








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
    'x-clientid' : '1001',
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

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/products</span>
</div>

### Response Parameters

Parameter | Type | Description | 
--------- | ------- | ----------- |
`products` | array[object] | List of products
`products` > `productId` | integer | Product identifier
`products` > `status` | string | Product status
`products` > `title` | string | Title
`products` > `description` | string | Description
`products` > `pricing` | array[object] | Pricing
`pricing` > `currency` | string | IsoCode
`pricing` > `purchaseInfo` | array[object] | Purchase info
`purchaseInfo` > `paymentMethod` | array[object] | Payment method
`paymentMethod` > `grossAmount` | number | Gross amount
`paymentMethod` > `paymentMethod` | string | Payment method
`paymentMethod` > `priceId` | string | Price id
`paymentMethod` > `resourceReference` | string | Resource Reference for the PriceId
`purchaseInfo` > `roleInfo` | object | Pricing role
`roleInfo` > `roleId` | string | Role identifier
`roleInfo` > `clientRef` | string | Client reference
`roleInfo` > `title` | string | Title
`products` > `images` | array[object] | Images of the product
`images` > `imageId` | integer | Image identifier
`images` > `displayName` | string | Display name
`images` > `fileName` | string | File name
`images` > `default` | boolean | Specify if image is default
`images` > `location` | string | Path to the image
`products` > `supplier` | object | Suplier details
`supplier` > `suppliedId` | integer | Suplier identifier
`supplier` > `name` | string | Name
`products` > `type` | object | Product type
`type` > `typeId` | integer | Type id
`type` > `name` | string | Type name
`products` > `customParameters` | array[object] | Custom parameters
`customParameters` > `parameterName` | string | Name of the custom parameter
`customParameters` > `parameterValue` | string | Value of the custom parameter
`products` > `resourceReference` | string | Resource Reference for the ProductId







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
    'x-clientid' : '1001',
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

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/products/search</span>
</div>

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
productIds | array[integer] | Optional | A collection of product Identifiers
currency | string | Optional | The currency prices should be returned


### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`products` | array[object] | List of products
`products` > `productId` | integer | Product identifier
`products` > `status` | string | Product status
`products` > `title` | string | Title
`products` > `description` | string | Description
`products` > `pricing` | array[object] | Pricing
`pricing` > `currency` | string | IsoCode
`pricing` > `purchaseInfo` | array[object] | Purchase info
`purchaseInfo` > `paymentMethod` | array[object] | Payment method
`paymentMethod` > `grossAmount` | number | Gross amount
`paymentMethod` > `paymentMethod` | string | Payment method
`paymentMethod` > `priceId` | string | Price id
`paymentMethod` > `resourceReference` | string | Resource Reference for the PriceId
`products` > `pricing` > purchaseInfo > roleInfo | object | Pricing role
`roleInfo` > `roleId` | string | Role identifier
`roleInfo` > `clientRef` | string | Client reference
`roleInfo` > `title` | string | Title
`products` > `images` | array[object] | Images of the product
`images` > `imageId` | integer | Image identifier
`images` > `displayName` | string | Display name
`images` > `fileName` | string | File name
`images` > `default` | boolean | Specify if image is default
`images` > `location` | string | Path to the image
`products` > `supplier` | object | Suplier details
`suppliedId` | integer | Suplier identifier
`supplier` > `name` | string | Name
`products` > `type` | object | Product type
`type` > `typeId` | integer | Type id
`type` > `name` | string | Type name
`products` > `customParameters` | array[object] | Custom parameters
`customParameters` > `parameterName` | string | Name of the custom parameter
`customParameters` > `parameterValue` | string | Value of the custom parameter
`products` > `resourceReference` | string | Resource Reference for the ProductId





