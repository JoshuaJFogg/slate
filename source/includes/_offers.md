# Offers

## Retrieve all Offers

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/offers \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/offers");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/offers")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/offers")

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

conn.request("GET", "/api/offers", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "totalNumberOfRecords": 0,
  "pageNumber": 0,
  "resultsPerPage": 0,
  "items": [
    {
      "offerReference": "string",
      "startDate": "2017-07-27T16:22:18.163Z",
      "expiryDate": "2017-07-27T16:22:18.163Z",
      "name": "string",
      "description": "string",
      "usageType": "UniqueToUserUseOnce",
      "applicationData": {
        "name": "string",
        "message": "string",
        "message2": "string"
      },
      "addCredits": {
        "amount": 0,
        "currency": "string",
        "paymentDetailsRequired": true
      },
      "lowStart": {
        "percentage": 0,
        "numberOfPeriods": 0,
        "lockInPeriods": 0,
        "closeSubOnExpiry": true,
        "serviceIds": [
          0
        ],
        "paymentDetailsRequired": true
      },
      "percentageDiscount": {
        "percentage": 0,
        "paymentDetailsRequired": true
      },
      "freePeriod": {
        "numberOfPeriods": 0,
        "serviceIds": [
          0
        ],
        "paymentDetailsRequired": true
      },
      "groupDiscount": {
        "activationCodeActivated": true,
        "metaData": {
          "qualifyingItemCount": 0,
          "freeItemCountOrDiscountAmount": 0,
          "productIds": [
            0
          ],
          "configurationType": "string",
          "productSource": "string",
          "customParameters": {}
        }
      },
      "fixedPriceDiscount": {
        "discountAmounts": [
          {
            "value": 0,
            "currency": "string"
          }
        ],
        "paymentDetailsRequired": true,
        "subscriptionSettings": {
          "enabled": true,
          "numberOfPeriods": 0,
          "lockInPeriods": 0,
          "closeSubOnExpiry": true,
          "serviceIds": [
            0
          ]
        },
        "productSettings": {
          "enabled": true,
          "productIds": [
            0
          ]
        },
        "miscellaneousChargeSettings": {
          "enabled": true
        }
      }
    }
  ]
}
```

Calling this endpoint, will return all configured offers against your instance of eSuite. This endpoint allow you to return a specific number of offers per page and the page number you would like to view. If no additional filters are provided a default 50 page limit will be returned.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/offers</span>
</div>

### GET Parameters

 |  |  | 
--------- | ------- | ------- | 
`productReference` <br />Providing this parameter will return offers specific to this product| <span class="string">string</span> |  | 
`status` <br />Indicates whether to return `Active` or `Disabled` offers| <span class="string">string</span> |  | 
`pageNumber` <br />Which page should be returned| <span class="integer">integer</span> |  | 
`rowsPerPage` <br />The number of results to return per page| <span class="integer">integer</span> |  | 

### Response Parameters

 |  |  
--------- | ------- | 
`totalNumberOfRecords` <br />The total number of offers found as a result of the request| <span class="string">string</span> | 
`pageNumber` <br />The page number being displayed| <span class="string">string</span> | 
`resultsPerPage` <br />The number of records being displayed| <span class="integer">integer</span> | 
`items` <br />Collection of all offers| <span class="array">array[objects]</span> | 
`items` > `offerReference` <br />Unique identifier for the offer| <span class="string">string</span> | 
`items` > `startDate` <br />The date at which the offer becomes active| <span class="string">string</span> | 
`items` > `expiryDate` <br />The date at which the offer becomes inactive| <span class="string">string</span> | 
`items` > `name` <br />The name associated to the offer| <span class="string">string</span> | 
`items` > `description` <br />Additional details against the offer| <span class="string">string</span> | 
`items` > `usageType` <br />The type of usage applicable for the offer| <span class="string">string</span> | 
`items` > `applicationData` <br />Alternative data to display to an end-user| <span class="array">array[objects]</span> | 
`applicationData` > `name` <br />End-user name| <span class="string">string</span> |  
`applicationData` > `message` <br />Public facing message| <span class="string">string</span> | 
`applicationData` > `message2` <br />Additional public facing message| <span class="string">string</span> | 
`items` > `addCredits` <br />Information relating to an AddCredits offer type| <span class="array">array[objects]</span> | 
`addCredits` > `amount` <br />Amount of credit the account should receive| <span style="font-weight:bold;color:#666;">decimal</span> | 
`addCredits` > `currency` <br />Currency the credit should be added in| <span class="string">string</span> | 
`addCredits` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`items` > `lowStart` <br />Information relating to an LowStart offer type| <span class="array">array[objects]</span> | 
`lowStart` > `percentage` <br />The percentage discount the account should receive| <span style="font-weight:bold;color:#666;">decimal</span> |  
`lowStart` > `numberOfPeriods` <br />How long the discount should take place| <span class="integer">integer</span> | 
`lowStart` > `lockInPeriods` <br />Number of periods before the account can cancel their subscription| <span class="integer">integer</span> | 
`lowStart` > `closeSubOnExpiry` <br />Indication whether the subscription will expire at the same time as the offer| <span class="bool">bool</span> | 
`lowStart` > `serviceIds` <br />Collection of applicable services for the offer| <span class="array">array[integer]</span> | 
`lowStart` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`items` > `percentageDiscount` <br />Information relating to an PercentageDiscount offer type| <span class="array">array[objects]</span> | 
`percentageDiscount` > `percentage` <br />The percentage discount that will be received| <span style="font-weight:bold;color:#666;">decimal</span> | 
`percentageDiscount` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`items` > `freePeriod` <br />Information relating to an freePeriod offer type| <span class="array">array[objects]</span> | 
`freePeriod` > `numberOfPeriods` <br />How long the discount should take place| <span class="integer">integer</span> | 
`freePeriod` > `serviceIds` <br />Collection of applicable services for the offer| <span class="array">array[integer]</span> | 
`freePeriod` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`items` > `groupDiscount` <br />Information relating to an GroupDiscount offer type| <span class="array">array[objects]</span> | 
`groupDiscount` > `metaData` <br />Metadata of the group discount| <span class="object">object</span> | 
`metaData` > `qualifyingItemCount` <br />The number of items that must be purchased to be applicable for the offer| <span class="integer">integer</span> | 
`metaData` > `freeItemCountOrDiscountAmount` <br />The discount amount or the number of free items| <span class="integer">integer</span> | 
`metaData` > `productIds` <br />List of Products that can have the offer redeemed| <span class="array">array[integer]</span> | 
`groupDiscount` > `productSource` <br />Product source| <span class="string">string</span> | 
`groupDiscount` > `customParameters` <br />Dictionary of custom parameters applicable to the discount| <span class="dictionary">dictionary</span> | 
`items` > `fixedPriceDiscount` <br />Information relating to an FixedPriceDiscount offer type| <span class="array">array[objects]</span> | 
`fixedPriceDiscount` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`fixedPriceDiscount` > `discountAmounts` <br />Specific currency configuration| <span class="array">array[objects]</span> | 
`discountAmounts` > `value` <br />Amount to be discounted| <span style="font-weight:bold;color:#666;">decimal</span> | 
`discountAmounts` > `currency` <br />The associated currency| <span class="string">string</span> | 
`fixedPriceDiscount` > `subscriptionSettings` <br />Settings associated to the service aspect of a fixed price discount| <span class="array">array[objects]</span> | 
`subscriptionSettings` > `enabled` <br />Indication as to whether the offer can be used on a subscription purchase| <span class="bool">bool</span> | 
`subscriptionSettings` > `numberOfPeriods` <br />Number of renewing periods the offer is applicable for| <span class="integer">integer</span> | 
`subscriptionSettings` > `lockInPeriods` <br />The number of periods an account would be locked in if the offer was redeemed| <span class="integer">integer</span> | 
`subscriptionSettings` > `closeSubOnExpiry` <br />Indication whether the subscription will expire at the same time as the offer| <span class="bool">bool</span> | 
`subscriptionSettings` > `serviceIds` <br />Collection of applicable services for the offer| <span class="array">array[integer]</span> | 
`fixedPriceDiscount` > `productSettings` <br />Product specific settings for the offer| <span class="array">array[objects]</span> | 
`productSettings` > `enabled` <br />Indication as to whether the offer can be used on a product purchase| <span class="bool">bool</span> | 
`productSettings` > `productIds` <br />Collection of products that can benefit from the offer| <span class="array">array[integer]</span> | 
`fixedPriceDiscount` > `miscellaneousChargeSettings` <br />Details specific to one-off charge| <span class="object">object</span> | 
`miscellaneousChargeSettings` > `enabled` <br />Indication as to whether the offer can be used on a one-off charge| <span class="bool">bool</span> | 


## Retrieve an Offer

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/offers/{offerReference} \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/offers/{offerReference}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/offers/{offerReference}")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/offers/{offerReference}")

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

conn.request("GET", "/api/offers/{offerReference}", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "offerReference": "string",
  "startDate": "2017-07-27T16:22:18.171Z",
  "expiryDate": "2017-07-27T16:22:18.171Z",
  "name": "string",
  "description": "string",
  "usageType": "UniqueToUserUseOnce",
  "applicationData": {
    "name": "string",
    "message": "string",
    "message2": "string"
  },
  "addCredits": {
    "amount": 0,
    "currency": "string",
    "paymentDetailsRequired": true
  },
  "lowStart": {
    "percentage": 0,
    "numberOfPeriods": 0,
    "lockInPeriods": 0,
    "closeSubOnExpiry": true,
    "serviceIds": [
      0
    ],
    "paymentDetailsRequired": true
  },
  "percentageDiscount": {
    "percentage": 0,
    "paymentDetailsRequired": true
  },
  "freePeriod": {
    "numberOfPeriods": 0,
    "serviceIds": [
      0
    ],
    "paymentDetailsRequired": true
  },
  "groupDiscount": {
    "activationCodeActivated": true,
    "metaData": {
      "qualifyingItemCount": 0,
      "freeItemCountOrDiscountAmount": 0,
      "productIds": [
        0
      ],
      "configurationType": "string",
      "productSource": "string",
      "customParameters": {}
    }
  },
  "fixedPriceDiscount": {
    "discountAmounts": [
      {
        "value": 0,
        "currency": "string"
      }
    ],
    "paymentDetailsRequired": true,
    "subscriptionSettings": {
      "enabled": true,
      "numberOfPeriods": 0,
      "lockInPeriods": 0,
      "closeSubOnExpiry": true,
      "serviceIds": [
        0
      ]
    },
    "productSettings": {
      "enabled": true,
      "productIds": [
        0
      ]
    },
    "miscellaneousChargeSettings": {
      "enabled": true
    }
  }
}
```

Calling this endpoint will return a specific instance of an offer.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/offers/{offerReference}</span>
</div>

### Response Parameters

 |  | 
--------- | ------- | 
`offerReference` <br />Unique identifier for the offer| <span class="string">string</span> | 
`startDate` <br />The date at which the offer becomes active| <span class="string">string</span> | 
`expiryDate` <br />The date at which the offer becomes inactive| <span class="string">string</span> | 
`name` <br />The name associated to the offer| <span class="string">string</span> | 
`description` <br />Additional details against the offer| <span class="string">string</span> | 
`usageType` <br />The type of usage applicable for the offer| <span class="string">string</span> | 
`applicationData` <br />Alternative data to display to an end-user| <span class="array">array[objects]</span> | 
`applicationData` > `name` <br />End-user name| <span class="string">string</span> |  
`applicationData` > `message` <br />Public facing message| <span class="string">string</span> | 
`applicationData` > `message2` <br />Additional public facing message| <span class="string">string</span> | 
`addCredits` <br />Information relating to an AddCredits offer type| <span class="array">array[objects]</span> | 
`addCredits` > `amount` <br />Amount of credit the account should receive| <span style="font-weight:bold;color:#666;">decimal</span> | 
`addCredits` > `currency` <br />Currency the credit should be added in| <span class="string">string</span> | 
`addCredits` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`lowStart` <br />Information relating to an LowStart offer type| <span class="array">array[objects]</span> | 
`lowStart` > `percentage` <br />The percentage discount the account should receive| <span style="font-weight:bold;color:#666;">decimal</span> |  
`lowStart` > `numberOfPeriods` <br />How long the discount should take place| <span class="integer">integer</span> | 
`lowStart` > `lockInPeriods` <br />Number of periods before the account can cancel their subscription| <span class="integer">integer</span> | 
`lowStart` > `closeSubOnExpiry` <br />Indication whether the subscription will expire at the same time as the offer| <span class="bool">bool</span> | 
`lowStart` > `serviceIds` <br />Collection of applicable services for the offer| <span class="array">array[integer]</span> | 
`lowStart` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`percentageDiscount` <br />Information relating to an PercentageDiscount offer type| <span class="array">array[objects]</span> | 
`percentageDiscount` > `percentage` <br />The percentage discount that will be received| <span style="font-weight:bold;color:#666;">decimal</span> | 
`percentageDiscount` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`freePeriod` <br />Information relating to an freePeriod offer type| <span class="array">array[objects]</span> | 
`freePeriod` > `numberOfPeriods` <br />How long the discount should take place| <span class="integer">integer</span> | 
`freePeriod` > `serviceIds` <br />Collection of applicable services for the offer| <span class="array">array[integer]</span> | 
`freePeriod` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`groupDiscount` <br />Information relating to an GroupDiscount offer type| <span class="array">array[objects]</span> | 
`groupDiscount` > `metaData` <br />Metadata of the group discount| <span class="object">object</span> | 
`metaData` > `qualifyingItemCount` <br />The number of items that must be purchased to be applicable for the offer| <span class="integer">integer</span> | 
`metaData` > `freeItemCountOrDiscountAmount` <br />The discount amount or the number of free items| <span class="integer">integer</span> | 
`metaData` > `productIds` <br />List of Products that can have the offer redeemed| <span class="array">array[integer]</span> | 
`groupDiscount` > `productSource` <br />Product source| <span class="string">string</span> | 
`groupDiscount` > `customParameters` <br />Dictionary of custom parameters applicable to the discount| <span class="dictionary">dictionary</span> | 
`fixedPriceDiscount` <br />Information relating to an FixedPriceDiscount offer type| <span class="array">array[objects]</span> | 
`fixedPriceDiscount` > `paymentDetailsRequired` <br />Indication as to whether the account is required to provide payment information| <span class="bool">bool</span> | 
`fixedPriceDiscount` > `discountAmounts` <br />Specific currency configuration| <span class="array">array[objects]</span> | 
`discountAmounts` > `value` <br />Amount to be discounted| <span style="font-weight:bold;color:#666;">decimal</span> | 
`discountAmounts` > `currency` <br />The associated currency| <span class="string">string</span> | 
`fixedPriceDiscount` > `subscriptionSettings` <br />Settings associated to the service aspect of a fixed price discount| <span class="array">array[objects]</span> | 
`subscriptionSettings` > `enabled` <br />Indication as to whether the offer can be used on a subscription purchase| <span class="bool">bool</span> | 
`subscriptionSettings` > `numberOfPeriods` <br />Number of renewing periods the offer is applicable for| <span class="integer">integer</span> | 
`subscriptionSettings` > `lockInPeriods` <br />The number of periods an account would be locked in if the offer was redeemed| <span class="integer">integer</span> | 
`subscriptionSettings` > `closeSubOnExpiry` <br />Indication whether the subscription will expire at the same time as the offer| <span class="bool">bool</span> | 
`subscriptionSettings` > `serviceIds` <br />Collection of applicable services for the offer| <span class="array">array[integer]</span> | 
`fixedPriceDiscount` > `productSettings` <br />Product specific settings for the offer| <span class="array">array[objects]</span> | 
`productSettings` > `enabled` <br />Indication as to whether the offer can be used on a product purchase| <span class="bool">bool</span> | 
`productSettings` > `productIds` <br />Collection of products that can benefit from the offer| <span class="array">array[integer]</span> | 
`fixedPriceDiscount` > `miscellaneousChargeSettings` <br />Details specific to one-off charge| <span class="object">object</span> | 
`miscellaneousChargeSettings` > `enabled` <br />Indication as to whether the offer can be used on a one-off charge| <span class="bool">bool</span> | 


## Retrieve all vouchers

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/offers/{offerReference}/vouchers \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/offers/{offerReference}/vouchers");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/offers/{offerReference}/vouchers")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .body("{}")
  .asString();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/offers/{offerReference}/vouchers")

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

conn.request("GET", "/api/offers/{offerReference}/vouchers", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript

```

> The above command returns JSON structured like this:

```json
[
    "J964AG3AJA",
    "7G94G3JJ5A",
    "67JAGJAD4G",
    "G7JMGGPPPP"
]
```

This endpoint will allow you to retrieve all available voucher codes that are applicable for use.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/offers/{offerReference}/vouchers</span>
</div>

### Response Parameters

 |  | 
--------- | ------- | 
List of available voucher codes for the configured offer | <span class="array">array[string]</span> | 
