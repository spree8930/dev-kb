# Introduction

## Model-View-View Model (MVVM) Design Pattern

**Model:** application's stored data from server/DB. It is independent of any UI

**View Model:** code representation of data and operations on UI. It holds the unsaved data user is working with. In KO, view models are pure JavaScript objects.

```javascript
var myViewModel = {
    firstName: 'test'
}
```

**View:** Interactive UI representing the state of view model. When using KO, it is HTML document (or templates) with declarative bindings to link it to the view model

```html
<span data-bind="text: firstName"></span>
```

### Activating Knockout

```javascript
ko.applyBindings(myViewModel);
```

OCC has following in the main.js

```javascript
ko.applyBindings(masterViewModel, document.getElementById("oracle-cc"));
```

{% hint style="info" %}
[https://knockoutjs.com/documentation/introduction.html](https://knockoutjs.com/documentation/introduction.html)
{% endhint %}

