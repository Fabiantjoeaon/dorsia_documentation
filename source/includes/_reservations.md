# Reservations

## Get your reservations
> A valid response (status code 200) from this endpoint returns JSON structured like this:

<aside class="notice">
  To avoid multiple API calls, customer data relevant to this reservation is automatically passed on to your reservation.
</aside>

```json  
{
  "data": [
    {
      "id": 19,
      "start_date_time": "2017-01-11 14:30:00",
      "length_minutes": 0,
      "end_date_time": "2017-01-11 15:30:00",
      "activity": "eufheuhg",
      "description": "eugheug",
      "is_active_now": 0,
      "number_persons": 3,
      "has_passed": 0,
      "room_id": 3,
      "user_id": 22,
      "customer_id": 22,
      "created_at": "2017-01-11 10:03:14",
      "updated_at": "2017-01-11 10:03:14",
      "room": {
        "id": 3,
        "location": "Lake Lyda",
        "floor": 0,
        "number": 41,
        "capacity": 3,
        "color": "Paars",
        "type": "Onderzoekkamer",
        "is_reserved_now": 0,
        "invalid": 0,
        "has_pc": 0,
        "created_at": "2017-01-07 03:09:46",
        "updated_at": null
      },
      "customer": {
        "id": 22,
        "BSN": 123456,
        "first_name": "Jurrian",
        "last_name": "Lammerts",
        "email": "jurrianlammerts@hotmail.com",
        "user_id": 22,
        "created_at": "2017-01-11 10:03:14",
        "updated_at": "2017-01-11 10:03:14"
      }
    }
  ]
}
```

This endpoint retrieves your reservations

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/me/reservations/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
TOKEN | Your JSON web token


## Get all reservations
> A valid response (status code 200) from this endpoint returns JSON structured like this:

```json
{
  "data": [
    {
      "start_date_time": "2017-01-12 10:48:54",
      "length_minutes": 66,
      "end_date_time": "2017-01-12 11:54:54",
      "activity": "Quaerat id aut.",
      "description": "Labore sapiente earum.",
      "is_active_now": 0,
      "number_persons": 1,
      "room_id": 15
    },
    {
      "start_date_time": "2017-01-12 10:48:54",
      "length_minutes": 106,
      "end_date_time": "2017-01-12 12:34:54",
      "activity": "Eligendi soluta sunt et.",
      "description": "Iste in sapiente cupiditate molestiae.",
      "is_active_now": 0,
      "number_persons": 5,
      "room_id": 2
    }
  ]
}
```

This endpoint retrieves all reservations

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/reservations/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
TOKEN | Your JSON web token

## Get a specific reservation by ID
> A valid response (status code 200) from this endpoint with ID 2 returns JSON structured like this:

```json
{
  "data": {
    "id": 2,
    "start_date_time": "2017-01-12 10:48:54",
    "length_minutes": 66,
    "end_date_time": "2017-01-12 11:54:54",
    "activity": "Quaerat id aut.",
    "description": "Labore sapiente earum.",
    "is_active_now": 0,
    "number_persons": 1,
    "has_passed": 0,
    "room_id": 15,
    "user_id": 3,
    "customer_id": 4,
    "created_at": "2016-12-22 23:24:19",
    "updated_at": null,
    "customer": {
      "id": 4,
      "BSN": 589,
      "first_name": "Preston",
      "last_name": "Will",
      "email": "thora.pacocha@gmail.com",
      "user_id": 20,
      "created_at": "2016-12-29 08:32:43",
      "updated_at": null
    }
  }
}
```

This endpoint retrieves a specific reservation

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/reservations/<ID>/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the reservation to retrieve
TOKEN | Your JSON web token

## Get a specific reservation by date
> A valid response (status code 200) from this endpoint with a valid date string returns JSON structured like this:

```json
{
  "data": [
    {
      "start_date_time": "2017-01-12 10:48:54",
      "length_minutes": 66,
      "end_date_time": "2017-01-12 11:54:54",
      "activity": "Quaerat id aut.",
      "description": "Labore sapiente earum.",
      "is_active_now": 0,
      "number_persons": 1,
      "room_id": 15
    },
    {
      "start_date_time": "2017-01-12 10:48:54",
      "length_minutes": 106,
      "end_date_time": "2017-01-12 12:34:54",
      "activity": "Eligendi soluta sunt et.",
      "description": "Iste in sapiente cupiditate molestiae.",
      "is_active_now": 0,
      "number_persons": 5,
      "room_id": 2
    },
    {
      "start_date_time": "2017-01-12 10:48:54",
      "length_minutes": 171,
      "end_date_time": "2017-01-12 13:39:54",
      "activity": "Qui ut omnis aut.",
      "description": "Quia consectetur assumenda unde doloribus fugiat.",
      "is_active_now": 0,
      "number_persons": 7,
      "room_id": 11
    }
  ]
}
```
This endpoint retrieves specific a reservation by date

<aside class="notice">
  Pay attention to the format of the date, which is YYYY-MM-DD in this case
</aside>

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/reservations/date/<DATE>/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
DATE | The date of the reservation to retrieve
TOKEN | Your JSON web token

## Get reservations by a specific room
> A valid response (status code 200) from this endpoint with a room ID of 2 returns JSON structured like this:

```json
{
  "data": [
    {
      "start_date_time": "2017-01-12 10:48:54",
      "length_minutes": 106,
      "end_date_time": "2017-01-12 12:34:54",
      "activity": "Eligendi soluta sunt et.",
      "description": "Iste in sapiente cupiditate molestiae.",
      "is_active_now": 0,
      "number_persons": 5,
      "room_id": 2
    }
  ]
}
```

This endpoint retrieves all reservations for a specific room

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/rooms/<ROOM_ID>/reservations/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
ROOM_ID | The room to retrieve reservations for
TOKEN | Your JSON web token

## Get all reservations by a specific user
> A valid response (status code 200) from this endpoint with a user ID of 2 returns JSON structured like this:

```json
{
  "data": [
    {
      "start_date_time": "2017-01-12 10:48:54",
      "length_minutes": 66,
      "end_date_time": "2017-01-12 11:54:54",
      "activity": "Quaerat id aut.",
      "description": "Labore sapiente earum.",
      "is_active_now": 0,
      "number_persons": 1,
      "room_id": 15
    }
  ]
}
```

This endpoint retrieves all reservations for a specific user

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/rooms/<USER_ID>/reservations/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
USER_ID | The user to retrieve reservations for
TOKEN | Your JSON web token

## Place a new reservation

### HTTP Request

`POST https://dorsia.fabiantjoeaon.com/api/v1/rooms/<TOKEN>`

### POST Parameters

Parameter | Description
--------- | -----------
start_date_time | The starting date and time for the reservation, formatted YYYY-MM-DD H:M:S
length_minutes | The length in minutes of the reservation
end_date_time | The end date and time for the reservation, formatted YYYY-MM-DD H:M:S
activity | The activity of the reservation
description | The description of the reservation
number_persons | The number of persons for this reservation (should not exceed the room capacity!)
customer_id | The ID for the customer for this reservation
room_id | The ID for the room for this reservation
TOKEN | Your JSON web token



## Edit an existing reservation

## Delete a reservation
