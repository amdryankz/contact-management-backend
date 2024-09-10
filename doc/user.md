# User API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "ryan",
  "password": "rahasia",
  "name": "Ahmad Chairiansyah"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "ryan",
    "name": "Ahmad Chairiansyah"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username must not blank, ..."
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "ryan",
  "password": "rahasia"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "ryan",
    "name": "Ahmad Chairiansyah",
    "token": "uuid"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username or password wrong, ..."
}
```

## Get User

Endpoint : GET /api/users/current

Request Header :

- X-API_TOKEN : token

Response Body (Success) :

```json
{
  "data": {
    "username": "ryan",
    "name": "Ahmad Chairiansyah"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized, ..."
}
```

## Update User

Endpoint : PATCH /api/users/current

Request Header :

- X-API_TOKEN : token

Request Body :

```json
{
  "name": "Ahmad Chairiansyah", // tidak wajib
  "password": "rahasia" // tidak wajib
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "ryan",
    "name": "Ahmad Chairiansyah"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized, ..."
}
```

## Logout User

Endpoint : DELETE /api/users/current

Request Header :

- X-API_TOKEN : token

Response Body (Success) :

```json
{
  "data": "OK"
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized, ..."
}
```
