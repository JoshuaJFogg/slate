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

`POST http://uat.mppglobal.com/api/accounts/{accountId}/groups`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
groupName | string | Optional | The name of the group






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

`GET http://uat.mppglobal.com/api/accounts/{accountId}/groups`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
groups | array[object] | optional | Groups
groups > role | string | optional | Role
groups > groupInfo | object | optional | GroupInfo class
groups > groupInfo > accountGroupName | string | optional | AccountGroupName
groups > groupInfo > accountGroupToken | string | optional | AccountGroupToken
groups > groupInfo > created | string | optional | Created
groups > groupInfo > lastUpdated | string | optional | LastUpdated
groups > groupInfo > payeeInfo | object | optional | AccountGroupInfoPayeeAccount
groups > groupInfo > payeeInfo > clientUserId | string | optional | ClientUserId
groups > groupInfo > payeeInfo > firstName | string | optional | FirstName
groups > groupInfo > payeeInfo > lastName | string | optional | LastName
groups > groupInfo > payeeInfo > email | string | optional | Email
groups > groupInfo > ipRanges | array[object] | optional | IpRanges
groups > groupInfo > ipRanges > start | string | optional | Start of the range
groups > groupInfo > ipRanges > end | string | optional | End of the range
groups > groupInfo > emailDomains | array[string] | optional | EmailDomains
groups > groupInfo > permitUserPayments | boolean | optional | PermitUserPayments
groups > groupInfo > matchEmailOnlyAfterIpMatch | boolean | optional | MatchEmailOnlyAfterIpMatch






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

`GET http://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members`

### Query String Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
role | string | optional | The account's role within the group
rowsPerPage | integer | optional | Rows per page
currentPage | integer | optional | Current page
firstName | string | optional | First name
surName | string | optional | Surname






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

`POST http://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members`

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

`DELETE http://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/members/{accountId}`






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

`GET http://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
subscriptions | array[object] | optional | Subscriptions
subscriptions > accountSubscriptionInfo | object | optional | Account Subscription Info
subscriptions > accountSubscriptionInfo > expiryDate | string | optional | Expiry Date
subscriptions > accountSubscriptionInfo > firstNonDiscountedBillingPointUtc | string | optional | First Non Discounted Billing PointUTC
subscriptions > accountSubscriptionInfo > lastDiscountedBillingPointUtc | string | optional | Last Discounted Billing PointUTC
subscriptions > accountSubscriptionInfo > paymentMethod | string | optional | Payment Method
subscriptions > accountSubscriptionInfo > recurringPaymentInfo | object | optional | Recurring Payment Info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > subscriptionReference | integer | optional | Subscription Reference
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > resourceReference | string | optional | Unique Resource Reference
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > configuredSubscriptionPrice | number | optional | Configured Subscription Price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > subscribedPrice | number | optional | Subscribed Price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > currency | string | optional | Currency
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > recurringPaymentEnable | string | optional | Recurring Payment Enable
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > subscriptionLockedIn | string | optional | Subscription LockedIn
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > nextPaymentDate | string | optional | Next Payment Date
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo | object | optional | Previous Billing Info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > subscriptionPriceId | integer | optional | Subscription Price Id
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > totalAmount | number | optional | Total Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > totalTaxAmount | number | optional | Total Tax Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > totalNetAmount | number | optional | Total Net Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > billingDate | string | optional | Billing Date
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > paymentDate | string | optional | Payment Date
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo | array[object] | optional | Tax info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > regionName | string | optional | Region Name
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > regionType | string | optional | Region Type
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > displayName | string | optional | Display Name
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > category | string | optional | Category
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > rate | number | optional | Rate
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > taxInfo > amount | number | optional | Amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems | array[object] | optional | Price Items
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > thirdPartyRef | string | optional | Gets or sets the external reference
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > supplierId | integer | optional | Gets or sets the supplier id
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > price | number | optional | Gets or sets the price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > description | string | optional | Gets or sets the description
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > isGrossAmount | string | optional | Specify whether is groos amount
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > previousBillingInfo > priceItems > taxCategoryName | string | optional | Tax Category Name
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo | object | optional | Group Subscription Info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > licenseLevel | integer | optional | License Level
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > overflowLevel | integer | optional | Overflow Level
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList | array[object] | optional | Subscriber List
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList > subscriptionId | integer | optional | SubscriptionId
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList > emailAddress | string | optional | Email Address
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > subscriberList > clientUserId | string | optional | ClientUserId
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > overFlowCount | integer | optional | Overflow Count
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > fullSubscriptionsCount | integer | optional | Full Subscriptions Count
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > groupSubscriptionInfo > currentUserInOverFlow | string | optional | Specify whether Current User In OverFlow
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > voucherCodes | object | optional | Voucher Code
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > voucherCodes > voucherCode | string | optional | Voucher Code
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > voucherCodes > discountPrice | number | optional | Discount Price
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > statusInfo | object | optional | Status info
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > statusInfo > statusId | integer | optional | Status id
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > statusInfo > statusDescription | string | optional | Status description
subscriptions > accountSubscriptionInfo > recurringPaymentInfo > customParameters | object | optional | Custom parameters
subscriptions > accountSubscriptionInfo > paymentScheduleInfo | object | optional | Payment Schedule Info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > startDate | string | optional | Start Date
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > frequency | string | optional | Start Date
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > totalAmount | number | optional | Total Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > paymentDayOffset | integer | optional | Payment Day Offset
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > paymentDay | integer | optional | Payment Day
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > currency | string | optional | Currency
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > paymentMethod | string | optional | Payment Method
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments | string | optional | Scheduled Payments
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > orderId | integer | optional | Order Id
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > orderDate | string | optional | Order Date
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > status | string | optional | Status
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo | object | optional | Price Info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > grossAmount | number | optional | Gross Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > netAmount | number | optional | Gross Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > totalTaxAmount | number | optional | Total Tax Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo | array[object] | optional | Tax Info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > regionName | string | optional | Region Name
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > regionType | string | optional | Region Type
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > displayName | string | optional | Display Name
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > category | string | optional | Category
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > rate | number | optional | Rate
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > scheduledPayments > priceInfo > taxInfo > amount | number | optional | Amount
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > statusInfo | object | optional | Status info
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > statusId | integer | optional | Status id
subscriptions > accountSubscriptionInfo > paymentScheduleInfo > statusDescription | string | optional | Status description
subscriptions > defaultSubscriptionInfo | object | optional | Default Subscription Info
subscriptions > defaultSubscriptionInfo > customParameters | object | optional | Custom Parameters
subscriptions > defaultSubscriptionInfo > subscriptionId | integer | optional | Subscription Id
subscriptions > defaultSubscriptionInfo > subscriptionStatus | string | optional | Subscription Status
subscriptions > defaultSubscriptionInfo > subscriptionTitle | string | optional | Subscription Title
subscriptions > defaultSubscriptionInfo > subscriptionGroup | string | optional | Subscription Group







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

`DELETE http://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members/{accountId}`





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

`PATCH http://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/licenses`

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

`POST http://uat.mppglobal.com/api/accounts/groups/{accountGroupToken}/subscriptions/{subscriptionId}/members`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
useOverFlowLicense | boolean | Optional | Use Overflow lincense
clientUserId | string | Optional | Gets or sets the client user id
emailAddress | string | Optional | Email Address
taxInfo | object | Optional | {MppGlobal.Api.Rest.Dtos.v1.TaxRegionInfo} Tax region info class
taxInfo > zeroRated | string | Optional | Gets or sets the zero rated
taxInfo > country | string | Optional | Gets or sets the country
taxInfo > state | string | Optional | Gets or sets the state
taxInfo > county | string | Optional | Gets or sets the county
taxInfo > city | string | Optional | Gets or sets the city





