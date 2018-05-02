# Introduction

Welcome to the Flip API!

## Supported Banks

Currently, we only support disbursement to these banks:

Bank Code | Bank Name
----------|-----------
`mandiri`|Bank Mandiri
`bri`|Bank Rakyat Indonesia
`bni`|BNI (Bank Negara Indonesia) & BNI Syariah
`bca`|Bank Central Asia
`bsm`|Bank Syariah Mandiri
`cimb`|CIMB Niaga & CIMB Niaga Syariah
`muamalat`|Muamalat

## Authentication

```php
<?php 
$api_key = 'aaasssdddfffggghhhiiijjj';
$token = 'zzzxxxcccvvvbbbnnnmmmqqq';

$curl = curl_init();
curl_setopt($curl, CURLOPT_HTTPHEADER, [
	"Authorization: Bearer $token",
	"api-key: $api_key"
	]);
```


```shell
curl --request GET \
  --header 'Authorization: Bearer zzzxxxcccvvvbbbnnnmmmqqq' \
  --header 'api-key: zzzxxxcccvvvbbbnnnmmmqqq'
```


We are using **Bearer Authentication** by including `Authorization` and `api-key` header in each of your request. Value of the `Authorization header` is token provided by [login](#login) or [signup](#sign-up) endpoint.

## General Response

### Unauthorized

```json
Status 401
Content-Type: application/json

{
    "name": "Unauthorized",
    "message": "You are requesting with an invalid credential.",
    "status": 401,
}
```

This response will be sent if the value of Authorization header or the api-key key is invalid.

### Not Found

```json
Status 404
Content-Type: application/json

{
    "name": "Not Found",
    "message": "Page not found.",
    "status": 404,
}
```

You will get this response if the url you're trying to access is wrong, or if the resource you're trying to access is not exist.