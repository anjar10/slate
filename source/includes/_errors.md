# Errors

## Error Structure

```php
```

```shell
```

If error occured, it will return an error with structure as shown in the right panel:

> Example of Error

```json
{
	"errors" : [
		{
			"code" : 1000,
			"message" : "Name should not be empty"
		},
		...
	]
}
```

## Error Codes

The Flip API uses the following error codes:

### User Related Errors

Any error related with user will have error codes ranging from 1000 to 1999 with detail as described below:

Error Code | Meaning
-----------|--------
1011 | User not found
1012 | Invalid api-key. Please contact Flip to get a valid api-key
1013 | Transaction callback url not found
1014 | User callback url not found
1014 | Validation token callback not found
1016 | Phone number miss or false attribute
1017 | Wrong phone number
1018 | Token not registered
1019 | Phone number has been verified before
1020 | User should fill all identity form before do identity verification
1021 | User should upload all identity image before do identity verification
1022 | User has been verified before
1023 | Verification failed. Make sure your image fulfill the criteria
1024 | No image uploaded
1030 | Parameter empty
1500 | User should finish verification progress before create transaction
1600 | Action can\'t be executed


### Transaction Related Errors
Any error related with transaction will have error codes ranging from 2000 to 2999 with detail as described below:

Error Code | Meaning
-----------|--------
2001 | Pagination parameter should be an integer and more than zero (0)
2002 | Page parameter should be an integer and more than zero (0)
2003 | Transaction ID has not assigned. Please contact Flip\'s Developer to fix this
2011 | Miss or false attribute
2021 | Transaction not found
2022 | Transaction has been confirmed before
2023 | Only transaction with NEW status could be canceled
2031 | Only transaction with WRONG_ACCOUNT_NUMBER status can update
2042 | Credit receipt file should be uploaded
2041 | Only transaction with NEW or NEED CREDIT RECEIPT status can upload receipt
2050 | Bank code should not empty
2051 | Bank code is invalid
2052 | Failed to save beneficiary_city to account number. Please try again
2056 | Account number should not empty
2057 | Account number failed to save. Please try again