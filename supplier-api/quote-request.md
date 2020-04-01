---
description: >-
  Allows suppliers to directly receive quote requests and respond without any
  human interaction.
---

# Quote Request API

## Overview

BidUnity can send a quote request to a supplier through a RESTful web service. The supplier must have an endpoint setup to receive the request.

{% api-method method="post" host="https://your-supplier-site.com" path="/v1/quote/request" %}
{% api-method-summary %}
Send Quote Request to Supplier
{% endapi-method-summary %}

{% api-method-description %}
BidUnity will make a POST request to the supplier's endpoint when a user starts a quote request from within BidUnity. The supplier has full control over what the URL is to that endpoint; it must be configured by BidUnity support.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="request\_id" type="string" required=true %}
A random, unique identifier for the quote. This must be sent back to BidUnity when responding with the quote.
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
Quote request successfully received by supplier.
{% endapi-method-response-example-description %}

```
{ }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
If an error occurs, include a description of the error with the response.
{% endapi-method-response-example-description %}

```
{ "error": "Description of the error that occurred." }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Example quote request body

```yaml
{
    "request_id": “d770d1d3-72f6-48b7-b24b-fea1c8a2da77”,
    "request_type": “quote”,
    "company_id": “5cd2410d2482a6002148aa38”,
    "company_name": “The Company Name”,
    "deliver_to": {
        "line1": “4822 Somewhere Street”,
        "line2": null,
        "city": “New York”,
        "state": “NY”,
        "zip": 48230,
        "country": “USA”,
    },
    "project_id": “5db1bd412c3017002170ebb6”,
    "project_name": “The Project Name”,
    "proposal_id": “5e383f71e8c7250026e29f80”,
    "proposal_name": “The Proposal Name”,
    "parts": [{
        id: “407f191e810c19729de860ec”,
        name: “Trulite 3101 Head/Sill/Jamb”,
        part_number: “3101”,
        finish_type: “Class 1 Anodized”,
        finish_color: “Dark Bronze”,
        finish_multiplier: 1.0,
        total_cost: 100.00,
        package_unit_cost: 20.00,
        package_quantity_to_order: 5,
        item_measurement_type: “stock_length”,
        items_per_package: 1,   # Lengths sold individually
        item_stock_size: 288,   # 288” stock lengths
        item_size_unit_of_measure: “in”,  // Inches
        sizes: [{
            component: “Head”,
            length: 29.125   # inches
        },{
            component: “Sill”,
            length: 29.125   # inches
        }]
    }],
    "doors": [DoorObject],
    "total_cost": 3820.48
}
```

