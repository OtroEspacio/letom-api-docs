# Reservations

## Get a Consumer's Reservations

```shell
curl "https://api-letom.herokuapp.com/v1/consumer/reservations/?email=someemail@address.com"
  -H "Authorization: meowmeowmeow"
  -H "Accept: application/vnd.letom.v1"
```

> The above request returns a JSON structured in following manner:

```json
{
  "reservations": [
    {
      "id": 1,
      "status": "canceled",
      "date_requested": "12 de 09",
      "motel_name": "Vásquez e Hijos",
      "room": {
        "id": 1,
        "name": "giants",
        "description": "Cold-pressed narwhal post-ironic mixtape asymmetrical thundercats put a bird on it. Intelligentsia gluten-free put a bird on it. Ethical gluten-free fingerstache bitters diy. Microdosing messenger bag chicharrones skateboard post-ironic pitchfork."
      }
    },
    {
      "id": 2,
      "status": "canceled",
      "date_requested": "02 de 10",
      "motel_name": "Vásquez e Hijos",
      "room": {
        "id": 5,
        "name": "worshipers",
        "description": "Offal swag vice put a bird on it bespoke. 3 wolf moon paleo squid bitters direct trade intelligentsia flannel vegan. Gluten-free sartorial tattooed blog. Trust fund try-hard swag aesthetic humblebrag blog brooklyn yolo."
      }
    }
  ]
}
```

Get a consumer's all reservations made in Letom. The reservation includes the room type reserved.

### HTTP Request

`GET "https://api-letom.herokuapp.com/v1/consumer/reservations/?email=<CONSUMER-EMAIL-ADDRESS>"`

### URL Parameters

Parameter | Description
--------- | -----------
email | The email address of the current consumer


## Create a Reservation

```shell
curl -X POST "https://api-letom.herokuapp.com/v1/consumer/reservations"
  -H "Authorization: meowmeowmeow"
  -H "Accept: application/vnd.letom.v1"
  -d '{ "reservation": {
        "room_type_id": 5,
        "email": "c2@email.com" }
      }'
```

> The previous POST request creates a reservations and returns a JSON like this:

```json
{
  "reservation": {
    "id": 9,
    "status": "pending",
    "consumer": {
      "id": 1,
      "name": null,
      "last_name": null,
      "email": "c2@email.com",
      "device_id": "string"
    },
    "room": {
      "id": 5,
      "name": "worshipers",
      "status": "active",
      "available": true
    }
  },
  "meta": {
    "message": "Reserva completada"
  }
}
```
This endpoint creates a reservation for the current user. The resulting JSON gives information about the reservation's status, additional data of the consumer and the room type and a custom success message.

<aside class="notice">Users can only make reservations as long as they do not have any reservations with a pending status.</aside>

### HTTP Request

`POST https://api-letom.herokuapp.com/v1/consumer/reservations/`

### Request Parameters

Parameter | Description
--------- | -----------
reservation (*hash*) | A hash containing the `room_type_id` and the `email` for creating the reservation
room_type_id (*integer*) | The ID of the room type to be reserved
email (*string*) | The current user's email address


## Get Last User's Reservation

```shell
curl "https://api-letom.herokuapp.com/v1/consumer/reservations/last/?email=someemail@address.com"
  -H "Authorization: meowmeowmeow"
  -H "Accept: application/vnd.letom.v1"
```

> The previoous request returns a JSON structured like this:

```json
{
  "reservation": {
    "id": 9,
    "status": "pending",
    "consumer": {
      "id": 1,
      "name": null,
      "last_name": null,
      "email": "c2@email.com",
      "device_id": "string"
    },
    "room": {
      "id": 5,
      "name": "worshipers",
      "status": "active",
      "available": false
    }
  }
}
```

Get the current user's last reservation. The reservation includes the room type reserved and the user's data.

### HTTP Request

`GET "https://api-letom.herokuapp.com/v1/consumer/reservations/last/?email=<CONSUMER-EMAIL-ADDRESS>"`

### URL Parameters

Parameter | Description
--------- | -----------
email (*string*) | The email address of the current consumer


## Cancel a Reservation

```shell
curl -X PUT "https://api-letom.herokuapp.com/v1/consumer/reservations/?email=someemail@address.com"
  -H "Authorization: meowmeowmeow"
  -H "Accept: application/vnd.letom.v1"
```

> The above request returns a JSON structured in following manner:

```json
{
  "reservation": {
    "id": 9,
    "status": "canceled",
    "consumer": {
      "id": 1,
      "name": null,
      "last_name": null,
      "email": "c2@email.com",
      "device_id": "string"
    },
    "room": {
      "id": 5,
      "name": "worshipers",
      "status": "active",
      "available": false
    }
  }
}
```

This endpoint finds and cancels the most recent pending reservation a user has made.

### HTTP Request

`PUT "https://api-letom.herokuapp.com/v1/consumer/reservations/cancel/?email=<CONSUMER-EMAIL-ADDRESS>"`

### URL Parameters

Parameter | Description
--------- | -----------
email (*string*) | The email address of the current consumer


