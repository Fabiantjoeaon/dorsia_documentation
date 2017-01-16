# Customers

## Get your customers
> A valid response (status code 200) from this endpoint returns JSON structured like this:

```json  
{
  "data": [
    {
      "id": 1,
      "BSN": 214,
      "first_name": "Geovany",
      "last_name": "Turner",
      "email": "brielle61@yahoo.com"
    },
    {
      "id": 2,
      "BSN": 287,
      "first_name": "Pietro",
      "last_name": "Funk",
      "email": "rodolfo37@mann.com"
    }
  ]
}
```

This endpoint retrieves your customers

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/me/custuomers/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
TOKEN | Your JSON web token

## Get all customers
> A valid response (status code 200) from this endpoint returns JSON structured like this:

```json  
{
  "data": [
    {
      "id": 1,
      "BSN": 214,
      "first_name": "Geovany",
      "last_name": "Turner",
      "email": "brielle61@yahoo.com"
    },
    {
      "id": 2,
      "BSN": 287,
      "first_name": "Pietro",
      "last_name": "Funk",
      "email": "rodolfo37@mann.com"
    }
  ]
}
```

This endpoint retrieves all customers

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/customers/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
TOKEN | Your JSON web token

## Get a specific customer by ID
> A valid response (status code 200) from this endpoint with ID 2 returns JSON structured like this:

```json
{
  "id": 2,
  "BSN": 214,
  "first_name": "Geovany",
  "last_name": "Turner",
  "email": "brielle61@yahoo.com"
}
```

This endpoint retrieves a specific customer

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/reservations/<ID>/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the reservation to retrieve
TOKEN | Your JSON web token

## Get customers by a specific reservation
> A valid response (status code 200) from this endpoint with a reservation ID of 2 returns JSON structured like this:

```json
{
  "data": [
    {
      "id": 1,
      "BSN": 214,
      "first_name": "Geovany",
      "last_name": "Turner",
      "email": "brielle61@yahoo.com"
    },
    {
      "id": 2,
      "BSN": 287,
      "first_name": "Pietro",
      "last_name": "Funk",
      "email": "rodolfo37@mann.com"
    }
  ]
}
```

This endpoint retrieves all customers for a specific reservation

### HTTP Request

`GET https://dorsia.fabiantjoeaon.com/api/v1/reservations/<RESERVATION_ID>/customers/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
RESERVATION_ID | The reservation to retrieve customers for
TOKEN | Your JSON web token

## Add a new customer
> A valid response (status code 200) from this endpoint with an id of 18 returns JSON structured like this:

```json
{
  "id": 18
}
```

### HTTP Request

`POST https://dorsia.fabiantjoeaon.com/api/v1/customers/<TOKEN>`

This endpoint saves a new customer

### POST Parameters

Parameter | Description
--------- | -----------
first_name | The customers first name
last_name | The customers last name
email | The customers email
BSN | The customers social security number
TOKEN | Your JSON web token

## Edit an existing customer

<aside class="notice">
  Note that the BSN key is in capital letters!
</aside>

### HTTP Request

`POST https://dorsia.fabiantjoeaon.com/api/v1/customers/<ID>/<TOKEN>`

This endpoint edits an existing customer by a given ID

### POST Parameters

Parameter | Description
--------- | -----------
first_name | The customers first name
last_name | The customers last name
email | The customers email
BSN | The customers social security number
ID | The customer to edit
TOKEN | Your JSON web token

## Delete a customer
> A valid response (status code 200) from this endpoint with an id of 18 returns JSON structured like this:

```json
{
  "first_name": "Customers first name",
  "last_name": "Customers last name"
}
```

<aside class="notice">
  Note that only customers made by you can be deleted!
</aside>

This endpoint deletes your customer by a given ID

### HTTP Request

`DELETE https://dorsia.fabiantjoeaon.com/api/v1/customer/<CUSTOMER_ID>/<TOKEN>`

### URL Parameters

Parameter | Description
--------- | -----------
CUSTOMER_ID | The customer to delete
TOKEN | Your JSON web token
