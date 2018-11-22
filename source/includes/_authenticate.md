#Authenticate

To authenticate to the API you need a valid email and password

## HTTP Request
```shell
curl "http://example.com/v1/authenticate -d
'{
    "user" : "user@example.com",
    "password" : "password1234"
  }'
```
> The above command returns JSON structured like this:

```json
{
  "user_id": 1,
    "status": 200,
    "token": "abcdefghijkmnop",
    "access_rights": [
    {
      "id": 22,
      "entity_id": 1,
      "permissions": 65535
    },
    {
      "id": 23,
      "entity_id": 2,
      "permissions": 65535
    }
    ],
    "Msg": "authenticated"
}
```

`POST http://example.com/v1/authenticate`

## Query Parameters

Parameter | Optional | Description
--------- | ------- | -----------
email | false | the login email address
password | false | the clear text password

## Response 
Parameter |  Description
--------- |  -----------
user_id | the user_id related to email address
token |  the generated token you need to use in all your upcoming requests
access_rights | list of all the [AccessRight](#json-objects-accessright) for the user
status | the request [status](#errorcodes)
msg | string containing the message

