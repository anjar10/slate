# Callback

```php
<?php
$data = isset($_POST['data']) ? $_POST['data'] : null;
$token = isset($_POST['token']) ? $_POST['token'] : null;
if($token === 'the_token_you_get_from_big_flip_dashboard'){
	$decoded_data = json_decode($data);
	print_r($decoded_data);
	//example of what will be printed are listed below
}
```

```shell
# See php tab for sample code
```

> Example of bank account inquiry

```json
{
    "bank_code": "bca",
    "account_number": "5465327020",
    "account_holder": "PT Fliptech Lentera IP",
    "status": "SUCCESS"
}
```

> Example of transaction

```json
{
    "id": 790,
    "user_id": 23,
    "amount": 10000,
    "status": "DONE",
    "timestamp": "2017-08-28 14:32:47",
    "beneficiary_bank": "bni",
    "beneficiary_account": "0437051936",
    "beneficiary_name": "- FLIPTECH LENTERA INSPIRASI P",
    "sender_bank": "bri",
    "remark": "testing",
    "receipt": "https://storage.biznetgiocloud.com/receipt.jpg",
    "time_served": "2017-08-28 14:42:47",
    "recipient_city": 391,
    "fee": 1500
}
```

> Example of User

```json
{
    "id": 59,
    "email": "ginanjar.ibnu@gmail.com",
    "name": "Ginanjar Ibnu Solikhin",
    "identity_number": "1234567890",
    "identity_type": "ktp",
    "date_of_birth": "1998-06-05",
    "identity_image": "https://storage.biznetgiocloud.com/identity.jpg",
    "face_image": "https://storage.biznetgiocloud.com/face.jpg",
    "face_and_identity_image": "https://storage.biznetgiocloud.com/face_and_identity.jpg",
    "phone_number": "+6285729685018",
    "deposit": 0,
    "address": "Jalan Amonia V, Beji Timur, Beji",
    "city": 3405,
    "place_of_birth": 3492,
    "verification_status" : "DONE",
    "verification_failure_notes" : "",
}
```

We will hit these callback when:

- transaction status changed to `DONE`, `CANCELED`, or `INVALID_BENEFICIARY_ACCOUNT`

- our system have completed the account inquiry process

- user verification status changed to `DONE` or `REJECTED`

The provided URL should return 200 HTTP status. Otherwise, it will be retry as described below:

Callback Type | Expected Response Status | Timeout | Maximum Retry | Delay
--------------|--------------------------|---------|---------------|-------
Transaction | 200 | 30 seconds | 3 | 2 minutes
User | 200 | 30 seconds | 3 | 2 minutes
Bank Account Inquiry | 200 | 30 seconds | - | -

We will hit your URL using POST request with content type `application/x-www-form-urlencoded` and payload as described below:

Attribute | Description
----------|-------------
data | `string`<br>JSON array string with content exactly the same as the response of disbursement or bank account inquiry (see example on the right side)
token | `string`<br>Validation token to ensure that the callback is coming from our server. You can get your token in your Big Flip dashboard.

Example code of how to receive the callback are shown on the right side.