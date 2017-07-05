# Social Sign-on

## Create Account via Third party 

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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/external-providers</span>
</div>

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
account | object | Optional | Account
account > accountId | integer | Optional | Id of the account
account > resourceReference | string | Optional | Resource reference
account > status | string | Optional | Status of account
account > email | string | Optional | Email of account
account > clientUserId | string | Yes | Client Id of the user
account > password | string | Optional | Account password
account > currentPassword | string | Optional | Current account password
account > newPassword | string | Optional | New account password
account > salutation | string | Optional | Salutation for account
account > firstName | string | Optional | Account first name
account > lastName | string | Optional | Account last name
account > phoneNumber | string | Optional | Account phone number
account > mobileNumber | string | Optional | Account mobile number
account > dateOfBirth | string | Optional | Date of birth of the Account
account > gender | string | Optional | Gender
account > addresses | array[object] | Optional | Addresses of Account
account > addresses > addressType | string | Optional | Address type
account > addresses > houseName | string | Optional | House name
account > addresses > houseNumber | string | Optional | House number
account > addresses > street | string | Optional | Street name
account > addresses > townCity | string | Optional | Name of town city
account > addresses > district | string | Optional | Name of district
account > addresses > state | string | Optional | State
account > addresses > county | string | Optional | County
account > addresses > postCode | string | Optional | Postcode
account > addresses > country | string | Optional | Country
account > addresses > isDefault | boolean | Optional | Is default
account > customParameters | object | Optional | Custom parameters
sessionToken | string | Optional | The session token




## Retrieve Available Third parties 

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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/external-providers</span>
</div>

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
availableProviders | array[object] | Optional | {MppGlobal.Api.Rest.Dtos.v1.UserAuthenticationProvider}
availableProviders > providerName | string | Optional | The name of 3rd party authentication provider
availableProviders > accountLinked | boolean | Optional | The account status




## Link Facebook Account 

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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/link/external-providers/facebook</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
facebookRedirectURI | string | Yes | Gets or sets the FacebookRedirectURI
authorisationCode | string | Optional | AuthorisationCode
accessToken | string | Optional | AccessToken
applicationIdentifier | string | Yes | ApplicationIdentifier





## Link Janrain Account 

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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/link/external-providers/janrain</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
accessToken | string | Yes | Gets or sets the AccessToken






## Authenticate via Facebook 

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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/authenticate/external-providers/facebook</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
facebookRedirectURI | string | Yes | FacebookRedirectURI
authorisationCode | string | Optional | Authorisation Code
accessToken | string | Optional | Access Token
applicationIdentifier | string | Yes | Application Identifier






## Authenticate via Janrain 

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
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/authenticate/external-providers/janrain</span>
</div>

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
accessToken | string | Yes | Gets the access token




