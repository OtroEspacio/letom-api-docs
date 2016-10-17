# Room Types

## Get a Specific Room Type

```shell
curl "{BASE_URL}/consumer/room_types/1"
  -H "Authorization: meowmeowmeow"
```

> The above request returns a JSON structured like this:

```json
{
  "room_type": {
    "id": 1,
    "name": "fishes",
    "price": "5556",
    "description": "Swag cred pabst yuccie literally 8-bit kombucha. Umami health whatever jean shorts keffiyeh chicharrones. Scenester vegan normcore disrupt small batch tofu sustainable. Humblebrag pop-up franzen.",
    "available_rooms": 4,
    "room_type_pictures": [
      {
        "id": 16,
        "pic": "https://robohash.org/asperiorespariaturmagni.png?size=300x300&set=set1"
      },
      {
        "id": 17,
        "pic": "https://robohash.org/autdignissimosnihil.png?size=300x300&set=set1"
      }
    ]
  }
}
```

Get the information of a room type and all its pictures.

### HTTP Request

`GET "{BASE_URL}/consumer/room_types/<ID>"`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the room type to retrieve
