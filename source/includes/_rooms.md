# Rooms

## Get all rooms
> A valid response (status code 200) from this endpoint returns JSON structured like this:

```json
{
  "data": [
    {
      "id": 21,
      "name": "Adonismouth.0.15",
      "floor": 0,
      "number": 15,
      "capacity": 2,
      "color": "Groen",
      "type": "Onderzoekkamer",
      "invalid": false,
      "has_pc": true,
      "is_reserved_now": false
    },
    {
      "id": 3,
      "name": "Lake Lyda.0.41",
      "floor": 0,
      "number": 41,
      "capacity": 5,
      "color": "Paars",
      "type": "Onderzoekkamer",
      "invalid": false,
      "has_pc": false,
      "is_reserved_now": true
    }
  ]
}
```

This endpoint retrieves all rooms.

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/rooms/<TOKEN>`

### Query Parameters

Parameter | Description
--------- | ------------
TOKEN | Your JSON web token

## Get a specific room
> A valid response (status code 200) from this endpoint with ID 2 returns JSON structured like this:

```json
{
  "data": {
    "id": 2,
    "name": "Manteland.1.47",
    "floor": 1,
    "number": 47,
    "capacity": 4,
    "color": "Groen",
    "type": "Onderzoekkamer",
    "invalid": false,
    "has_pc": true,
    "is_reserved_now": false
  }
}
```

This endpoint retrieves a specific room.

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/rooms/<ID>/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the room to retrieve
TOKEN | Your JSON web token
