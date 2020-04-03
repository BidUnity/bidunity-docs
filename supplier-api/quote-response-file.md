---
description: >-
  Allows suppliers to send a quote PDF file through a web service in after
  receiving a quote request.
---

# Quote Response File

{% api-method method="post" host="https://bidunity.com/supplier/api" path="/v1/quote/response/file" %}
{% api-method-summary %}
Quote Response File
{% endapi-method-summary %}

{% api-method-description %}
Uploads a PDF file of the quote in response to a quote request. The `Content-Type` of this request must be `multipart/form-data` in order to accept a file.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Must contain your API key as Base64 encoded string. See HTTP Basic Auth for details.
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
multipart/form-data
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="request\_id" type="string" required=true %}
The unique identifier of the quote request this is responding to.
{% endapi-method-parameter %}

{% api-method-parameter name="file" type="string" required=true %}
The PDF file of the quote. The MIME type of the file must be `application/pdf`. Only PDF files are supported.
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
File successfully received by BidUnity.
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

## Example

```bash
curl https://api.bidunity.com/v1/quote/response/file \
  -u your_api_key: \
  -F request_id="d770d1d3-72f6-48b7-b24b-fea1c8a2da77" \
  -F request_type="quote"
  -F file="@/path/to/file.pdf"
```

