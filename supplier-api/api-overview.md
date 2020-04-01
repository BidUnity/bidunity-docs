---
description: Allows suppliers to automate quote requests without any human interaction.
---

# Introduction

The BidUnity Supplier API is a set of web services that allow quote requests to be sent directly to suppliers and processed automatically, potentially without any human interaction. 

Suppliers must implement a REST endpoint to receive quote requests with full parts lists and door configurations, and make a web service call to respond with the quote itself.

The API will be expanded to include orders in the future. As new features are added, new verions of the api will become available.

## Technical Overview

The BidUnity Supplier API is a set of web services based on [REST](https://en.wikipedia.org/wiki/Representational_state_transfer). The API accepts [form-encoded](https://en.wikipedia.org/wiki/POST_%28HTTP%29#Use_for_submitting_web_forms) request bodies and returns [JSON-encoded](https://www.json.org) response bodies.

{% tabs %}
{% tab title="BASE URL" %}
```text
https://api.bidunity.com
```
{% endtab %}
{% endtabs %}

## Authentication

The BidUnity API uses API keys to authenticate requests. Suppliers must contact [support@bidunity.com](mailto:support@bidunity.com) to request an API key.

Authentication is performed using [HTTP Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). Provide your API key as the basic auth username without providing a password.

All API requests must be made over HTTPS and include your API key for authentication.

## Webhook Endpoints

Webhooks are part of the supplier API in which BidUnity notifies the supplier of events, such as when a quote request is made to them. In this case, BidUnity will make a request to the supplier at a URL of their choosing with the contents of the quote request. Suppliers must contact [support@bidunity.com](mailto:support@bidunity.com) to configure their endpoints.

