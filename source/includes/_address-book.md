# Address Book

## Create Address

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

`POST http://uat.mppglobal.com/api/accounts/{accountId}/addresses`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
houseName | string | optional | This is the name of the house
houseNumber | string | optional | This is the number of the house
street | string | optional | The street/road that the house is on
townCity | string | optional | The town or city of the account holder
district | string | optional | The district the town or city is in
state | string | optional | The state, if applicable
county | string | optional | The county, if applicable
postCode | string | optional | The postcode or zipcode
country | string | optional | The residing country of the account






## Retrieve Address Book

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

`GET http://uat.mppglobal.com/api/accounts/{accountId}/addresses`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
addressBook | array[object] | optional | The list of addresses
addressBook > addressIdentifier | string | optional | The address identifier
addressBook > houseName | string | optional | House name
addressBook > houseNumber | string | optional | House number
addressBook > street | string | optional | Street name
addressBook > townCity | string | optional | Name of town city
addressBook > district | string | optional | Name of district
addressBook > state | string | optional | State
addressBook > county | string | optional | County
addressBook > postCode | string | optional | Postcode
addressBook > country | string | optional | Country
addressBook > isDefault | boolean | optional | Is default





