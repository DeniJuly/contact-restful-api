# User API Spec

## Register User API

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "pzn",
  "password": "rahasia",
  "name": "Deni juli Setiawan"
}
```

Response Body Success :

```json
{
  "data": {
    "username": "pzn",
    "name": "Deni Juli Setiawan"
  }
}
```

Response Body Error :

```json
{
  "errors": "Username already registered"
}
```

## Login User API

Endpoint : POST api/users/login

Request Body :

```json
{
  "username": "pzn",
  "password": "rahasia"
}
```

Request Body Success :

```json
{
  "data": {
    "token": "unique-token"
  }
}
```

Request Body Error :

```json
{
  "errors": "Username or password wrong"
}
```

## Update User API

Endpoint : PATCH api/users/current

Headers :

- Authorization : token

Request Body :

```json
{
  "name": "Deni Juli Setiawan", //optional
  "password": "new-password" //optional
}
```

Request Body Success :

```json
{
  "data": {
    "username": "pzn",
    "name": "Deni Juli Setiawan"
  }
}
```

Request Body Error :

```json
{
  "errors": "Name length max 100"
}
```

## Get User API

Endpoint : GET api/users/current

Headers :

- Authorization : token

Request Body Success :

```json
{
  "data": {
    "username": "pzn",
    "name": "Deni Juli Setiawan"
  }
}
```

Request Body Error :

```json
{
  "errors": "Unauthorize"
}
```

## Logout User API

Endpoint : DELETE api/users/logout

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": "OK"
}
```

Response Body Error :

```json
{
  "errors": "Unauthorize"
}
```
