# Node.js

Yarn - An npm Alternative - Yarn is an alternative to npm. It's faster, more secure, and easier to use. You don't need to change a line of code to switch.

Debugging Node - Learn how to debug Node.js applications using Google Chrome and Visual Studio Code.

Diving into ESLint - Learn how to setup and configure ESLint to work with JavaScript, Node, and React.

Publish Your Own npm Module - Learn how to create and publish your own NPM module.

```node.js
var userSchema = new Schema({
  phone: {
    type: String,
    validate: {
      validator: function(v) {
        return /\d{3}-\d{3}-\d{4}/.test(v);
      },
      message: props => `${props.value} is not a valid phone number!`
    },
    required: [true, 'User phone number required']
  }
});

var User = db.model('user', userSchema);
var user = new User();
var error;

user.phone = '555.0123';
error = user.validateSync();
assert.equal(error.errors['phone'].message,
  '555.0123 is not a valid phone number!');

user.phone = '';
error = user.validateSync();
assert.equal(error.errors['phone'].message,
  'User phone number required');

user.phone = '201-555-0123';
// Validation succeeds! Phone number is defined
// and fits `DDD-DDD-DDDD`
error = user.validateSync();
assert.equal(error, null);
```
