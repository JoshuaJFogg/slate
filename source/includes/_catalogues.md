# Catalogues

## Retrieve All Subscriptions

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

`GET http://uat.mppglobal.com/api/subscriptions`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
subscriptionsInfo | array[object] | Optional | Subscriptions info
subscriptionsInfo > subscriptionId | string | Optional | Subscription id
subscriptionsInfo > resourceReference | string | Optional | Resource reference
subscriptionsInfo > subscriptionGroup | string | Optional | Subscription group
subscriptionsInfo > subscriptionGroupTag | string | Optional | Subscription group tag
subscriptionsInfo > subscriptionGroupStatus | string | Optional | Subscription group status
subscriptionsInfo > subscriptionDescription | string | Optional | Subscription description
subscriptionsInfo > subscriptionTitle | string | Optional | Subscription title
subscriptionsInfo > subscriptionType | string | Optional | Subscription type
subscriptionsInfo > subscriptionStatus | string | Optional | Subscription status
subscriptionsInfo > initialPricingEnabled | boolean | Optional | Initial pricing enabled
subscriptionsInfo > trialInfo | object | Optional | Trial info
subscriptionsInfo > trialInfo > trialEnabled | boolean | Optional | Trial enabled
subscriptionsInfo > trialInfo > trialUnit | string | Optional | Trial unit
subscriptionsInfo > trialInfo > trialPeriod | integer | Optional | Trial period
subscriptionsInfo > trialInfo > discountPercentage | number | Optional | Discount percentage
subscriptionsInfo > trialInfo > nonPaymentTrial | boolean | Optional | Non payment trial
subscriptionsInfo > contractInfo | object | Optional | Contract info
subscriptionsInfo > contractInfo > contractUnit | string | Optional | Contract Unit
subscriptionsInfo > contractInfo > contractPeriod | integer | Optional | Contract period
subscriptionsInfo > contractInfo > autoRenewDefault | string | Optional | Auto renew default
subscriptionsInfo > pricingInfo | array[object] | Optional | The collection of all prices configured for the subscription service
subscriptionsInfo > pricingInfo > currency | string | Optional | The currency the price is associated to
subscriptionsInfo > pricingInfo > initialPrice | number | Optional | The price that will be paid on sign-up of the subscription service
subscriptionsInfo > pricingInfo > priceIsGross | boolean | Optional | An indication as to whether the price returned is the gross or net price
subscriptionsInfo > pricingInfo > renewalPrice | number | Optional | The price that will be paid on subsequent renewal purchases
subscriptionsInfo > pricingInfo > priceId | integer | Optional | The eSuite Identifer for the price
subscriptionsInfo > pricingInfo > taxCategory | string | Optional | Tax category
subscriptionsInfo > pricingInfo > resourceReference | string | Optional | The identifier for the price that should be used on purchase calls
subscriptionsInfo > pricingInfo > paymentMethod | string | Optional | The payment method associated to the specific price
subscriptionsInfo > allowedPaymentMethods | array[string] | Optional | The collection of payment methods available on the subscription service
subscriptionsInfo > customParameters | array[object] | Optional | Custom parameters
subscriptionsInfo > customParameters > parameterName | string | Optional | Name of the custom parameter
subscriptionsInfo > customParameters > parameterType | string | Optional | An indication as to what data type the parameter should be displayed e.g. HTML, Decimal
subscriptionsInfo > customParameters > parameterValue | string | Optional | Value of the custom parameter
subscriptionsInfo > images | array[object] | Optional | The overarching object which contains all images for the subscription service
subscriptionsInfo > images > imageId | integer | Optional | The eSuite identifier for the image
subscriptionsInfo > images > displayName | string | Optional | Display name
subscriptionsInfo > images > fileName | string | Optional | The file name associated to the image
subscriptionsInfo > images > default | boolean | Optional | An indication as to whether the image is the default image for the subscription service 
subscriptionsInfo > images > location | string | Optional | The URL location the image is hosted at
subscriptionsInfo > groupLicensing | object | Optional | A breakdown of how many group licenses are associated to the subscription service
subscriptionsInfo > groupLicensing > standard | integer | Optional | The number of standard licenses associated to the subscription service
subscriptionsInfo > groupLicensing > overflow | integer | Optional | The number of overflow licenses associated to the subscription service


## Retrieve Filtered Subscriptions

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

`GET http://uat.mppglobal.com/api/subscriptions/search`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
subscriptionsInfo | array[object] | Optional | Subscriptions info
subscriptionsInfo > subscriptionId | string | Optional | Subscription id
subscriptionsInfo > resourceReference | string | Optional | Resource reference
subscriptionsInfo > subscriptionGroup | string | Optional | Subscription group
subscriptionsInfo > subscriptionGroupTag | string | Optional | Subscription group tag
subscriptionsInfo > subscriptionGroupStatus | string | Optional | Subscription group status
subscriptionsInfo > subscriptionDescription | string | Optional | Subscription description
subscriptionsInfo > subscriptionTitle | string | Optional | Subscription title
subscriptionsInfo > subscriptionType | string | Optional | Subscription type
subscriptionsInfo > subscriptionStatus | string | Optional | Subscription status
subscriptionsInfo > initialPricingEnabled | boolean | Optional | Initial pricing enabled
subscriptionsInfo > trialInfo | object | Optional | Trial info
subscriptionsInfo > trialInfo > trialEnabled | boolean | Optional | Trial enabled
subscriptionsInfo > trialInfo > trialUnit | string | Optional | Trial unit
subscriptionsInfo > trialInfo > trialPeriod | integer | Optional | Trial period
subscriptionsInfo > trialInfo > discountPercentage | number | Optional | Discount percentage
subscriptionsInfo > trialInfo > nonPaymentTrial | boolean | Optional | Non payment trial
subscriptionsInfo > contractInfo | object | Optional | Contract info
subscriptionsInfo > contractInfo > contractUnit | string | Optional | Contract Unit
subscriptionsInfo > contractInfo > contractPeriod | integer | Optional | Contract period
subscriptionsInfo > contractInfo > autoRenewDefault | string | Optional | Auto renew default
subscriptionsInfo > pricingInfo | array[object] | Optional | Subscription pricing
subscriptionsInfo > pricingInfo > currency | string | Optional | Currency
subscriptionsInfo > pricingInfo > initialPrice | number | Optional | Initial price
subscriptionsInfo > pricingInfo > priceIsGross | boolean | Optional | Price is gross
subscriptionsInfo > pricingInfo > renewalPrice | number | Optional | Renewal price
subscriptionsInfo > pricingInfo > priceId | integer | Optional | Price id
subscriptionsInfo > pricingInfo > taxCategory | string | Optional | Tax category
subscriptionsInfo > pricingInfo > resourceReference | string | Optional | Resource reference
subscriptionsInfo > pricingInfo > paymentMethod | string | Optional | Payment Method
subscriptionsInfo > allowedPaymentMethods | array[string] | Optional | Alowed payment methods
subscriptionsInfo > customParameters | array[object] | Optional | Custom parameters
subscriptionsInfo > customParameters > parameterName | string | Optional | Name of the custom parameter
subscriptionsInfo > customParameters > parameterType | string | Optional | Parameter type
subscriptionsInfo > customParameters > parameterValue | string | Optional | Value of the custom parameter
subscriptionsInfo > images | array[object] | Optional | Images
subscriptionsInfo > images > imageId | integer | Optional | Image identifier
subscriptionsInfo > images > displayName | string | Optional | Display name
subscriptionsInfo > images > fileName | string | Optional | File name
subscriptionsInfo > images > default | boolean | Optional | Specify if image is default
subscriptionsInfo > images > location | string | Optional | Path to the image
subscriptionsInfo > groupLicensing | object | Optional | Group licensing
subscriptionsInfo > groupLicensing > standard | integer | Optional | Standard
subscriptionsInfo > groupLicensing > overflow | integer | Optional | Overflow







## Retrieve All Products

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

`GET http://uat.mppglobal.com/api/products`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
products | array[object] | Optional | List of products
products > productId | integer | Optional | Product identifier
products > status | string | Optional | Product status
products > title | string | Optional | Title
products > description | string | Optional | Description
products > pricing | array[object] | Optional | Pricing
products > pricing > currency | string | Optional | IsoCode
products > pricing > purchaseInfo | array[object] | Optional | Purchase info
products > pricing > purchaseInfo > paymentMethod | array[object] | Optional | Payment method
products > pricing > purchaseInfo > paymentMethod > grossAmount | number | Optional | Gross amount
products > pricing > purchaseInfo > paymentMethod > paymentMethod | string | Optional | Payment method
products > pricing > purchaseInfo > paymentMethod > priceId | string | Optional | Price id
products > pricing > purchaseInfo > paymentMethod > resourceReference | string | Optional | Resource Reference for the PriceId
products > pricing > purchaseInfo > roleInfo | object | Optional | Pricing role
products > pricing > purchaseInfo > roleInfo > roleId | string | Optional | Role identifier
products > pricing > purchaseInfo > roleInfo > clientRef | string | Optional | Client reference
products > pricing > purchaseInfo > roleInfo > title | string | Optional | Title
products > images | array[object] | Optional | Images of the product
products > images > imageId | integer | Optional | Image identifier
products > images > displayName | string | Optional | Display name
products > images > fileName | string | Optional | File name
products > images > default | boolean | Optional | Specify if image is default
products > images > location | string | Optional | Path to the image
products > supplier | object | Optional | Suplier details
products > supplier > suppliedId | integer | Optional | Suplier identifier
products > supplier > name | string | Optional | Name
products > type | object | Optional | Product type
products > type > typeId | integer | Optional | Type id
products > type > name | string | Optional | Type name
products > customParameters | array[object] | Optional | Custom parameters
products > customParameters > parameterName | string | Optional | Name of the custom parameter
products > customParameters > parameterValue | string | Optional | Value of the custom parameter
products > resourceReference | string | Optional | Resource Reference for the ProductId







## Retrieve Filtered Products

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

`GET http://uat.mppglobal.com/api/products/search`

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
products | array[object] | Optional | List of products
products > productId | integer | Optional | Product identifier
products > status | string | Optional | Product status
products > title | string | Optional | Title
products > description | string | Optional | Description
products > pricing | array[object] | Optional | Pricing
products > pricing > currency | string | Optional | IsoCode
products > pricing > purchaseInfo | array[object] | Optional | Purchase info
products > pricing > purchaseInfo > paymentMethod | array[object] | Optional | Payment method
products > pricing > purchaseInfo > paymentMethod > grossAmount | number | Optional | Gross amount
products > pricing > purchaseInfo > paymentMethod > paymentMethod | string | Optional | Payment method
products > pricing > purchaseInfo > paymentMethod > priceId | string | Optional | Price id
products > pricing > purchaseInfo > paymentMethod > resourceReference | string | Optional | Resource Reference for the PriceId
products > pricing > purchaseInfo > roleInfo | object | Optional | Pricing role
products > pricing > purchaseInfo > roleInfo > roleId | string | Optional | Role identifier
products > pricing > purchaseInfo > roleInfo > clientRef | string | Optional | Client reference
products > pricing > purchaseInfo > roleInfo > title | string | Optional | Title
products > images | array[object] | Optional | Images of the product
products > images > imageId | integer | Optional | Image identifier
products > images > displayName | string | Optional | Display name
products > images > fileName | string | Optional | File name
products > images > default | boolean | Optional | Specify if image is default
products > images > location | string | Optional | Path to the image
products > supplier | object | Optional | Suplier details
products > supplier > suppliedId | integer | Optional | Suplier identifier
products > supplier > name | string | Optional | Name
products > type | object | Optional | Product type
products > type > typeId | integer | Optional | Type id
products > type > name | string | Optional | Type name
products > customParameters | array[object] | Optional | Custom parameters
products > customParameters > parameterName | string | Optional | Name of the custom parameter
products > customParameters > parameterValue | string | Optional | Value of the custom parameter
products > resourceReference | string | Optional | Resource Reference for the ProductId





