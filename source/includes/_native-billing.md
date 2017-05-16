# Native Billing

## Validate a Roku Purchase

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

`POST http://uat.mppglobal.com/api/native-billing/roku/`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
rokuTransactionId | string | Optional | The roku transaction ID that is to be validated
email | string | Optional | Email address of the customer's Roku billing account
password | string | Optional | Customer's password
newAccountDetails | object | Optional | A sub-object of RokuValidateTransactionRequest, containing additional customer information
newAccountDetails > firstName | string | Optional | The customer's first name, as forwarded from Roku's native billing
newAccountDetails > lastName | string | Optional | The customer's last name, as forwarded from Roku's native billing







## Validate Existing Account's Roku Purchase

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

`POST http://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/roku`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
rokuTransactionId | string | Optional | The roku transaction ID that is to be validated







## Validate iTunes Purchase

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

`POST http://uat.mppglobal.com/api/native-billing/itunes`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
receipt | string | Required | The encrypted receipt returned from the iTunes stored when the app was purchased
email | string | Required | Email address of the purchaser
password | string | Required | Password address of the subscriber
newaccountdetails | object | Optional | New Account Details of the purchaser
newaccountdetails > firstName | string | Optional | First name of the purchaser
newaccountdetails > lastName | string | Optional | Last name of the purchaser







## Validate Existing Account's iTunes Purchase

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

`POST http://uat.mppglobal.com/api/accounts/{accountId}/subscriptions/native-billing/itunes`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
receipt | string | Yes | The encrypted receipt returned from the iTunes stored when the app was purchased





