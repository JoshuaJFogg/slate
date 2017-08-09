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

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
`productReference` | string | No | Providing this parameter will return offers specific to this product
`status` | string | No | Indicates whether to return `Active` or `Disabled` offers
`pageNumber` | integer | No | Which page should be returned
`rowsPerPage` | integer | No | The number of results to return per page

### Response Parameters

Parameter | Type | Description | 
--------- | ------- | ----------- |
`totalNumberOfRecords` | string | The total number of offers found as a result of the request
`pageNumber` | string | The page number being displayed
`resultsPerPage` | integer | The number of records being displayed
`items` | array[objects] | Collection of all offers
`items` > `offerReference` | string | Unique identifier for the offer
`items` > `startDate` | string | The date at which the offer becomes active
`items` > `expiryDate` | string | The date at which the offer becomes inactive
`items` > `name` | string | The name associated to the offer
`items` > `description` | string | Additional details against the offer
`items` > `usageType` | string | The type of usage applicable for the offer
`items` > `applicationData` | array[objects] | Alternative data to display to an end-user
`applicationData` > `name` | string | End-user name 
`applicationData` > `message` | string | Public facing message
`applicationData` > `message2` | string | Additional public facing message
`items` > `addCredits` | array[objects] | Information relating to an AddCredits offer type
`addCredits` > `amount` | decimal | Amount of credit the account should receive
`addCredits` > `currency` | string | Currency the credit should be added in
`addCredits` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`items` > `lowStart` | array[objects] | Information relating to an LowStart offer type
`lowStart` > `percentage` | decimal | The percentage discount the account should receive 
`lowStart` > `numberOfPeriods` | integer | How long the discount should take place
`lowStart` > `lockInPeriods` | integer | Number of periods before the account can cancel their subscription
`lowStart` > `closeSubOnExpiry` | Bool | Indication whether the subscription will expire at the same time as the offer
`lowStart` > `serviceIds` | array[integer] | Collection of applicable services for the offer
`lowStart` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`items` > `percentageDiscount` | array[objects] | Information relating to an PercentageDiscount offer type
`percentageDiscount` > `percentage` | decimal | The percentage discount that will be received
`percentageDiscount` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`items` > `freePeriod` | array[objects] | Information relating to an freePeriod offer type
`freePeriod` > `numberOfPeriods` | integer | How long the discount should take place
`freePeriod` > `serviceIds` | array[integer] | Collection of applicable services for the offer
`freePeriod` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`items` > `groupDiscount` | array[objects] | Information relating to an GroupDiscount offer type
`groupDiscount` > `metaData` | objects | Metadata of the group discount
`metaData` > `qualifyingItemCount` | integer | The number of items that must be purchased to be applicable for the offer
`metaData` > `freeItemCountOrDiscountAmount` | integer | The discount amount or the number of free items
`metaData` > `productIds` | array[integer] | List of Products that can have the offer redeemed
`groupDiscount` > `productSource` | string | Product source
`groupDiscount` > `customParameters` | dictionary | Dictionary of custom parameters applicable to the discount
`items` > `fixedPriceDiscount` | array[objects] | Information relating to an FixedPriceDiscount offer type
`fixedPriceDiscount` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`fixedPriceDiscount` > `discountAmounts` | array[objects] | Specific currency configuration
`discountAmounts` > `value` | decimal | Amount to be discounted
`discountAmounts` > `currency` | string | The associated currency
`fixedPriceDiscount` > `subscriptionSettings` | array[objects] | Settings associated to the service aspect of a fixed price discount
`subscriptionSettings` > `enabled` | Bool | Indication as to whether the offer can be used on a subscription purchase
`subscriptionSettings` > `numberOfPeriods` | integer| Number of renewing periods the offer is applicable for
`subscriptionSettings` > `lockInPeriods` | integer | The number of periods an account would be locked in if the offer was redeemed
`subscriptionSettings` > `closeSubOnExpiry` | Bool | Indication whether the subscription will expire at the same time as the offer
`subscriptionSettings` > `serviceIds` | array[integer] | Collection of applicable services for the offer
`fixedPriceDiscount` > `productSettings` | array[objects] | Product specific settings for the offer
`productSettings` > `enabled` | Bool | Indication as to whether the offer can be used on a product purchase
`productSettings` > `productIds` | array[integer] | Collection of products that can benefit from the offer
`fixedPriceDiscount` > `miscellaneousChargeSettings` | objects | Details specific to one-off charge
`miscellaneousChargeSettings` > `enabled` | Bool | Indication as to whether the offer can be used on a one-off charge


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

Parameter | Type | Description | 
--------- | ------- | ----------- |
`offerReference` | string | Unique identifier for the offer
`startDate` | string | The date at which the offer becomes active
`expiryDate` | string | The date at which the offer becomes inactive
`name` | string | The name associated to the offer
`description` | string | Additional details against the offer
`usageType` | string | The type of usage applicable for the offer
`applicationData` | array[objects] | Alternative data to display to an end-user
`applicationData` > `name` | string | End-user name 
`applicationData` > `message` | string | Public facing message
`applicationData` > `message2` | string | Additional public facing message
`addCredits` | array[objects] | Information relating to an AddCredits offer type
`addCredits` > `amount` | decimal | Amount of credit the account should receive
`addCredits` > `currency` | string | Currency the credit should be added in
`addCredits` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`lowStart` | array[objects] | Information relating to an LowStart offer type
`lowStart` > `percentage` | decimal | The percentage discount the account should receive 
`lowStart` > `numberOfPeriods` | integer | How long the discount should take place
`lowStart` > `lockInPeriods` | integer | Number of periods before the account can cancel their subscription
`lowStart` > `closeSubOnExpiry` | Bool | Indication whether the subscription will expire at the same time as the offer
`lowStart` > `serviceIds` | array[integer] | Collection of applicable services for the offer
`lowStart` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`percentageDiscount` | array[objects] | Information relating to an PercentageDiscount offer type
`percentageDiscount` > `percentage` | decimal | The percentage discount that will be received
`percentageDiscount` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`freePeriod` | array[objects] | Information relating to an freePeriod offer type
`freePeriod` > `numberOfPeriods` | integer | How long the discount should take place
`freePeriod` > `serviceIds` | array[integer] | Collection of applicable services for the offer
`freePeriod` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`groupDiscount` | array[objects] | Information relating to an GroupDiscount offer type
`groupDiscount` > `metaData` | objects | Metadata of the group discount
`metaData` > `qualifyingItemCount` | integer | The number of items that must be purchased to be applicable for the offer
`metaData` > `freeItemCountOrDiscountAmount` | integer | The discount amount or the number of free items
`metaData` > `productIds` | array[integer] | List of Products that can have the offer redeemed
`groupDiscount` > `productSource` | string | Product source
`groupDiscount` > `customParameters` | dictionary | Dictionary of custom parameters applicable to the discount
`fixedPriceDiscount` | array[objects] | Information relating to an FixedPriceDiscount offer type
`fixedPriceDiscount` > `paymentDetailsRequired` | Bool | Indication as to whether the account is required to provide payment information
`fixedPriceDiscount` > `discountAmounts` | array[objects] | Specific currency configuration
`discountAmounts` > `value` | decimal | Amount to be discounted
`discountAmounts` > `currency` | string | The associated currency
`fixedPriceDiscount` > `subscriptionSettings` | array[objects] | Settings associated to the service aspect of a fixed price discount
`subscriptionSettings` > `enabled` | Bool | Indication as to whether the offer can be used on a subscription purchase
`subscriptionSettings` > `numberOfPeriods` | integer| Number of renewing periods the offer is applicable for
`subscriptionSettings` > `lockInPeriods` | integer | The number of periods an account would be locked in if the offer was redeemed
`subscriptionSettings` > `closeSubOnExpiry` | Bool | Indication whether the subscription will expire at the same time as the offer
`subscriptionSettings` > `serviceIds` | array[integer] | Collection of applicable services for the offer
`fixedPriceDiscount` > `productSettings` | array[objects] | Product specific settings for the offer
`productSettings` > `enabled` | Bool | Indication as to whether the offer can be used on a product purchase
`productSettings` > `productIds` | array[integer] | Collection of products that can benefit from the offer
`fixedPriceDiscount` > `miscellaneousChargeSettings` | objects | Details specific to one-off charge
`miscellaneousChargeSettings` > `enabled` | Bool | Indication as to whether the offer can be used on a one-off charge


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

Parameter | Type | Description | 
--------- | ------- | ----------- |
`--` | array[string] | List of available voucher codes for the configured offer
