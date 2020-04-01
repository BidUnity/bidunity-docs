---
description: >-
  Allows suppliers to respond with a quote through a web service API. This API
  call is made after receiving a quote request.
---

# Quote Response API

{% api-method method="post" host="https://api.bidunity.com" path="/v1/quote/response" %}
{% api-method-summary %}
Quote Response Information
{% endapi-method-summary %}

{% api-method-description %}
Sends a quote response to BidUnity for a particular quote request. A PDF file of the quote may also be included. The `Content-Type` of this request must be `multipart/form-data` in order to accept a file.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}
multipart/form-data
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="request\_id" type="string" required=true %}
The unique identifier of the quote request this is responding to.
{% endapi-method-parameter %}

{% api-method-parameter name="request\_type" type="string" required=true %}
What this is in response to: `quote`
{% endapi-method-parameter %}

{% api-method-parameter name="needs\_confirmation" type="boolean" required=false %}
Whether confirmation is needed by staff.
{% endapi-method-parameter %}

{% api-method-parameter name="notes" type="string" required=false %}
Any notes or exceptions to convey for the quote.
{% endapi-method-parameter %}

{% api-method-parameter name="total\_amount" type="number" required=false %}
The total amount of the quote. This should include everything, including tax and shipping, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="tax" type="number" required=false %}
The estimated tax for the materials, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="shipping\_cost" type="number" required=false %}
The estimated shipping cost for the materials, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="delivery\_date" type="number" required=false %}
The estimated date that the materials could be delivered. This is a timestamp in milliseconds.
{% endapi-method-parameter %}

{% api-method-parameter name="quoted\_by" type="string" required=false %}
Name of the person that created the quote, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="contact\_name" type="string" required=false %}
The name of the person to contact with questions.
{% endapi-method-parameter %}

{% api-method-parameter name="contact\_email" type="string" required=false %}
The email address for the point of contact.
{% endapi-method-parameter %}

{% api-method-parameter name="contact\_phone" type="string" required=false %}
The phone number for the point of contact.
{% endapi-method-parameter %}

{% api-method-parameter name="file" type="string" required=false %}
The PDF file of the quote.
{% endapi-method-parameter %}

{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}

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

{% api-method-parameter name="contact\_name" type="string" required=false %}
The name of the person to contact with questions.
{% endapi-method-parameter %}

{% api-method-parameter name="contact\_email" type="string" required=false %}
The email address for the point of contact.
{% endapi-method-parameter %}

{% api-method-parameter name="contact\_phone" type="string" required=false %}
The phone number for the point of contact.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Quote successfully received by BidUnity.
{% endapi-method-response-example-description %}

```
{ }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
A problem occurred 
{% endapi-method-response-example-description %}

```
{ "error": "Description of the error that occurred." }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

