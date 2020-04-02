---
description: >-
  Allows suppliers to respond with a quote through a web service API. This API
  call is made after receiving a quote request.
---

# Quote Response

{% api-method method="post" host="https://bidunity.com/supplier/api" path="/v1/quote/response" %}
{% api-method-summary %}
Quote Response Information
{% endapi-method-summary %}

{% api-method-description %}
Sends a quote to BidUnity in response to a quote request.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="request\_id" type="string" required=true %}
The unique identifier of the quote request this is responding to.
{% endapi-method-parameter %}

{% api-method-parameter name="total\_amount" type="number" required=true %}
The total amount of the quote, inclusive of everything including tax and shipping, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="tax" type="number" required=false %}
The estimated tax for the materials, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="shipping" type="number" required=false %}
The estimated shipping for the materials, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="notes" type="string" required=false %}
Any notes or exceptions to convey for the quote.
{% endapi-method-parameter %}

{% api-method-parameter name="needs\_confirmation" type="boolean" required=false %}
Whether confirmation is needed by staff.total\_
{% endapi-method-parameter %}

{% api-method-parameter name="delivery\_date" type="number" required=false %}
The estimated date that the materials could be delivered. This is a timestamp in milliseconds.
{% endapi-method-parameter %}

{% api-method-parameter name="quoted\_by" type="string" required=false %}
Name of the person that created the quote, if applicable.
{% endapi-method-parameter %}

{% api-method-parameter name="contact\_name" type="string" required=false %}
Name of the person to contact with questions.
{% endapi-method-parameter %}

{% api-method-parameter name="contact\_email" type="string" required=false %}
Email address for the point of contact.
{% endapi-method-parameter %}

{% api-method-parameter name="contact\_phone" type="string" required=false %}
Phone number for the point of contact.
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

```bash
curl https://api.bidunity.com/v1/quote/response \
  -u your_api_key: \
  -d request_id="@/path/to/a/file.pdf" \
  -d total_amount=5683.75
  -d tax=358.75
  -d shipping=200
  -d notes="This is our best offer!"
  -d delivery_date=1585761463
  -d quoted_by="John Doe"
```

