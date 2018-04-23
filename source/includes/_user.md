# User
This section list all end-points related user object.
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