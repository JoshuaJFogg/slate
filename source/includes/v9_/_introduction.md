# Introduction

The eSuite API is built around the architectural principle of REST (Representational State Transfer)..

The API allows you to interact with eSuite from both a client-side web application and a traditional server-side application. The API also uses standard HTTP features and can be used via standard HTTP clients in order to perform actions prior to integrating the functionality. All responses are returned in JSON, including error messages. 

In order ensure the eSuite REST API is secure, certain features are not available to client-side web applications but the functions that are made availalbe will allow you to build an application to take card payments without having to have it hosted with a third party or use a hosted white label solution.

The API has also been built using the OpenAPI Specification (formally the Swagger Specification) which will allow you to automatically generate code. Please be aware that although Swagger is provided to speed up the rate of development, it may contain documentation issues that will be resolved in a later release of the API.

You can generate your bindings against our UAT swagger [here](https://uat.mppglobal.com:443/swagger/docs/9).

<aside class="info">Please be aware the all dates and times returned via the API are presented in UTC and do not take into account your local time zone.</aside>