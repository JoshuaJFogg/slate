# Analytics

## Retrieve Analytics Data

```shell
curl --request GET \
  --url 'https://uat.mppglobal.com/api/analytics/methodName?enddate=2099-05-18T00%3A00%3A00.000Z&startdate=2017-05-18T00%3A00%3A00.000Z' \
  --header 'x-clientid: 1001' \
  --header 'x-clientpassword: Str0ngP@ssword' \
  --header 'x-version: 10.0.0' \
  --data '{}'
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/analytics/methodName?enddate=2099-05-18T00%3A00%3A00.000Z&startdate=2017-05-18T00%3A00%3A00.000Z");
var request = new RestRequest(Method.GET);
request.AddHeader("x-version", "10.0.0");
request.AddHeader("x-clientpassword", "Str0ngP@ssword");
request.AddHeader("x-clientid", "1001");
request.AddParameter("undefined", "{}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```java
HttpResponse<String> response = Unirest.get("https://uat.mppglobal.com/api/analytics/methodName?enddate=2099-05-18T00%3A00%3A00.000Z&startdate=2017-05-18T00%3A00%3A00.000Z")
  .header("x-clientid", "1001")
  .header("x-clientpassword", "Str0ngP@ssword")
  .header("x-version", "10.0.0")
  .body("{}")
  .asString();
```
```ruby
require 'uri'
require 'net/http'

url = URI("https://uat.mppglobal.com/api/analytics/methodName?enddate=2099-05-18T00%3A00%3A00.000Z&startdate=2017-05-18T00%3A00%3A00.000Z")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-clientid"] = '1001'
request["x-clientpassword"] = 'Str0ngP@ssword'
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
    'x-clientid': "1001",
    'x-clientpassword': "Str0ngP@ssword",
    'x-version': '10.0.0'
    }

conn.request("GET", "/api/analytics/methodName?enddate=2099-05-18T00%3A00%3A00.000Z&startdate=2017-05-18T00%3A00%3A00.000Z", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
Unavailable
```

> The above command returns JSON structured like this:

```json
[
  {
    "parameterName": "parameterValue"
  }
]
```

This endpoint can be used to extract predefined datasets from eSuite for use in external dashboards.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/analytics/{method}</span>
</div>

### Query string

 |  |  | 
--------- | ------- | ------- | 
`startdate` <br />DateTime (No) for start of query| <span class="string">string</span> |  | 
`enddate` <br />DateTime (No) for end of query| <span class="string">string</span> |  | 
`referencecurrency` <br />If the method returns a financial information. It is possible to restrict down by currency| <span class="string">string</span> |  | 
`timezoneoffset` <br />All data stored in eSuite is stored in UTC. If you require it in your local time, provide your UTC offset e.g. 1| <span class="integer">integer</span> |  | 

### Available Data Sources

 |
--------- 
`Dynamic_Account_Authentication_Attempts` <br />Account authentication attempts (per day) | 
`Dynamic_Authentication_RequestsPerHour` <br />Account authentication attempts (per hour) | 
`Dynamic_Accounts_ByStatus`<br />Account Status |  
`Dynamic_Accounts_CreatedByDay` <br />Account creation profile | 
`Dynamic_Cards_Expiring_Next_Month`<br />Expiring Cards | 
`Dynamic_Consumer_Payment_Methods` <br />Consumer Payment Methods | 
`Dynamic_CreditDebitCard_Autorisations` <br />Payment card authorisation attempts | 
`Dynamic_Most_Redeemed_Offers` <br />Most redeemed Offers | 
`Dynamic_NonSubscriptions_RevenueByDay` <br />None Subscription Revenue (by day) | 
`Dynamic_NonSubscriptions_RevenueByPaymentType` <br />None Subscription Revenue (by payment type) | 
`Dynamic_Payment_Attempts_Per_Period` <br />Payment Attempts (by period) | 
`Dynamic_PromotionCodes_ByDay` <br />Promotion Code redemption (by day) | 
`Dynamic_PromotionCodes_RedeemedInPeriod` <br />Promotion Code redemption (by period) | 
`Dynamic_Revenue_AllByDay` <br />All revenue generated per day | 
`Dynamic_RPM_GetCountOfApiMethods` <br />API Method Count | 
`Dynamic_RPM_GetTop50Minutes` <br />Top RPM Count | 
`Dynamic_Subscriptions_ActiveByDay` <br />Active Subscription (by day) | 
`Dynamic_Subscriptions_ActiveByServiceId` <br />Active Subscription (by Subscription Service) | 
`Dynamic_Subscriptions_Added` <br />Subscriptions added |
`Dynamic_Subscriptions_ChurnbyMonth` <br />Subscription Churn (by month) | 
`Dynamic_Subscriptions_ChurnByReason` <br />ubscription Churn (by reason) | 
`Dynamic_Subscriptions_ChurnByService` <br />Subscription Churn (by Subscription Service) | 
`Dynamic_Subscriptions_ChurnPredictionPrecisionV5LastMonth` <br />Churn Prediction Precision (previous month)  | 
`Dynamic_Subscriptions_ChurnPredictionPrecisionV5ThisMonth` <br />Churn Prediction Precision (current month) | 
`Dynamic_Subscriptions_RevenueByDay` <br />Subscription revenue (by day) | 
`Dynamic_Subscriptions_RevenueByPaymentType` <br />Subscription revenue (by payment type) | 
`Dynamic_Top_Subscription_Types` <br />Top performing Subscriptions | 
`Dynamic_Voucher_Codes_Redeemed_Per_Period` <br />Voucher redemption | 
`RPM_Core_Get` <br />eSuite Core API Requests (per minute) | 



