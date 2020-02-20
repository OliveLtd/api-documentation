## Asset Building Programs

### The Asset Building Program object

Attributes | Type | Description
--------- | ------- | -----------
ID | string | Asset building program ID
Created | datetime | Creation date & time
Name | string | Asset building program name
Active | boolean | Whether the asset building program is currently active

### Create an Asset Building Program

```swift
POST /v1/asset_building_programs HTTPS/1.1
```

```shell
curl -v -X POST \
  https://api.oliveltd.com/v1/asset_building_programs \
  -H 'content-type: application/json' \
  -H 'olive-key: b913d3b7903c4d11a8dfc336ec9c5cc9'
  -d '{
    "name": "Acme Inc Asset Building Program",
    "active": true
  }'
```
> RESPONSE

```json
{
  "id": "365fabf4-d482-43fd-1b39-08d7ab196872",
  "name": "Acme Inc Asset Building Program",
  "created": "2020-02-06T15:29:51.187",
  "active": true
}
```

Creates a new asset building program.

**Arguments**

| | |
--------- | ------- | ----------
Name | <b><sup><font color="red">REQUIRED</font></sup></b> Asset building program name
Active | Whether the asset building program is currently active. Default value: `false`

**Returns**

Returns an Asset Building Program object.

### List Asset Building Programs

```shell
curl -v -X GET \
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

Returns a list of your Asset Building Programs.

**Arguments**

No arguments.

**Returns**

Returns an array of Asset Building Program objects.

### Retrieve an Asset Building Program

```shell
curl -v -X GET \
  https://api.oliveltd.com/v1/asset_building_programs/365fabf4-d482-43fd-1b39-08d7ab196872 \
  -H 'content-type: application/json' \
  -H 'olive-key: b913d3b7903c4d11a8dfc336ec9c5cc9'
```

> RESPONSE

```json
{
  "id": "365fabf4-d482-43fd-1b39-08d7ab196872",
  "name": "Acme Inc Asset Building Program",
  "created": "2020-02-06T15:29:51.187",
  "active": true
}
```

Retrieves an Asset Building Program with the given ID.

**Arguments**

No arguments.

**Returns**

Returns an Asset Building Program object.

### Edit Asset Building Program

```shell
curl -v -X PATCH \
  https://api.oliveltd.com/v1/asset_building_programs/365fabf4-d482-43fd-1b39-08d7ab196872 \
  -H 'content-type: application/json' \
  -H 'olive-key: b913d3b7903c4d11a8dfc336ec9c5cc9'
  -d '{
    "name": "Globex Asset Building Program",
    "active": true
  }'
```

> RESPONSE

```json
{
  "id": "365fabf4-d482-43fd-1b39-08d7ab196872",
  "name": "Globex Asset Building Program",
  "created": "2020-02-06T15:29:51.187",
  "active": true
}
```
**Arguments**

 | | |
--------- | ------- | ----------
Name | *Optional.* Asset building program name
Active | *Optional.* Whether the asset building program is currently active. Default value: `false`

**Returns**

Returns the edited Asset Building Program object.

### Delete Asset Building Program

```shell
curl -v -X DELETE \
  https://api.oliveltd.com/v1/asset_building_programs/365fabf4-d482-43fd-1b39-08d7ab196872 \
  -H 'content-type: application/json' \
  -H 'olive-key: b913d3b7903c4d11a8dfc336ec9c5cc9'
```

> RESPONSE

```json
{
  "id": "365fabf4-d482-43fd-1b39-08d7ab196872",
  "name": "Acme Inc Asset Building Program",
  "created": "2020-02-06T15:29:51.187",
  "active": true
}
```
Deletes an Asset Building Program.

**Arguments**

No arguments.

**Returns**

Returns whether the Asset Building Program object has been deleted.
