---
description: >-
  Allows suppliers to respond with a quote through a web service API. This API
  call is made after receiving a quote request.
---

# Quote Response API

{% api-method method="post" host="https://bidunity.com/" path="" %}
{% api-method-summary %}
Quote Response Information
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="request\_id" type="string" required=true %}
The unique identifier of the quote request this is responding to.
{% endapi-method-parameter %}

{% api-method-parameter name="response\_type" type="string" required=true %}
What this is a response to: `quote` or `order`
{% endapi-method-parameter %}

{% api-method-parameter name="confirmation\_needed" type="boolean" required=false %}
Whether confirmation is needed by staff.
{% endapi-method-parameter %}

{% api-method-parameter name="notes" type="string" required=false %}
Any notes or exceptions to convey for the quote.
{% endapi-method-parameter %}

{% api-method-parameter name="total\_amount" type="number" required=true %}
The total amount of the quote. This should include everything, including shipping and tax, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="shipping\_cost" type="number" required=false %}
The estimated shipping cost for the materials, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="tax" type="number" required=false %}
The estimated tax for the materials, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="quoted\_by" type="object" required=false %}
The person that created the quote, if applicable. Can contain strings for `name`, `email`, and `phone`.
{% endapi-method-parameter %}

{% api-method-parameter name="delivery\_date" type="number" required=false %}
The date that the materials can be delivered. This is a timestamp in milliseconds.
{% endapi-method-parameter %}

{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

