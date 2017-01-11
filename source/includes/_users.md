# Users

## Get your user related data
> A valid response (status code 200) from this endpoint returns JSON structured like this:

```json
{
  "data": {
    "id": 22,
    "email": "your_email",
    "name": "Your Name",
    "remember_token": null,
    "created_at": "2016-12-20 17:45:55",
    "updated_at": null
  }
}
```

This endpoint retrieves your user relevant data.

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/me/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
TOKEN | Your JSON web token

## Get all users
> A valid response (status code 200) from this endpoint returns JSON structured like this:

```json
{
  "data": [
    {
      "id": 1,
      "email": "casper67@kessler.com",
      "name": "Mr. Markus Padberg",
      "remember_token": null,
      "created_at": "2016-12-30 20:57:50",
      "updated_at": null
    },
    {
      "id": 2,
      "email": "gleason.soledad@hotmail.com",
      "name": "Miss Bettie Kemmer",
      "remember_token": null,
      "created_at": "2016-12-21 18:02:02",
      "updated_at": null
    }
  ]
}
```

This endpoint retrieves all users

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/users/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
TOKEN | Your JSON web token

## Get a specific User
> A valid response (status code 200) from this endpoint with ID 2 returns JSON structured like this:

```json
{
  "data": {
    "id": 2,
    "email": "gleason.soledad@hotmail.com",
    "name": "Miss Bettie Kemmer",
    "remember_token": null,
    "created_at": "2016-12-21 18:02:02",
    "updated_at": null
  }
}
```

This endpoint retrieves a specific user.

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/users/<ID>/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to retrieve
TOKEN | Your JSON web token
