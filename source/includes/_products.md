# Products
## Retrieve 

```shell
curl --request GET \
  --url https://uat.mppglobal.com/api/products \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/products/");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/products")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
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
request["x-version"] = '10.0.0'
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
    'x-version': '10.0.0'
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
    "x-version": "10.0.0",
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

 |  |  | 
--------- | ------- | ------- | 
`productIds` <br />A collection of product Identifiers| <span class="array">array[integer]</span> |  | 
`currency` <br />The currency prices should be returned| <span class="string">string</span> |  | 


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


