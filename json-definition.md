# Packet Definitions
## About
To ensure consistent communication between various microservices, the packets are explicitly defined. These are likely used as JSON-formatted string.
This definition may be updated.

## Definition and Uses
### Extern JSON 
#### Definition
```json
{
  "auth":{
    <AuthReq JSON>
  },
  "req":{
    <information necessary for the request to process by the appropriate end-point microservice. Ignored at GET `/authenticate`>
  }
}
```
#### Use
Input to Auth microservice
### AuthReq JSON
#### Definition
```json
{
  "id":"",
  "pass":"",
  "token":""
}
```
#### Use
output from Auth microservice to Database microservice's POST /authenticate as well as response back to Auth with a token.
### TokenRes JSON
#### Definition
```json
{
  "token":""
}
```
#### Use
response back to user from Auth microservice's GET /authenticate
### Route JSON
#### Definition
```json
{
  "api":"",
  "method":"",
  "req":{
    <information necessary for the request to process by the appropriate end-point microservice.>
  }
}
```
*where `api` refers to the API the request used, and `method` refers to the REST, and `req` is identical to Extern JSON's `req`.*
#### Use
from Auth microservice to Route microservice
