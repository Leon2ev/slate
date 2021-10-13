# Synx Pass

Authentication and identification system for heterogeneous networks.

## Register user
Ths endpoint will trigger email verification. You should check your email for verification link.

<aside class="notice">
This endpoint can be used only by the root domain owner as it require authToken.
</aside>

### HTTP Request

**`POST /api/synxpass/create-user`**

### Query Parameters

```shell
curl -X POST https://synxhive.com/api/synxpass/create-user \ 
-H "Content-Type: application/x-www-form-urlencoded" \ 
-d "username={{username}}&password={{password}}&password2={{password2}}&authToken={{authToken}}"
```

Parameter | Default | Description
--------- | ------- | -----------
username | false | Your email address
password | false | Password
password2 | false | Repeat password
authToken | false | Root domain owner token

### Response

> OK

```json
{
  "message": "Success"
}
```

> Server got your request, but something went wrong

```json
{
  "error": "Error"
}
```

<aside class="success">
  <strong>200</strong>
</aside>

## Verify user
This endpoint will verify your email. After that you can continue registraton proccess.

<aside class="notice">
This endpoint can be used only by the root domain owner as it require authToken.
</aside>

### HTTP request

**`POST /api/synxpass/verify-user`**

### Query Parameters

> CURL

```shell
curl -X POST https://synxhive.com/api/synxpass/verify-user \ 
-H "Content-Type: application/x-www-form-urlencoded" \ 
-d "username={{username}}&verification={{verificationToken}}&authToken={{authToken}}"
```

Parameter | Default | Description
--------- | ------- | -----------
username | false | Your email address
verificationToken | false | You can get this token from the url that you got on your email
authToken | false | Root domain owner token

### Response

> OK

```json
{
  "message": "Success"
}
```

> Server got your request, but something went wrong

```json
{
  "error": "Error"
}
```

<aside class="success">
  <strong>200</strong>
</aside>

## Register user
This endpoint will finally register user in the system.

<aside class="notice">
This endpoint can be used only by the root domain owner as it require authToken.
</aside>

### HTTP request

**`POST /api/synxpass/register-user`**

### Query Parameters

> CURL

```shell
curl -X POST https://synxhive.com/api/synxpass/register-user \ 
-H "Content-Type: application/x-www-form-urlencoded" \ 
-d "username={{username}}&password={{password}}&authToken={{authToken}}"
```

Parameter | Default | Description
--------- | ------- | -----------
username | false | Your email address
password | false | Password
authToken | false | Root domain owner token

### Response

> OK

```json
{
  "message": "Success"
}
```

> Server got your request, but something went wrong

```json
{
  "error": "Error"
}
```

<aside class="success">
  <strong>200</strong>
</aside>

## Get token
This endpoint will give you a token.

### HTTP request

**`POST /api/synxpass/get-token`**

### Query Parameters

> CURL

```shell
curl -X POST https://synxhive.com/api/synxpass/get-token \ 
-H "Content-Type: application/x-www-form-urlencoded" \ 
-d "username={{username}}&password={{password}}"
```

Parameter | Default | Description
--------- | ------- | -----------
username | false | Your email address
password | false | Password

### Response

> OK

```json
{
  "token": "aToken_yourToken"
}
```

> Server got your request, but something went wrong

```json
{
  "error": "Error"
}
```

<aside class="success">
  <strong>200</strong>
</aside>

## Forgot password
This endpoint will send you an email with the temporary password which you should use to create new password in the next request.

### HTTP request

**`POST /api/synxpass/forgot-password`**

### Query Parameters

> CURL

```shell
curl -X POST https://synxhive.com/api/synxpass/forgot-password \ 
-H "Content-Type: application/x-www-form-urlencoded" \ 
-d "username={{username}}"
```

Parameter | Default | Description
--------- | ------- | -----------
username | false | Your email address

### Response

> OK

```json
{
  "message": "Success"
}
```

> Server got your request, but something went wrong

```json
{
  "error": "Error"
}
```

<aside class="success">
  <strong>200</strong>
</aside>

## New password
This endpoint allow you to create a new password.

### HTTP request

**`POST /api/synxpass/new-password`**

### Query Parameters

> CURL

```shell
curl -X POST https://synxhive.com/api/synxpass/new-password \ 
-H "Content-Type: application/x-www-form-urlencoded" \ 
-d "username={{username}}&password={{password}}&tempPassword={{tempPassword}}"
```

Parameter | Default | Description
--------- | ------- | -----------
username | false | Your email address
password | false | New password
tempPassword | false | Temporary password which you should get from url that you got on your email

### Response

> OK

```json
{
  "message": "Success"
}
```

> Server got your request, but something went wrong

```json
{
  "error": "Error"
}
```

<aside class="success">
  <strong>200</strong>
</aside>
