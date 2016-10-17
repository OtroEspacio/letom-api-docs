# Consumers

## Create Consumer

```shell
curl -X POST "https://api-letom.herokuapp.com/v1/consumer/consumers"
  -H "Authorization: meowmeowmeow"
  -H "Accept: application/vnd.letom.v1"
  -d '{ "consumer": {
        "device_id": "somerandomstring" }
      }'
```

> The previous request returns a consumer JSON as follows:

```json
{
  "consumer": {
    "id": 2,
    "name": null,
    "last_name": null,
    "email": null,
    "device_id": "somedeviceidstring"
  }
}
```

Creates a new consumer that will be able to make reservations.

### HTTP Request

`POST "https://api-letom.herokuapp.com/v1/consumer/consumers"`

### URL Parameters

Parameter | Description
--------- | -----------
consumer (*hash*)| A hash containing the `device_id` for registering the user in the databse
device_id (*string*)| String obtained from the current user's mobile phone
