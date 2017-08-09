# Account Groups

## Create Group

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/groups</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
groupName | string | No | The name of the group






## Retrieve Account Groups

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/groups</span>
</div>

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
groups | array[object] | No | Groups
groups > role | string | No | Role
groups > groupInfo | object | No | GroupInfo class
groups > groupInfo > accountGroupName | string | No | AccountGroupName
groups > groupInfo > accountGroupToken | string | No | AccountGroupToken
groups > groupInfo > created | string | No | Created
groups > groupInfo > lastUpdated | string | No | LastUpdated
groups > groupInfo > payeeInfo | object | No | AccountGroupInfoPayeeAccount
groups > groupInfo > payeeInfo > clientUserId | string | No | ClientUserId
groups > groupInfo > payeeInfo > firstName | string | No | FirstName
groups > groupInfo > payeeInfo > lastName | string | No | LastName
groups > groupInfo > payeeInfo > email | string | No | Email
groups > groupInfo > ipRanges | array[object] | No | IpRanges
groups > groupInfo > ipRanges > start | string | No | Start of the range
groups > groupInfo > ipRanges > end | string | No | End of the range
groups > groupInfo > emailDomains | array[string] | No | EmailDomains
groups > groupInfo > permitUserPayments | Bool | No | PermitUserPayments
groups > groupInfo > matchEmailOnlyAfterIpMatch | Bool | No | MatchEmailOnlyAfterIpMatch






## Retrieve a Group's Members

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members</span>
</div>

### Query String Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
role | string | No | The account's role within the group
rowsPerPage | integer | No | Rows per page
currentPage | integer | No | Current page
firstName | string | No | First name
surName | string | No | Surname






## Add a Member to a Group

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
email | string | Yes/No | The email associated with the account
clientUserId | string | Yes/No | The userID of the client






## Delete an Account from a Group

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}</span>
</div>





## Retrieve a Group's Subscription

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions</span>
</div>

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
subscriptions | array[object] | No | Subscriptions
subscriptions > accountSubscriptionInfo | object | No | Account Subscription Info
subscriptions > accountSubscriptionInfo > expiryDate | string | No | Expiry Date
subscriptions > accountSubscriptionInfo > firstNonDiscountedBillingPointUtc | string | No | First Non Discounted Billing PointUTC
subscriptions > accountSubscriptionInfo > lastDiscountedBillingPointUtc | string | No | Last Discounted Billing PointUTC
subscriptions > accountSubscriptionInfo > paymentMethod | string | No | Payment Method
subscriptions > accountSubscriptionInfo > recurringPaymentInfo | object | No | Recurring Payment Info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > subscriptionReference | integer | No | Subscription Reference
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > resourceReference | string | No | Unique Resource Reference
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > configuredSubscriptionPrice | number | No | Configured Subscription Price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > subscribedPrice | number | No | Subscribed Price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > currency | string | No | Currency
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > recurringPaymentEnable | string | No | Recurring Payment Enable
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > subscriptionLockedIn | string | No | Subscription LockedIn
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > nextPaymentDate | string | No | Next Payment Date
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo | object | No | Previous Billing Info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > subscriptionPriceId | integer | No | Subscription Price Id
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > totalAmount | number | No | Total Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > totalTaxAmount | number | No | Total Tax Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > totalNetAmount | number | No | Total Net Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > billingDate | string | No | Billing Date
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > paymentDate | string | No | Payment Date
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo | array[object] | No | Tax info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > regionName | string | No | Region Name
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > regionType | string | No | Region Type
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > displayName | string | No | Display Name
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > category | string | No | Category
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > rate | number | No | Rate
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > amount | number | No | Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems | array[object] | No | Price Items
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > thirdPartyRef | string | No | Gets or sets the external reference
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > supplierId | integer | No | Gets or sets the supplier id
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > price | number | No | Gets or sets the price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > description | string | No | Gets or sets the description
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > isGrossAmount | string | No | Specify whether is groos amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > taxCategoryName | string | No | Tax Category Name
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo | object | No | Group Subscription Info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > licenseLevel | integer | No | License Level
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > overflowLevel | integer | No | Overflow Level
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList | array[object] | No | Subscriber List
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList > subscriptionId | integer | No | SubscriptionId
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList > emailAddress | string | No | Email Address
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList > clientUserId | string | No | ClientUserId
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > overFlowCount | integer | No | Overflow Count
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > fullSubscriptionsCount | integer | No | Full Subscriptions Count
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > currentUserInOverFlow | string | No | Specify whether Current User In OverFlow
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > voucherCodes | object | No | Voucher Code
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > voucherCodes > voucherCode | string | No | Voucher Code
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > voucherCodes > discountPrice | number | No | Discount Price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > statusInfo | object | No | Status info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > statusInfo > statusId | integer | No | Status id
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > statusInfo > statusDescription | string | No | Status description
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > customParameters | object | No | Custom parameters
subscriptions > accountSubscriptionInfo > paymentScheduleInfo | object | No | Payment Schedule Info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > startDate | string | No | Start Date
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > frequency | string | No | Start Date
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > totalAmount | number | No | Total Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > paymentDayOffset | integer | No | Payment Day Offset
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > paymentDay | integer | No | Payment Day
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > currency | string | No | Currency
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > paymentMethod | string | No | Payment Method
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments | string | No | Scheduled Payments
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > orderId | integer | No | Order Id
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > orderDate | string | No | Order Date
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > status | string | No | Status
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo | object | No | Price Info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > grossAmount | number | No | Gross Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > netAmount | number | No | Gross Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > totalTaxAmount | number | No | Total Tax Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo | array[object] | No | Tax Info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > regionName | string | No | Region Name
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > regionType | string | No | Region Type
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > displayName | string | No | Display Name
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > category | string | No | Category
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > rate | number | No | Rate
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > amount | number | No | Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > statusInfo | object | No | Status info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > statusId | integer | No | Status id
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > statusDescription | string | No | Status description
subscriptions > defaultSubscriptionInfo | object | No | Default Subscription Info
subscriptions > defaultSubscriptionInfo > customParameters | object | No | Custom Parameters
subscriptions > defaultSubscriptionInfo > subscriptionId | integer | No | Subscription Id
subscriptions > defaultSubscriptionInfo > subscriptionStatus | string | No | Subscription Status
subscriptions > defaultSubscriptionInfo > subscriptionTitle | string | No | Subscription Title
subscriptions > defaultSubscriptionInfo > subscriptionGroup | string | No | Subscription Group







## Delete an Account from a Subscription

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members/{accountId}</span>
</div>



## Edit Licence Level

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-patch">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/licenses</span>
</div>

### PATCH Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
standard | string | Yes/No | 1 vaildation
overflow | string | Yes/No | 1 validation







## Add a Member to a Subscription

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json

```

Description of what the endpoint does.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
useOverFlowLicense | Bool | No | Use Overflow lincense
clientUserId | string | No | Gets or sets the client user id
emailAddress | string | No | Email Address
taxInfo | object | No | {MppGlobal.Api.Rest.Dtos.v1.TaxRegionInfo} Tax region info class
taxInfo > zeroRated | string | No | Gets or sets the zero rated
taxInfo > country | string | No | Gets or sets the country
taxInfo > state | string | No | Gets or sets the state
taxInfo > county | string | No | Gets or sets the county
taxInfo > city | string | No | Gets or sets the city





