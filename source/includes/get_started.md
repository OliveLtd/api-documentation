# GET STARTED

## Introduction

The Olive API is organized around [REST](http://en.wikipedia.org/wiki/Representational_State_Transfer). Our API has predictable resource-oriented URLs, accepts [form-encoded](https://en.wikipedia.org/wiki/POST_(HTTP)#Use_for_submitting_web_forms) request bodies, returns [JSON-encoded](http://www.json.org/) responses, and uses standard HTTP response codes, authentication, and verbs.

The Olive API allows to create card-linked loyalty and asset building programs.

## Base URL

All API URLs referenced in this documentation start with the following base URL:

`https://api.oliveltd.com/v1`

## Authentication

The Olive API uses API keys to authenticate requests.

Authenticate your API requests by including your test or live secret API key in the request header. Create an HTTP header named `olive-key` and set your secret key as the value.

<aside class="warning">
Do not share or include your secret API keys on client side code.
</aside>

> Example Request

```shell
# With shell, you can just pass the correct header with each request
curl GET \
  https://api.oliveltd.com/v1/cards/6db5a7f8-6738-49f8-80ce-47fce0426bf1 \
  -H 'content-type: application/json' \
  -H 'olive-key: b913d3b7903c4d11a8dfc336ec9c5cc9'
```

## Errors

Olive uses conventional HTTP response codes to indicate the success or failure of an API request. In general:

- Codes in the `2xx` range indicate success
- Codes in the `4xx` range indicate an error that failed given the information provided (e.g., a required parameter was omitted, a charge failed, etc.)
- Codes in the `5xx` range indicate an error with Olive's servers


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- The kitten requested is hidden for administrators only.
404 | Not Found -- The specified kitten could not be found.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
