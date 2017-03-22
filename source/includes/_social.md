# Social Providers (SSO)

## Authenticate via Facebook

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json
{
  
}
```


### URL End-point

`POST https://uat.mppglobal.com/api/accounts/authenticate/external-providers/facebook`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
facebookRedirectURI | string | Yes | |
authorisationCode | string | No | |
accessToken | string | No | |
applicationIdentifier | string | Yes | |


## Link eSuite accounts to Facebook

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json
{
  
}
```


### URL End-point

`POST https://uat.mppglobal.com/api/accounts/link/external-providers/facebook`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
facebookRedirectURI | string | Yes | |
authorisationCode | string | No | |
accessToken | string | No | |
applicationIdentifier | string | Yes | |

## Authenticate via Janrain

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json
{

}
```


### URL End-point

`POST https://uat.mppglobal.com/api/accounts/authenticate/external-providers/janrain`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
accessToken | string | Yes | |

## Link eSuite accounts to Janrain 

```shell

```

```csharp

```

```java

```

> The above command returns JSON structured like this:

```json
{
  
}
```

### URL End-point

`POST https://uat.mppglobal.com/api/accounts/link/external-providers/janrain`

### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
accessToken | string | Yes | |




