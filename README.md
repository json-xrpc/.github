# JSON.xRPC - JSON E*x*tended RPC

All about JSON.xRPC

## What is JSON-RPC?

TBD.

## Why extend it?

TBD.

## What are the extensions we did?

TBD.

## The Spec

TBD.

* `"jsonrpc": "2.0"` is optional, it's is just ignored
* `"method"` in HTTP is optional, if missing it will be read from HTTP URL like this `/rpc/<METHOD>`. This helps using Swagger/OpenAPI/Postman. In WS method is manadatory.
* When called the function recieves a second optional parameter called `ctx` (for context) containing the object returned by auth method, for example auth might read session cookie or basic auth head and based on that returns `{"user":{id, name, avatar, ...}}`. 
* `"error"` object has the following properies beside `"code"` and `"message"`
  * `level`: `string` optional defaults to `error` but can be set `warning` in case of non-code problem like validation errors.
  * `trace`: `string`  which is the stack trace in non-production environment.
  * `validations`: `Object<string, Array<string>>` in case of validation errors it contains a mapping of field names (properties) and their corresponding array of problems.
