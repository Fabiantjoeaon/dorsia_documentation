---
title: Dorsia API Reference

language_tabs:
  - javascript

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - users
  - rooms
  - reservations
  - customers
  - errors

search: true
---

# Introduction

Welcome to the Dorsia API! Dorsia is a reference to the cult classic movie American Psycho.

This API is built to place reservations and retrieve room information for your company.
At this moment, only one company has been registered, so this documentation is made for employees of that specific company.

For more information, questions, or on how to register your company, please
send me a mail at fabiantjoeaon@gmail.com.

Dorsia API is build on top of Laravel and returns only and only JSON responses.

# Authentication
> For demonstration purposes, an example API call using the Fetch API has been illustrated below:

```javascript
import 'whatwg-fetch';

try {
  fetch('https://www.dorsia.fabiantjoeaon.com/api/v1/login', {
    method: 'POST',
    mode: 'cors',
    headers: {
      'Accept': 'application/json',
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({
      'email': 'your_email',
      'password': 'your_password'
    })
  })
  .then(res => res.json())
  .then((data) => {
    console.log(data);
  });
} catch(e) {
  console.log(e);
}
```

> The above command returns JSON structured like this:

```json
[{
  "token": {
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOjIyLCJpc3MiOiJodHRwczpcL1wvZG9yc2lhLmZhYmlhbnRqb2Vhb24uY29tXC9hcGlcL3YxXC9sb2dpbiIsImlhdCI6MTQ4NDEyNTI2OSwiZXhwIjoxNDg0MTI4ODY5LCJuYmYiOjE0ODQxMjUyNjksImp0aSI6ImZhY2ZjYjU2NDJiYjFkNDY4OGI2NTllMWM0NzQ3ZTc4In0.LOgchsjEmwNL5WRIcHsYEnDMz1DJn5uG0T8vtQKi7GE"
  },
  "user": {
    "id": 22,
    "email": "your_email",
    "name": "Your Name",
    "remember_token": null,
    "created_at": "2016-12-20 17:45:55",
    "updated_at": null
  }
}]
```

> Make sure to replace `your_email` and `your_password` with your credentials.

Dorsia uses JSON Web Tokens for authentication. Due to business logic and security measurements, you can not register as a user, as only employees are registered users.
If you are an employee, and you are not yet registered, please contact your supervisor.

Dorsia automatically generates an temporary JSON key, which is valid for an hour.
You can retrieve your token by POSTing your username and password to this URL:

`POST https://www.dorsia.fabiantjoeaon.com/api/v1/login`

<aside class="notice">
Please keep in mind to log out users when this key turns invalid (it lasts for an hour).
</aside>
