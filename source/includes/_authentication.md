# API Authorization

## Client-to-Server integrations

> To authorize, use this code:

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/ \
  --header 'content-type: application/json' \
  --header 'x-tokenId: BE52ADA2064C4F9A9D90F28D066D1CEE' \
  --header 'x-sessionId: BE52ADA2064C4F9A9D90F28D066D1RFT' \
  --header 'x-version: 9.0.0' \
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-sessionId", "BE52ADA2064C4F9A9D90F28D066D1RFT");
request.AddHeader("x-tokenId", "BE52ADA2064C4F9A9D90F28D066D1CEE");

```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/")
  .header("x-tokenId", "BE52ADA2064C4F9A9D90F28D066D1CEE")
  .header("x-sessionId", "BE52ADA2064C4F9A9D90F28D066D1RFT")
  .header("x-version", "9.0.0")
  .asString();
```


> Make sure to replace `BE52ADA2064C4F9A9D90F28D066D1CEE` with your API key.

eSuite uses API keys to allow access to the API. You can register a new eSuite API key by logging into eSuite HQ.

eSuite expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-tokenId: BE52ADA2064C4F9A9D90F28D066D1CEE`

`x-sessionId: BE52ADA2064C4F9A9D90F28D066D1CEE`

`Origin: https://mywebsite-domain.com`

<aside class="warning">
You must replace the <code>x-tokenId</code> value with your personal API key.
</aside>

## Server-to-server Integrations

> To authorize, use this code:

```shell
curl --request POST \
  --url https://uat.mppglobal.com/api/ \
  --header 'content-type: application/json' \
  --header 'x-clientId: 1001' \
  --header 'x-clientPassword: Str0ngP@ssword' \
  --header 'x-version: 9.0.0' \
```

```csharp
var client = new RestClient("https://uat.mppglobal.com/api/");
var request = new RestRequest(Method.POST);
request.AddHeader("x-version", "9.0.0");
request.AddHeader("x-clientId", "1001");
request.AddHeader("x-clientPassword", "Str0ngP@ssword");
```

```java
HttpResponse<String> response = Unirest.post("https://uat.mppglobal.com/api/")
  .header("x-clientId", "1001")
  .header("x-clientPassword", "Str0ngP@ssword")
  .header("x-version", "9.0.0")
  .asString();
```


> Make sure to replace `BE52ADA2064C4F9A9D90F28D066D1CEE` with your API key.

eSuite uses API keys to allow access to the API. You can register a new eSuite API key by logging into eSuite HQ.

eSuite expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-clientid: 1001`

`x-clientpassword: Str0ngP@ssword`

<aside class="warning">
The <code>x-clientId</code> should never be revealed in the public domain nor be accessible to general members of the team.
</aside>

## Versioning
The eSuite API operates a semantic versioning policy which is denoted using MAJOR.MINOR.PATCH (9.0.0). The x-version header is a mandatory parameter on *all* API requests.

If MPP Global makes a change to the eSuite API that could result in an existing intgration no longer functioning correct, a new major version will be release and thus incrementing the Major version of the API. An example of a non-backwards compatible change to the API would be the change the results in responses being returned as XML rather than JSON. This would see a version 9.12.3 being the final version 9 release and a breaking change being released on version 10.0.0.

As part of the development of the eSuite platform, new features are released every two weeks. The introduction of new features that do not cause breaking changes will be added to the current major version of the API and a minor release. An example of when this type of change would take place would be version 9.1.3 providing the ability to create a customer account on the eSuite platform. As part of the next release of the eSuite platform you are able to retrieve customer accounts via the eSuite API but this would be added to a new minor version and be available on version 9.2.0.

From time to time bugs will be discovered with the eSuite API and we will fix them as soon as technically possible. When a fix is deployed to an existing piece of functionality that does not change the details of the API from an integration level, a patch version would be released taking a version from 9.2.3 to version 9.2.4.

The current policy on version support for the eSuite API, MPP Global will continue to support all versions that are currently in use by clients. Once all clients have moved to a later version of the API, an end-of-life (eoL) process will begin.