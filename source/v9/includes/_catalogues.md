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
    'x-version': '9.0.0'
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

 |  | 
--------- | ------- |  
`subscriptionsInfo` <br />Object containing all subscription services on the Client| <span class="array">array[object]</span> | 
`subscriptionsInfo \ subscriptionId` <br />The identifier of the subscription| <span class="string">string</span> | 
`subscriptionsInfo \ resourceReference` <br />The reference of the subscription| <span class="string">string</span> | 
`subscriptionsInfo \ subscriptionGroup` <br />The subscription group the subscription belongs| <span class="string">string</span> | 
`subscriptionsInfo \ subscriptionGroupTag` <br />The subscription group tag the subscription belongs| <span class="string">string</span> | 
`subscriptionsInfo \ subscriptionGroupStatus` <br />The status of the subscription group| <span class="string">string</span> | 
`subscriptionsInfo \ subscriptionDescription` <br />A description of the subscription service| <span class="string">string</span> | 
`subscriptionsInfo \ subscriptionTitle` <br />A title of the subscription service| <span class="string">string</span> | 
`subscriptionsInfo \ subscriptionType` <br />The type of subscription service| <span class="string">string</span> | 
`subscriptionsInfo \ subscriptionStatus` <br />The status of the subscription service| <span class="string">string</span> | 
`subscriptionsInfo \ initialPricingEnabled` <br />An indication whether initial pricing is enabled| <span class="bool">bool</span> | 
`subscriptionsInfo \ trialInfo` <br />Object containing trial information| <span class="object">object</span> | 
`trialInfo \ trialEnabled` <br />An indication whether trials are enabled| <span class="bool">bool</span> | 
`trialInfo \ trialUnit` <br />Duration type (month, day, year, etc.)| <span class="string">string</span> | 
`trialInfo \ trialPeriod` <br />How long the duration should be| <span class="integer">integer</span> | 
`trialInfo \ discountPercentage` <br />How much the price will be discounted| <span style="font-weight:bold;color:#666;">number</span> | 
`trialInfo \ nonPaymentTrial` <br />An indication to whether payment details are required| <span class="bool">bool</span> | 
`subscriptionsInfo \ contractInfo` <br />Object containing contract information| <span class="object">object</span> | 
`contractInfo \ contractUnit` <br />Type of contract (day, week, month, etc.)| <span class="string">string</span> | 
`contractInfo \ contractPeriod` <br />Number of units the contract runs| <span class="integer">integer</span> | 
`contractInfo \ autoRenewDefault` <br />Indication whether the subscription service will renew| <span class="string">string</span> | 
`subscriptionsInfo \ pricingInfo` <br />The collection of all prices configured for the subscription service| <span class="array">array[object]</span> | 
`pricingInfo \ currency` <br />The currency the price is associated to| <span class="string">string</span> | 
`pricingInfo \ initialPrice` <br />The price that will be paid on sign-up of the subscription service| <span style="font-weight:bold;color:#666;">number</span> | 
`pricingInfo \ priceIsGross` <br />An indication as to whether the price returned is the gross or net price| <span class="bool">bool</span> | 
`pricingInfo \ renewalPrice` <br />The price that will be paid on subsequent renewal purchases| <span style="font-weight:bold;color:#666;">number</span> | 
`pricingInfo \ priceId` <br />The eSuite Identifer for the price| <span class="integer">integer</span> | 
`pricingInfo \ taxCategory` <br />Tax category| <span class="string">string</span> | 
`pricingInfo \ resourceReference` <br />The identifier for the price that should be used on purchase calls| <span class="string">string</span> | 
`pricingInfo \ paymentMethod` <br />The payment method associated to the specific price| <span class="string">string</span> | 
`subscriptionsInfo \ allowedPaymentMethods` <br />The collection of payment methods available on the subscription service| <span class="array">array[string]</span> | 
`customParameters` <br />Custom parameters| <span class="array">array[object]</span> | 
`customParameters \ parameterName` <br />Name of the custom parameter| <span class="string">string</span> | 
`customParameters \ parameterType` <br />An indication as to what data type the parameter should be displayed e.g. HTML, Decimal| <span class="string">string</span> | 
`customParameters \ parameterValue` <br />Value of the custom parameter| <span class="string">string</span> | 
`subscriptionsInfo \ images` <br />The overarching object which contains all images for the subscription service| <span class="array">array[object]</span> | 
`images \ imageId` <br />The eSuite identifier for the image| <span class="integer">integer</span> | 
`images \ displayName` <br />Display name| <span class="string">string</span> | 
`images \ fileName` <br />The file name associated to the image| <span class="string">string</span> | 
`images \ default` <br />An indication as to whether the image is the default image for the subscription service| <span class="bool">bool</span> |  
`images \ location` <br />The URL location the image is hosted at| <span class="string">string</span> | 
`subscriptionsInfo \ groupLicensing` <br />A breakdown of how many group licenses are associated to the subscription service| <span class="object">object</span> | 
`groupLicensing \ standard` <br />The number of standard licenses associated to the subscription service| <span class="integer">integer</span> | 
`groupLicensing \ overflow` <br />The number of overflow licenses associated to the subscription service| <span class="integer">integer</span> | 


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
    'x-version': '9.0.0'
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

 |  |  | 
--------- | ------- | ------- | 
`serviceIds` <br />A collection of subscription service Identifiers| <span class="array">array[integer]</span> |  | 
`subscriptionGroupTagName` <br />Subscription service group name| <span class="string">string</span> |  | 


### Response Parameters

 |  | 
--------- | ------- |  
`subscriptionsInfo` <br />Object containing all subscription services on the Client| <span class="array">array[object]</span> | 
`subscriptionsInfo` > subscriptionId <br />The identifier of the subscription| <span class="string">string</span> | 
`subscriptionsInfo` > resourceReference <br />The reference of the subscription| <span class="string">string</span> | 
`subscriptionsInfo` > subscriptionGroup <br />The subscription group the subscription belongs| <span class="string">string</span> | 
`subscriptionsInfo` > subscriptionGroupTag <br />The subscription group tag the subscription belongs| <span class="string">string</span> | 
`subscriptionsInfo` > subscriptionGroupStatus <br />The status of the subscription group| <span class="string">string</span> | 
`subscriptionsInfo` > subscriptionDescription <br />A description of the subscription service| <span class="string">string</span> | 
`subscriptionsInfo` > subscriptionTitle <br />A title of the subscription service| <span class="string">string</span> | 
`subscriptionsInfo` > subscriptionType <br />The type of subscription service| <span class="string">string</span> | 
`subscriptionsInfo` > subscriptionStatus <br />The status of the subscription service| <span class="string">string</span> | 
`subscriptionsInfo` > initialPricingEnabled <br />An indication whether initial pricing is enabled| <span class="bool">bool</span> | 
`subscriptionsInfo` > trialInfo <br />Object containing trial information| <span class="object">object</span> | 
`trialInfo` > trialEnabled <br />An indication whether trials are enabled| <span class="bool">bool</span> | 
`trialInfo` > trialUnit <br />Duration type (month, day, year, etc.)| <span class="string">string</span> | 
`trialInfo` > trialPeriod <br />How long the duration should be| <span class="integer">integer</span> | 
`trialInfo` > discountPercentage <br />How much the price will be discounted| <span style="font-weight:bold;color:#666;">number</span> | 
`trialInfo` > nonPaymentTrial <br />An indication to whether payment details are required| <span class="bool">bool</span> | 
`subscriptionsInfo` > contractInfo <br />Object containing contract information| <span class="object">object</span> | 
`contractInfo` > contractUnit <br />Type of contract (day, week, month, etc.)| <span class="string">string</span> | 
`contractInfo` > contractPeriod <br />Number of units the contract runs| <span class="integer">integer</span> | 
`contractInfo` > autoRenewDefault <br />Indication whether the subscription service will renew| <span class="string">string</span> | 
`subscriptionsInfo` > pricingInfo <br />The collection of all prices configured for the subscription service| <span class="array">array[object]</span> | 
`pricingInfo` > currency <br />The currency the price is associated to| <span class="string">string</span> | 
`pricingInfo` > initialPrice <br />The price that will be paid on sign-up of the subscription service| <span style="font-weight:bold;color:#666;">number</span> | 
`pricingInfo` > priceIsGross <br />An indication as to whether the price returned is the gross or net price| <span class="bool">bool</span> | 
`pricingInfo` > renewalPrice <br />The price that will be paid on subsequent renewal purchases| <span style="font-weight:bold;color:#666;">number</span> | 
`pricingInfo` > priceId <br />The eSuite Identifer for the price| <span class="integer">integer</span> | 
`pricingInfo` > taxCategory <br />Tax category| <span class="string">string</span> | 
`pricingInfo` > resourceReference <br />The identifier for the price that should be used on purchase calls| <span class="string">string</span> | 
`pricingInfo` > paymentMethod <br />The payment method associated to the specific price| <span class="string">string</span> | 
`subscriptionsInfo` > allowedPaymentMethods <br />The collection of payment methods available on the subscription service| <span class="array">array[string]</span> | 
`subscriptionsInfo` > customParameters <br />Custom parameters| <span class="array">array[object]</span> | 
`customParameters` > parameterName <br />Name of the custom parameter| <span class="string">string</span> | 
`customParameters` > parameterType <br />An indication as to what data type the parameter should be displayed e.g. HTML, Decimal| <span class="string">string</span> | 
`customParameters` > parameterValue <br />Value of the custom parameter| <span class="string">string</span> | 
`subscriptionsInfo` > images <br />The overarching object which contains all images for the subscription service| <span class="array">array[object]</span> | 
`images` > imageId <br />The eSuite identifier for the image| <span class="integer">integer</span> | 
`images` > displayName <br />Display name| <span class="string">string</span> | 
`images` > fileName <br />The file name associated to the image| <span class="string">string</span> | 
`images` > default <br />An indication as to whether the image is the default image for the subscription service| <span class="bool">bool</span> |  
`images` > location <br />The URL location the image is hosted at| <span class="string">string</span> | 
`subscriptionsInfo` > groupLicensing <br />A breakdown of how many group licenses are associated to the subscription service| <span class="object">object</span> | 
`groupLicensing` > standard <br />The number of standard licenses associated to the subscription service| <span class="integer">integer</span> | 
`groupLicensing` > overflow <br />The number of overflow licenses associated to the subscription service| <span class="integer">integer</span> | 








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
    'x-version': '9.0.0'
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

 |  | 
--------- | ------- | 
`products` <br />List of products| <span class="array">array[object]</span> | 
`products \ productId` <br />Product identifier| <span class="integer">integer</span> | 
`products \ status` <br />Product status| <span class="string">string</span> | 
`products \ title` <br />Title| <span class="string">string</span> | 
`products \ description` <br />Description| <span class="string">string</span> | 
`products \ pricing` <br />Pricing| <span class="array">array[object]</span> | 
`pricing \ currency` <br />IsoCode| <span class="string">string</span> | 
`pricing \ purchaseInfo` <br />Purchase info| <span class="array">array[object]</span> | 
`purchaseInfo \ paymentMethod` <br />Payment method| <span class="array">array[object]</span> | 
`paymentMethod \ grossAmount` <br />Gross amount| <span style="font-weight:bold;color:#666;">number</span> | 
`paymentMethod \ paymentMethod` <br />Payment method| <span class="string">string</span> | 
`paymentMethod \ priceId` <br />Price id| <span class="string">string</span> | 
`paymentMethod \ resourceReference` <br />Resource Reference for the PriceId| <span class="string">string</span> | 
`purchaseInfo \ roleInfo` <br />Pricing role| <span class="object">object</span> | 
`roleInfo \ roleId` <br />Role identifier| <span class="string">string</span> | 
`roleInfo \ clientRef` <br />Client reference| <span class="string">string</span> | 
`roleInfo \ title` <br />Title| <span class="string">string</span> | 
`products \ images` <br />Images of the product| <span class="array">array[object]</span> | 
`images \ imageId` <br />Image identifier| <span class="integer">integer</span> | 
`images \ displayName` <br />Display name| <span class="string">string</span> | 
`images \ fileName` <br />File name| <span class="string">string</span> | 
`images \ default` <br />Specify if image is default| <span class="bool">bool</span> | 
`images \ location` <br />Path to the image| <span class="string">string</span> | 
`products \ supplier` <br />Supplier details| <span class="object">object</span> | 
`supplier \ suppliedId` <br />Supplier identifier| <span class="integer">integer</span> | 
`supplier \ name` <br />Name| <span class="string">string</span> | 
`products \ type` <br />Product type| <span class="object">object</span> | 
`type \ typeId` <br />Type id| <span class="integer">integer</span> | 
`type \ name` <br />Type name| <span class="string">string</span> | 
`products \ customParameters` <br />Custom parameters| <span class="array">array[object]</span> | 
`customParameters \ parameterName` <br />Name of the custom parameter| <span class="string">string</span> | 
`customParameters \ parameterValue` <br />Value of the custom parameter| <span class="string">string</span> | 
`products \ resourceReference` <br />Resource Reference for the ProductId| <span class="string">string</span> | 







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
    'x-version': '9.0.0'
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

 |  |  | 
--------- | ------- | ------- | 
`productIds` <br />A collection of product Identifiers| <span class="array">array[integer]</span> |  | 
`currency` <br />The currency prices should be returned| <span class="string">string</span> |  | 


### Response Parameters

 |  |  | 
--------- | ------- | ------- | 
`products` <br />List of products| <span class="array">array[object]</span> | 
`products \ productId` <br />Product identifier| <span class="integer">integer</span> | 
`products \ status` <br />Product status| <span class="string">string</span> | 
`products \ title` <br />Title| <span class="string">string</span> | 
`products \ description` <br />Description| <span class="string">string</span> | 
`products \ pricing` <br />Pricing| <span class="array">array[object]</span> | 
`pricing \ currency` <br />IsoCode| <span class="string">string</span> | 
`pricing \ purchaseInfo` <br />Purchase info| <span class="array">array[object]</span> | 
`purchaseInfo \ paymentMethod` <br />Payment method| <span class="array">array[object]</span> | 
`paymentMethod \ grossAmount` <br />Gross amount| <span style="font-weight:bold;color:#666;">number</span> | 
`paymentMethod \ paymentMethod` <br />Payment method| <span class="string">string</span> | 
`paymentMethod \ priceId` <br />Price id| <span class="string">string</span> | 
`paymentMethod \ resourceReference` <br />Resource Reference for the PriceId| <span class="string">string</span> | 
`products \ pricing` > purchaseInfo > roleInfo <br />Pricing role| <span class="object">object</span> | 
`roleInfo \ roleId` <br />Role identifier| <span class="string">string</span> | 
`roleInfo \ clientRef` <br />Client reference| <span class="string">string</span> | 
`roleInfo \ title` <br />Title| <span class="string">string</span> | 
`products \ images` <br />Images of the product| <span class="array">array[object]</span> | 
`images \ imageId` <br />Image identifier| <span class="integer">integer</span> | 
`images \ displayName` <br />Display name| <span class="string">string</span> | 
`images \ fileName` <br />File name| <span class="string">string</span> | 
`images \ default` <br />Specify if image is default| <span class="bool">bool</span> | 
`images \ location` <br />Path to the image| <span class="string">string</span> | 
`products \ supplier` <br />Supplier details| <span class="object">object</span> | 
`suppliedId` <br />Supplier identifier| <span class="integer">integer</span> | 
`supplier \ name` <br />Name| <span class="string">string</span> | 
`products \ type` <br />Product type| <span class="object">object</span> | 
`type \ typeId` <br />Type id| <span class="integer">integer</span> | 
`type \ name` <br />Type name| <span class="string">string</span> | 
`products \ customParameters` <br />Custom parameters| <span class="array">array[object]</span> | 
`customParameters \ parameterName` <br />Name of the custom parameter| <span class="string">string</span> | 
`customParameters \ parameterValue` <br />Value of the custom parameter| <span class="string">string</span> | 
`products \ resourceReference` <br />Resource Reference for the ProductId| <span class="string">string</span> | 





