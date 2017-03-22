# Session Authentication

## Login using email address

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
    "accountId": 141458,
    "resourceReference": "OO45FTG67GTF",
    "sessionToken": "7c7e316ff9c6453fae5da7b7c26c4c77"
  }
```

This endpoint allows customers to authenticate themselves and gain a session for their eSuite account.

### URL End-point

`POST https://uat.mppglobal.com/api/accounts/authenticate`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
email | string | Yes | The email address associated to the eSuite account.
password | string | Yes | The password the customer has associated to their account.


## Login using client-defined identifiers

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
    "accountId": 141458,
    "resourceReference": "OO45FTG67GTF",
    "sessionToken": "7c7e316ff9c6453fae5da7b7c26c4c77"
  }
```

This endpoint allows third-party systems gain a session for an account that isn't mastered in eSuite.

### URL End-point

`POST https://uat.mppglobal.com/api/accounts/authenticate/:clientUserId`

<aside class="warning">
Client-defined identifiers (clientUserId) are a single key authentication and as such can only authenticate by a server-side authentication request.
</aside>

