---
title: API Reference

toc_footers:

language_tabs:

includes:

search: true
---

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

# API REFERENCE

## Asset Building Programs

### The asset building program object

Attributes | Type | Description
--------- | ------- | -----------
ID | string | Asset building program ID
Created | datetime | Creation date & time
Name | string | Asset building program name
Active | boolean | Whether the asset building program is currently active

### Create asset building program

Creates a new asset building program.

Body arguments | Description
--------- | ------- | -----------
Name | <b><sup><font color="red">REQUIRED</font></sup></b> Asset building program name
Active | Whether the asset building program is currently active. Default value: `false`

```shell
curl GET \
  https://api.oliveltd.com/v1/asset_building_programs \
  -H 'content-type: application/json' \
  -H 'olive-key: b913d3b7903c4d11a8dfc336ec9c5cc9'
  -d '{
    "id": "8b6298a8-70d1-40b2-d331-08d7b3d27117",
    "created": "2020-02-17T17:54:32.1",
    "name": "Acme Inc Asset Building Program",
    "active": true
  }'
```

### List Asset Building Programs

Returns a list of your Asset Building Programs.

```shell
curl GET \
  https://api.oliveltd.com/v1/asset_building_programs \
  -H 'content-type: application/json' \
  -H 'olive-key: b913d3b7903c4d11a8dfc336ec9c5cc9'
```

> RESPONSE

```json
[
  {
    "id": "365fabf4-d482-43fd-1b39-08d7ab196872",
    "name": "Acme Inc Asset Building Program",
    "created": "2020-02-06T15:29:51.187",
    "active": true
  },
  {
    "id": "c882d758-5597-4f3d-8987-5f13a00bd2a7",
    "name": "Umbrella Asset Building Program",
    "created": "2020-02-06T15:05:06.587",
    "active": true
  }
]
```

### Get Asset Building Program

### Edit Asset Building Program

### Delete Asset Building Program


## Brands

## Cards

## Destination Accounts

## Locations

## Loyalty Programs

## Members

## Members (Asset Building Programs)

## Members (Loyalty Programs)

## Notification Preference

## Offers

## Redeemed Offers

## Round-Up Rules

## Source Accounts

## Totals

## Transactions

## Webhooks

## Kittens

### Get All Kittens

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

#### HTTP Request

`GET http://example.com/api/kittens`

#### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

### Get a Specific Kitten

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

#### HTTP Request

`GET http://example.com/kittens/<ID>`

#### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

### Delete a Specific Kitten

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

#### HTTP Request

`DELETE http://example.com/kittens/<ID>`

#### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete
