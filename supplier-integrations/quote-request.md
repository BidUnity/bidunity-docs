---
description: >-
  Allows suppliers to directly receive quote requests and respond without any
  human interaction.
---

# Quote Request API

BidUnity can send a quote request to a supplier through a RESTful web service. The supplier must have an endpoint setup to receive the request.

{% api-method method="post" host="https://your-supplier-site.com" path="/v1/quote/request" %}
{% api-method-summary %}
Send Quote Request
{% endapi-method-summary %}

{% api-method-description %}
BidUnity will make a POST request to the supplier's endpoint when a user starts a quote request from within BidUnity. The supplier has full control over what the URL is to that endpoint; it must be configured by BidUnity support.
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
    "parts": [PartObject],
    "doors": [DoorObject],
    "total_cost": 3820.48
}
```

### The part object

The Part object can represent many different types of items, such as items purchased individually, in a box, as a stock length, area, or volume. But no matter how the part is purchased, it has the same JSON object structure.

Some definitions before we get started:

* **Package** is the thing that is being purchased.
* A package can contain a **single item** or a **group of items**.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Field Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>id</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">BidUnity&apos;s unique id for the part.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>name</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The name of the part.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>part_number</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The supplier&apos;s part number.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>finish_type</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The metal finish for the part, or null if not applicable. See Finish Types
        (TODO link)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>finish_color</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The finish color for the part, or null if not applicable. See Finish Colors
        (TODO link)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>finish_multiplier</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">A value to multiply against the configured finish price to calculate the
        cost for the part. This defaults to 1.0 but can be modified by users when
        creating the proposal.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>total_cost</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">The total cost for the part, including all quantities of the part being
        ordered.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>package_unit_cost</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">The cost for a single quantity of the part. The unit cost multiplied by
        the package quantity to order will equal the total cost for the part.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>package_quantity_to_order</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>The quantity of the package being ordered.</p>
        <p>item_measurement_type - Describes what is being ordered.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>item_measurement_type</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>Describes what is being ordered. Possible values:</p>
        <p><code>each</code>, <code>box</code>, <code>stock_length</code>, <code>block_area</code>, <code>container</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>items_per_package</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>The number of items contained in each package. This will be 1 for items
          purchased individually.</p>
        <p>Examples:</p>
        <ul>
          <li>If purchasing a box of 4 stock lengths then the value would be 4.</li>
          <li>If purchasing a box of 200 screws then the value would be 200.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>item_stock_size</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>The stock size for the item. The units of measure depend on the measurement
          type:</p>
        <ul>
          <li>For <code>each </code> this will be 1.</li>
          <li>For <code>box</code> this will be equal to <code>items_per_package</code>.</li>
          <li>For <code>stock_length</code> this may be 288 inches.</li>
          <li>For <code>block_area</code> this will be 1 square foot.</li>
          <li>For <code>container</code> this may be 500 milliliters.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>item_size_unit_of_measure</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The units of measure for the item_stock_size. Possible values: <code>item</code>, <code>in</code> (inches), <code>sqft</code> (square
        feet), <code>ml</code> (milliliters)</td>
    </tr>
  </tbody>
</table>

