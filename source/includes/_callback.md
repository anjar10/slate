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
    "id": [TRANSACTION_ID],
    "user_id": [USER_ID],
    "amount": 10000,
    "unique_code" : [UNIQUE_CODE],
    "status": "PENDING",
    "sender_bank": "bni",
    "account_number": "12345678",
    "beneficiary_bank": "muamalat",
    "beneficiary_name": "Dummy Account",
    "beneficiary_city": 391,
    "remark": "Dummy via Flip",
    "credit_receipt": "",
    "debit_receipt": "",
    "created_at": "2018-07-03 14:39:12",
    "completed_at": null,
    "fee": null,
    "notes": ""
}
```

> Example of [User Object](#user-object)

```json
{
    "id": 999,
    "email": "dummy_person@gmail.com",
    "email_verified": true,
    "name": "Im Dummy Person",
    "identity_number": "317500010001",
    "identity_type": "ktp",
    "birth_date": "2000-01-01",
    "birth_place": 3492,
    "address": "Jln. Dummy Place",
    "city": 3405,
    "phone_number": "+6285729685018",
    "phone_number_verified": true,
    "identity_image": "59_eaa4eba9453d906d8f5ae1816ecaf2fc_1522653089.jpg",
    "face_image": "59_725ba12bb7e49d650042fe46c2a5b5b5_1522653089.jpg",
    "face_and_identity_image": "59_c23bca50e0fc1ea05a074928489dcdfb_1521443408.jpeg",
    "deposit": 9999,
    "saving": 9999,
    "created_source": '[App ID]',
    "kyc_status": 2,
    "notes": "",
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
token | `string`<br>Validation token to ensure that the callback is coming from our server. You can get your token in your Flip for Developer dashboard.

Example code of how to receive the callback are shown on the right side.