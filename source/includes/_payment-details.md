# Payment Details

## Add a Payment Card

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/accounts/123456/payment-details/card \
  --header 'content-type: application/json' \
  --header 'x-clientpassword: MyP@ssword01' \
  --header 'x-clientid: 433' \
  --data '{"cardNumber":"4111111111111111","cardType":"Visa",
  "expiryDate":"01/19",  "issueCode":null,"securityCode":"123", 
  "billingHouseName":"Lilac Cottage","billingHouseFlatNumber":"12",
  "billingStreet":"Windermere Road","billingDistrict":null,
  "billingTownCity":"Chester","billingCounty":"Cheshire",
  "billingPostcode":"CH638BF","billingCountry":"United Kingdom",
  "setDefault":true,"associatedName":"My Visa Card","skipPreAuth":false}'
```

```csharp
insert csharp here
```

```java
insert java here
```

> The above command returns JSON structured like this:

```json
{
  "paymentDetailId": "604DB6C40EAA4C04BC6E65C4E4135069"
}
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

