# Observables

JavaScript objects that can

* notify subscribers about changes
* automatically detect dependencies

```javascript
var myViewModel = {
    orderId: ko.observable(''),
    isPending: ko.observable(false)
}

// Read
myViewModel.orderId();

// Write
myViewModel.orderId('12345');

// Multiple write
myViewModel.firstName('12345').age(true);
```

### Explicit Subscription

The subscribe function has 3 parameters:

* callback
* target (optional)
* event (optional)

```javascript
var subscription = myViewModel.orderId.subscribe(function(newValue) {
    // code goes here
});

// some where later
subscription.dispose();
```

## Observable Arrays

Putting an object in observable array doesn't make all its properties observables. An observable array notifies its listeners if objects are added or removed

```javascript
var myViewModel = {
    breadcrumb: ko.observableArray([])
}

// Add an item
myViewModel.breadcrumb.push({
    label: 'home',
    url: '/home'
});

// Remove all values
myViewModel.breadcrumb.removeAll();
```

Any of the native JavaScript array functions can be used

## Computed Observables

Functions dependent on one or more observables and will automatically update if any of the dependencies change

```javascript
// Some code
```

Pure computed observable simply calculates and returns a value

```javascript
isMobile = ko.pureComputed(function () {
    return viewportDesignation() === 'xs';   
});
```
