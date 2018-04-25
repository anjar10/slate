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
1000 | The related attribute should not be empty.
1001 | Value for the related attribute is considered not clean. Things that considered as not clean are html tag and `?`, `#`, `$`, `'` (single quote), `"` (double quote), and `;` character
1500 | User was not verified succesfully yet, hence cannot create a transaction
1999 | Undefined error. Please contact us if this happen.


### Transaction Related Errors
Any error related with transaction will have error codes ranging from 2000 to 2999 with detail as described below:

Error Code | Meaning
-----------|--------
2999 | Undefined error. Please contact us if this happen;