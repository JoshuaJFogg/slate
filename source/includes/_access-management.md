# Access Management

## Create Access

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

`POST http://uat.mppglobal.com/api/accounts/{accountId}/entitlements`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
name | string | Optional | The name of entitlement
identifier | string | Yes | The identifier of entitlement
startDate | string | Yes | The create date of the entitlement
endDate | string | Yes | The expiry of the entitlement







## Search for Access

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

`GET http://uat.mppglobal.com/api/accounts/{accountId}/entitlements/search`

### Query string

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
createDateMin | string | Optional | 1 validations
createDateMax | string | Optional | 1 validations
startDateMin | string | Optional | 1 validations
startDateMax | string | Optional | 1 validations
endDateMin | string | Optional | 1 validations
endDateMax | string | Optional | 1 validations
entitlementIdentifier | string | Optional | 
rowsPerPage | integer | Optional | 1 validations
currentPage | integer | Optional | 1 validations
exactMatch | boolean | Optional | 







## Retrieve all Access

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

`GET http://uat.mppglobal.com/api/accounts/{accountId}/entitlements`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
entitlements | string | Optional | The list of current account entitlements
name | string | Optional | The name of entitlement
identifier | string | Required | The identifier of entitlement
startDate | string | Required | The create date of the entitlement
endDate | string | Required | The expire date of the entitlement







## Validate Access

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

`GET http://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}`

### Query String

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
incrementUsage | boolean | Optional | 
deviceIdentifier | string | Optional | 






## Delete Access

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

`DELETE http://uat.mppglobal.com/api/accounts/{accountId}/entitlements/{entitlementIdentifier}`







