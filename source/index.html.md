---
title: Letom API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate' target="_blank">Documentation Powered by Slate</a>

includes:
  - errors

search: false
---

# Introduction

You can use our API to access Letom API endpoints, which can get information on various motels, room types, make reservations and more.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Letom uses API keys to allow access to the API.

Letom expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your API key.
</aside>

## Base URL

This is the main fragment from all requests URLs are based from.

From now on, everywhere you see `{BASE_URL}` replace it with the one in the right panel.

> The base URL for API version 1 is

```
https://api-letom.herokuapp.com/v1
```

# Motels

## Get All Motels

```shell
curl "{BASE_URL}/consumer/motels"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "motels": [
    {
      "id": 1,
      "name": "Vásquez e Hijos",
      "address": "Arrabal Berta Gallegos, 14 Esc. 592",
      "email": "terrill_zulauf@hamillthiel.com",
      "phone": "68-217-1923",
      "profile_pic": "https://robohash.org/expeditaquivoluptates.png?size=300x300&set=set1",
      "cover_pic": "https://robohash.org/autetmolestiae.png?size=300x300&set=set1"
    },
    {
      "id": 2,
      "name": "Pulido, Rivas y Llamas Asociados",
      "address": "Caserio Horacio Camarillo, 2 Esc. 195",
      "email": "hollie.purdy@reinger.info",
      "phone": "28-009-4243",
      "profile_pic": "https://robohash.org/placeataniminemo.png?size=300x300&set=set1",
      "cover_pic": "https://robohash.org/inciduntbeataeimpedit.png?size=300x300&set=set1"
    }
  ]
}
```

This endpoint retrieves all available letoms.

### HTTP Request

`GET {BASE_URL}/consumer/motels`

## Get a Specific Letom

```shell
curl "{BASE_URL}/consumer/motels/1"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "motel": {
    "id": 1,
    "name": "Vásquez e Hijos",
    "address": "Arrabal Berta Gallegos, 14 Esc. 592",
    "email": "terrill_zulauf@hamillthiel.com",
    "phone": "68-217-1923",
    "cover_pic": "https://robohash.org/autetmolestiae.png?size=300x300&set=set1",
    "room_types": [
      {
        "id": 1,
        "name": "chimeras",
        "price": "1336",
        "description": "Church-key heirloom retro dreamcatcher. Mlkshk offal mumblecore direct trade street neutra hella. Venmo gastropub asymmetrical jean shorts flexitarian sustainable twee. Austin meh meditation tacos.",
        "cover": "https://robohash.org/autemrecusandaedoloribus.png?size=300x300&set=set1"
      },
      {
        "id": 2,
        "name": "conspirators",
        "price": "4635",
        "description": "Cronut chicharrones food truck vinyl skateboard intelligentsia you probably haven't heard of them. Selvage stumptown letterpress next level intelligentsia pitchfork authentic. Chartreuse irony godard. Pickled health cornhole ennui park drinking twee gastropub. Bicycle rights roof chartreuse.",
        "cover": "https://robohash.org/optiodoloreipsa.png?size=300x300&set=set1"
      }
    ]
  }
}
```

This endpoint retrieves a specific letom and its `RoomTypes`.

### HTTP Request

`GET {BASE_URL}/consumer/motels/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the letom to retrieve

