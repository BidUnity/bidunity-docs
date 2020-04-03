---
description: >-
  Provides a set of web services for suppliers to integrate with to automate
  quote requests.
---

# API Overview

The BidUnity Supplier API is a set of web services that allow quote requests to be sent directly to suppliers and processed automatically, potentially without any human interaction. 

Suppliers must implement a REST endpoint to receive quote requests with full parts lists and door configurations, and make a web service call to respond with the quote itself.

The API will be expanded to include orders in the future. As new features are added, new verions of the API will become available.

## Technical Overview

The BidUnity Supplier API is a set of web services based on [REST](https://en.wikipedia.org/wiki/Representational_state_transfer). The API accepts [JSON-encoded](https://www.json.org) request bodies and returns JSON-encoded response bodies.

{% tabs %}
{% tab title="BASE URL" %}
```text
https://bidunity.com/supplier/api
```
{% endtab %}
{% endtabs %}

## Authentication

The Supplier API uses API keys to authenticate requests. Suppliers must contact [support@bidunity.com](mailto:support@bidunity.com) to request an API key.

Authentication is performed using [HTTP Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). Provide your API key as the basic auth username without providing a password.

All API requests must be made over HTTPS and include your API key for authentication.

## Webhook Endpoints

Webhooks are part of the supplier API in which BidUnity notifies the supplier of events, such as when a quote request is made to them. In this case, BidUnity will make a request to the supplier at a URL of their choosing with the contents of the quote request. Suppliers must contact [support@bidunity.com](mailto:support@bidunity.com) to configure their endpoints.

### Verifying Webhooks

When BidUnity makes a request to your webhook endpoints, it will include an HTTP header `BidUnity-Key` containing your API Webhook key. You can use this key to verify that the request came from BidUnity.

