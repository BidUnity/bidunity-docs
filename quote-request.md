---
description: >-
  Allows suppliers to directly receive quote requests and respond without any
  human interaction.
---

# Quote Request

BidUnity can send a quote request to a supplier through a RESTful web service. The supplier must have an endpoint setup to receive the request.

{% api-method method="post" host="https://your-supplier-site.com" path="/v1/quote/request" %}
{% api-method-summary %}
Send Quote Request
{% endapi-method-summary %}

{% api-method-description %}
BidUnity will make a POST request to the supplier's endpoint when a user starts a quote request from within BidUnity.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="request\_id" type="string" required=true %}
A random, unique id for the quote. This must be sent back to BidUnity when responding with the quote.
{% endapi-method-parameter %}

{% api-method-parameter type="string" name="request\_type" required=true %}
The type of request being made. For quote requests this will be `quote`. Orders will be `order`.
{% endapi-method-parameter %}

{% api-method-parameter name="company\_id" type="string" required=true %}
The id of the company making the request.
{% endapi-method-parameter %}

{% api-method-parameter name="company\_name" type="string" required=true %}
The name of the company making the request.
{% endapi-method-parameter %}

{% api-method-parameter name="deliver\_to" type="object" required=true %}
The address of where the materials should be delivered. This will include the following string fields: `line1`, `line2`, `city`, `state`, `zip`, `country`
{% endapi-method-parameter %}

{% api-method-parameter name="project\_id" type="string" required=true %}
The id of the project.
{% endapi-method-parameter %}

{% api-method-parameter name="project\_name" type="string" required=true %}
The name of the project.
{% endapi-method-parameter %}

{% api-method-parameter name="proposal\_id" type="string" required=true %}
The id of the proposal within the project.
{% endapi-method-parameter %}

{% api-method-parameter name="proposal\_name" type="string" required=true %}
The name of the proposal.
{% endapi-method-parameter %}

{% api-method-parameter name="parts" type="array" required=false %}
Contains an array of Part objects to be quoted. This can be an empty array. See the Part object for the structure of each object.
{% endapi-method-parameter %}

{% api-method-parameter name="doors" type="array" required=false %}
Contains an array of Door objects to be quoted. This can be an empty array. See the Door object for the structure of each object.
{% endapi-method-parameter %}

{% api-method-parameter name="total\_cost" type="number" required=true %}
The total cost that BidUnity calculated for all parts and doors in the quote request. Note this is provided for information purposes only and may differ from the actual amount quoted.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{    "name": "Cake's name",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



### The part object



