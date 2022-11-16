# Observables

JavaScript objects that can

* notify subscribers about changes
* automatically detect dependencies

```javascript
var myViewModel = {
    firstName: ko.observable('test'),
    age: ko.observable(50)
}

// Read
myViewModel.firstName();

// Write
myViewModel.firstName('first');

// Multiple write
myViewModel.firstName('first').age(40);
```

### Explicit Subscription

The subscribe function has 3 parameters:

* callback
* target (optional)
* event (optional)
