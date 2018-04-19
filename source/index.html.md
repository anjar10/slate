---
title: Flip API V1

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - php

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

## General Response

## Error Code

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# User

## Get User Detail

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
{
    "id": 59,
    "email": "ginanjar.ibnu@gmail.com",
    "name": "Ginanjar Ibnu Solikhin",
    "identity_number": "1234567890",
    "identity_type": "ktp",
    "birth_date": "2000-01-01",
    "phone_number": "+6285729685018",
    "address": "Jalan Amonia V No 2",
    "city": 3405,
    "tempat_lahir": 3492,
    "identity_image": "59_eaa4eba9453d906d8f5ae1816ecaf2fc_1522653089.jpg",
    "face_image": "59_725ba12bb7e49d650042fe46c2a5b5b5_1522653089.jpg",
    "face_and_identity_image": "59_c23bca50e0fc1ea05a074928489dcdfb_1521443408.jpeg",
}
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Update User

## Verify Identity
## Verify Email
## Verify Phone Number

# Transaction
## Get All Tranasction
## Create Transaction
## Confirm Tranasction
## Cancel Tranasction
## Upload Receipt
## Update Beneficiary Account
## Get Transaction Detail
## Inquiry Beneficiary Name

# General
## Get Bank Info
## Is Maintenance

# Callback
## Transaction
## User