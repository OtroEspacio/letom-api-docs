# Motels

## Get All Motels

```shell
curl "https://letom-st.herokuapp.com/v1/consumer/motels"
  -H "Authorization: SUPER-COOL-ACCESS-TOKEN"
  -H "Accept: application/vnd.letom.v1"
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

`GET https://letom-st.herokuapp.com/v1/consumer/motels`

## Get a Specific Letom

```shell
curl "https://letom-st.herokuapp.com/v1/consumer/motels/1"
  -H "Authorization: SUPER-COOL-ACCESS-TOKEN"
  -H "Accept: application/vnd.letom.v1"
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

`GET https://letom-st.herokuapp.com/v1/consumer/motels/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the letom to retrieve
