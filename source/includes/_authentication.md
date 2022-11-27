# Authentication

ExoDeus uses API keys to allow you to access the API. In order to obtain an API key, you must first register an account with an email address (/register). Once you have submitted the required information in the correct format, you will have to verify the autenticity of your email address(/verify).

Once your account is verified, you may request an API Key (/apikey) using your credentials. This endpoint can also be used to regenerate your API Key. Note that this will invalidate your previous API Key.

In (almost) all further calls to the API, you will need to include your API Key.

## Register

```shell
```

```javascript
```

> Response JSON structure:

```json
{ 
  "code": 200, 
  "status": "OK", 
  "content": "Account awaiting verification, please check your email." 
}
```

Used to register an account.

<aside class="notice">
If you have received the authentication mail in your spam folder, please consider moving the email out of your spam folder. This will facilitate receiving emails from ExoDeus in the future.
</aside>

### Rate limit

1 request/minute.

### HTTP Request

`GET https://api.exod.eus/register`

### Body Parameters

Parameter | Required | Description
--------- | -------- | -----------
email     | true     | The email address for your account. Must be unique. Minimum length: 5. Maximum length: 128.
username  | true     | The username for your account. Must be unique. Minimum length: 4. Maximum length: 16. 
password  | true     | The username for your account. Must be unique. Minimum length: 12. Maximum length: 64. Must contain: 2 lowercase letters, 2 capital letters, 2 digits, 2 special characters.


## Verify

```shell
```

```javascript
```

> Response JSON structure:

```json
{ 
  "code": 200, 
  "status": "OK", 
  "content": "Account verified. Use /apikey to obtain an api key." 
}
```

Used to verify your email address before you can request and API key for your account.

A clickable link will be sent to the email address you provided to the /register endpoint.

### Rate limit

1 request/minute.

### HTTP Request

`GET https://api.exod.eus/verify`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
token     | true     | This is a special token generated solely to verify your account.
