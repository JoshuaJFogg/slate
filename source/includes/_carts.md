# Carts

## Create a Cart

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript

```

> The above command returns JSON structured like this:

```json

```

In order to add items to a cart, the cart must first be created by executing a request to this endpoint.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts</span>
</div>

## Retrieve a Cart

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript

```

> The above command returns JSON structured like this:

```json

```

This endpoint allows the retrieval of a specific cart that has been created on the eSuite platform.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartIdentifier}</span>
</div>

### Response Parameters

Parameter | Type |  Description | 
--------- | ------- | ----------- |
`cartItems` | array[object] | The list of cart Items
`cartItems` > `lineItemId` | integer | Line Item Id
`cartItems` > `itemDescription` | string | Description of the Line Item
`cartItems` > `pricing` | object | Pricing
`pricing` > `grossAmount` | number |  Gross Amount
`pricing` > `netAmount` | number | Net Amount
`pricing` > `taxAmount` | number | Tax Amount
`pricing` > `currency` | string | Currency
`cartItems` > `quantity` | integer | Quantity of items
`cartItems` > `productInfo` | object | Collection of Product information| 
`productInfo > productId` | integer | List of cart item detail parameters
`cartItems` > `customLineItemParameters` | array[object] | List of cart item detail parameters
`customLineItemParameters` > `parameterName` | string | Name of the custom parameter
`customLineItemParameters` > `parameterValue` | string | Value of the custom parameter
`cartItems` > `lineItemReference` | string | Line Item Reference

## Update a Cart

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript

```

> The above command returns JSON structured like this:

```json

```

An existing cart can be edited by calling the following endpoint. An example where this is required is when associating a cart to a specific eSuite account.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">PATCH</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartResourceReference}</span>
</div>




## Delete a Cart

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript

```

> The above command returns JSON structured like this:

```json

```

In order to remove a cart from the eSuite, this endpoint must be called. If the cart is associated to an previous payment, it is deemed immutable and cannot be removed.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartResourceReference}</span>
</div>



## Create a Line-item

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript

```

> The above command returns JSON structured like this:

```json

```

In order to add a new item to a cart, this endpoint should be called. This endpoint will allow the addition of single line items, not bulk.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-post">POST</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartReference}/line-items</span>
</div>


### POST Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
explicitPricedItem | object | No | Explicit Priced Item
explicitPricedItem > description | string | No | Description
explicitPricedItem > pricing | object | No | Pricing
explicitPricedItem > pricing > grossAmount | number | No | Gross Amount
explicitPricedItem > pricing > netAmount | number | No | Net Amount
explicitPricedItem > pricing > taxAmount | number | No | Tax Amount
explicitPricedItem > pricing > currency | string | No | Currency
explicitPricedItem > quantity | integer | No | Quantity
explicitPricedItem > productId | integer | No | Product Id
explicitPricedItem > customLineItemParameters | array[object] | No | Custom Parameters
preconfiguredItem | object | No | Preconfigured Item
preconfiguredItem > description | string | No | Description
preconfiguredItem > productPriceId | integer | No | Product Price Id
preconfiguredItem > quantity | integer | No | Quantity
preconfiguredItem > customLineItemParameters | array[object] | No | Custom Line Item Parameters

## Delete a Line-item

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript

```

> The above command returns JSON structured like this:

```json

```

Calling this endpoint will allow you to remove an item from a cart. It will not be possible to remove an line-item from a cart has is deemed immutable due to being involved in a purchase. 

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-delete">DELETE</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/carts/{cartResourceReference}/line-items/{lineItemReference}</span>
</div>



















## Retrieve an Account's Cart

```shell

```

```csharp

```

```java

```

```ruby

```

```python

```

```javascript

```

> The above command returns JSON structured like this:

```json

```

Calling this endpoint will allow for the retrieval of all carts associated to an account. The response will include those associated to a payment instruction and those which are still pending completion.

### HTTP Request

<div class="endpoint-cont">
<span class="endpoint-verb endpoint-verb-get">GET</span>
<span class="endpoint-path">https://uat.mppglobal.com/api/accounts/{accountId}/carts/{cartIdentifier}</span>
</div>

### Response Parameters

Parameter | Type | Mandatory | Description | 
--------- | ------- | ------- | ----------- |
cartItems | array[object] | No | The list of cart Items
cartItems > lineItemId | integer | No | Line Item Id
cartItems > itemDescription | string | No | Description of the Line Item
cartItems > pricing | object | No | Pricing
cartItems > pricing > grossAmount | number | No | Gross Amount
cartItems > pricing > netAmount | number | No | Net Amount
cartItems > pricing > taxAmount | number | No | Tax Amount
cartItems > pricing > currency | string | No | Currency
cartItems > quantity | integer | No | Quantity of items
cartItems > productInfo | object | No | 
cartItems > productInfo > productId | integer | No | List of cart item detail parameters
cartItems > customLineItemParameters | array[object] | No | List of cart item detail parameters
cartItems > customLineItemParameters > parameterName | string | No | Name of the custom parameter
cartItems > customLineItemParameters > parameterValue | string | No | Value of the custom parameter
cartItems > lineItemReference | string | No | Line Item Reference












