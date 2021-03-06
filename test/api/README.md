# API Tests

Our API tests are written in [coffeescript](http://coffeescript.org/) using the [Mocha testing framework](http://mochajs.org/). 

There's a variety of ways to run the tests:

```bash
# Individually
mocha test/api/name_of_test.coffee
# The entire collection of api tests
mocha test/api
# As part of the whole test suite
npm test
```

### Modules

Some modules are declared in the [api-helper.coffee](api-helper.coffee) file for use in any of the api tests:

* `moment` - time manipulation
* `async` - run async processes, good for before blocks
* `lodash (_)` - many utilities
* `shared` - generate uuids
* `expect` - making assertions
* `User` - look up a User in the db

### Helper Methods

There are helper methods declared in the [api-helper.coffee](api-helper.coffee) file. Some useful methods contained there:

* `registerNewUser(callback, main)` - Theres a global user variable that gets overwritten with the new user whenever you call `registerNewUser` unless you pass false in as the second argument.
* `registerManyUsers(number, callback)` - Good for testing things that require many users. The callback function returns new users as and array in the second argument.
