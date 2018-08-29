# @feathersjs/authentication-jwt

> __Important:__ The code for this module has been moved into the main Feathers repository at [feathersjs/feathers](https://github.com/feathersjs/feathers) ([package direct link](https://github.com/feathersjs/feathers/tree/master/packages/authentication-jwt)). Please open issues and pull requests there. No changes in your existing Feathers applications are necessary.

JWT authentication strategy for feathers-authentication using Passport

## Installation

```
npm install @feathersjs/authentication-jwt --save
```

## Quick example

```js
const feathers = require('@feathersjs/feathers');
const authentication = require('feathers-authentication');
const jwt = require('@feathersjs/authentication-jwt');
const app = feathers();

// Setup authentication
app.configure(authentication(settings));
app.configure(jwt());

// Setup a hook to only allow valid JWTs to authenticate
// and get new JWT access tokens
app.service('authentication').hooks({
  before: {
    create: [
      authentication.hooks.authenticate(['jwt'])
    ]
  }
});
```

## Documentation

Please refer to the [@feathersjs/authentication-jwt documentation](https://docs.feathersjs.com/api/authentication/jwt.html) for more details.


## License

Copyright (c) 2018

Licensed under the [MIT license](LICENSE).
