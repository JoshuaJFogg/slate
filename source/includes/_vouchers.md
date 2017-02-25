# Vouchers

## Validate a voucher

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```csharp
# With C#, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```java
# With Java, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "purchaseInfo" : {
    "purchasePrice" : 2.00,
    "discountPrice" : 1.25,
    "renewalPrice" : 5.50
  },
  "promotionInfo" : {
    "startDate" : "",
    "expiryDate" : "",
    "offerInfo" : {
      "name" : "",
      "description" : "",
      "usageType" : "",
      "applicationData" : {
        "name" : "",
        "message" : "",
        "message2" : "",
        "addCredits" : {
          "amount" : 15.00,
          "currency" : "GBP",
          "paymentDetailsRequired" : true
        },
        "lowStart" : {
          "percentage" : 10.00,
          "numberOfPeriods" : 2,
          "lockInPeriods" : 0,
          "closeSubOnExpiry" : true,
          "serviceIds" : [12354, 48511],
          "paymentDetailsRequired" : true
        },
        "percentageDiscount" : {
          "percentage" : 10.00,
          "paymentDetailsRequired" : true
        },
        "freePeriod" : {
          "numberOfPeriods" : 2,
          "serviceIds" : [12354, 48511],
          "paymentDetailsRequired" : true
        },
        "groupDiscount" : {

        }
      }
    }
  }
}
```

This endpoint retrieves all kittens.

### HTTP Request

`GET https://uat.mppglobal.com/api/voucher/:voucherCode/validate`

### Query Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
paymentDatesToCalculate | integer | Yes | 
paymentDatesStartDate | string | Yes | 
clientUserId | string | Yes | 

<aside class="success">
Only one offer type object will be populated depending on the voucher code you have passed.
</aside>
