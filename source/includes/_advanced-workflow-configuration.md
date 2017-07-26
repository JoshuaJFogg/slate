# Advanced Workflows

## Complete a Subscription Purchase (Advanced)

```shell
Not available
```

```csharp
Not available
```

```java
Not available
```

```ruby
Not available
```

```python
Not available
```

```javascript

```

> The above command returns JSON structured like this:

```json
{
  "amountCharged": 10
  "currency": "GBP",
  "paymentType": "PayPal",
  "subscriptionStatus": "Active",
  "renewalDay": 1,
  "renewalDayOffset": 0,
  "startDate": "2017-01-01T00:00:00",
  "renewalDate": "2018-01-01T00:00:00",
  "orderReference": 12548,
  "subscriptionId": 4555888,
  "subscriptionPriceId": 568845,
  "subscriptionReference": "458845",
  "resourceReference": "001DFTBDC03",
  "asynchronousProcessingParameters": null
}
```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/workflows/purchases/subscriptions</span>
</div>

### Request Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
name | string | Yes/No | What does the parameter represent?


