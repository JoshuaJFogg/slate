# API Authorization

## Client-to-Server integrations


Client-to-server integrations are often the quickest to complete and allow you to get live in a matter of hours. To help this process, MPP Global has developed the eSuite SDK which is an AngularJS application that contains UI elements covering the standard flows experienced by our existing clients. If you decide you would prefer to build the eSuite API into your existing technology stack directly, this is possible. Client-to-server API requests are restricted as to what features are available and the data that can be passed. For example, configuring a price from the client-side application is not possible as it should never be accessible to the end-user to change how much they pay for an item.

In order to authenticate with the eSuite API, you will be required to pass either two or three pieces of information dependent on the actions you are looking to complete. The values required are:

### X-TokenId

This is your API Key for the eSuite API. When you are set up on the eSuite platform, you will be provided with the API Key and it will be the value used by eSuite to identify you when making requests into the platform. It is possible to have multiple API Keys configured against your instance of eSuite. The API Key is a GUID (32 character non-sequential value) and will be different in both UAT and Live environments.

`x-tokenId: BE52ADA2064C4F9A9D90F28D066D1CEE`

### Origin

As part of the API Key provisioning process, your API key will be bound to a specific Origin that reflects the location from which you will make your API requests. It is possible to bind multiple Origin domains to a single API Key, the only restriction on the domains used as Origins is that they are all HTTPS. Whilst you are getting your system set up, the API Key for the UAT environment will be bound to https://localhost so that you can begin work straight away.

`Origin: https://mywebsite-domain.com`

### X-SessionId

In the event you are performing actions relating to a customer's account, whether that be account creation, retrieval or addition of payment details; you must provide a session token for that customer in the request you make. This session token can be gained from two different places: the customer authenticating themselves using their email address and password, or a server-to-server API request on behalf of the customer. The session provided will have both a short-life permission which allows the customer to carry out actions against their account and this lasts for 15 minutes since last use, and then a long-life permission which is used for checking access to content only.

`x-sessionId: BE52ADA2064C4F9A9D90F28D066Y6RDE`


<aside class="warning">
You must replace the <code>x-tokenId</code> value with your personal API key.
</aside>


## Server-to-server Integrations

eSuite uses API keys to allow access to the API. You can register a new eSuite API key by logging into eSuite HQ.

eSuite expects the API key to be included in all API requests to the server in a header that looks like the following:

### X-ClientId

The header 'x-clientid' is used to identify who is attempting to make the request to eSuite. You will only be issued with a single clientId for eSuite and this will remain consistent between both UAT and the Live system.

`x-clientid: 1001`

### X-ClientPassword

The client password is the authorization mechanism used to determine whether the requester has permissions to execute the API method in question. It is possible to have multiple API payments against your client but these will differ between both UAT and the Live system due to the UAT system not being a PCI compliant environment. 

The client password should never be revealed in the public domain nor should it be written on a physical item e.g paper. When moving to the Live system, MPP Globals Client Onboarding team will provide a designated member of your organisation the client password over the phone.

`x-clientpassword: Str0ngP@ssword`

<aside class="warning">
The <code>x-clientId</code> should never be revealed in the public domain, nor be accessible to general members of the team.
</aside>

<aside class="warning">
If you choose to integrate the eSuite API directly into your technology stack please be aware that in the event you are processing, storing or transmitting card data, your entire application will be in scope for PCI Level one compliance.
</aside>

## Versions
The eSuite API operates a semantic version policy which is denoted using MAJOR.MINOR.PATCH (10.0.0). The x-version header is a Required parameter on *all* API requests.

If MPP Global makes a change to the eSuite API that could result in an existing integration no longer functioning correctly, a new major version will be released, resulting in incrementing the Major version of the API. For example, a non-backwards compatible change to the API would be the change the results in responses being returned as XML rather than JSON. This would see a version 9.12.3 being the final version 9 release and a breaking change being released on version 10.0.0.

As part of the development of the eSuite platform, new features are released every two weeks. The introduction of new features that do not cause breaking changes will be added to the current major version of the API and a minor release. For example, this would be version 9.1.3 providing the ability to create a customer account on the eSuite platform. As part of the next release of the eSuite platform you are able to retrieve customer accounts via the eSuite API but this would be added to a new minor version and be available on version 9.2.0.

From time to time bugs will be discovered with the eSuite API and we will fix them as soon as technically possible. When a fix is deployed to an existing piece of functionality that does not change the details of the API from an integration level, a patch version would be released taking a version from 9.2.3 to version 9.2.4.

The current policy on version support for the eSuite API, MPP Global will continue to support all versions that are currently in use by clients. Once all clients have moved to a later version of the API, an end-of-life (eoL) process will begin.
