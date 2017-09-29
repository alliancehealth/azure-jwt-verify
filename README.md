pcf-jwt-verify
=================================


## This Plugin Requires
* NodeJS Runtime

## Features
* this repo is a fork of azure-jwt-verify that is changed.
* Verify JWT Token issued by PCF

## Install Plugin
`npm install --save pcf-jwt-verify`
 

### Initialize module
```javascript
var pcfJWT = require('azure-jwt-verify');

```

### Configuration and the JWT to verify
```javascript
var jwtToken = "YOUR_JWT_TOKEN_TO_VERIFY"; // You can find this token after logging in to pcf sso
const config = {
    JWK_URI: "",
    ISS: "",
    AUD: ""
};
```
* JWK_URI and the ISS(Issuer) can be obtained from the metadata endpoint of the policies created in the PCF tenant.
* AUD(Audience) is the Client ID of the application accessing the tenant.

### Verify Function
```javascript
azureJWT.verify(jwtToken, config).then(function(decoded){
// success callback

}, function(error){
// error callback

})
```

