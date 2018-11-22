# Users

## Create new user

### HTTP Request

`POST http://example.com/v1/user/create`

### Query Parameters

Parameter | Optional | Description
--------- | ------- | -----------
name | false | the name of the user
surname | false | the surname of the user
email | false | unique email of the user
password | false | password wanted
permissions | false | initial [permissions](#permissions) for the user
auth | false | [authorization](#json-objects-authorization) object

### Response

Parameter |  Description
--------- |  -----------
status | the request [status](#errorcodes)
msg | string containing the message
id | the id of the user created (if status is success)

##  Update User

`POST http://example.com/v1/user/update`

### Query Parameters

Parameter | Optional | Description
--------- | ------- | -----------
id | false | the id of the user
name | true | the name of the user
surname | true | the surname of the user
password | true | password wanted
permissions | true | [permissions](#permissions) for the user. The user that executes the query should have the permissions to update the permissions and cannot set permissions higher to the one he already have
auth | false | [authorization](#json-objects-authorization) object

All the optional fields that are not present will not be updated

### Response

Parameter |  Description
--------- |  -----------
status | the request [status](#errorcodes)
msg | string containing the message
