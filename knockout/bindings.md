# Bindings

## Binding syntax

```html
<span data-bind="text: myMessage"></span>

// Multiple Bindings
<input data-bind="value: cellphoneNumber, enable: hasCellphone" />
```

## Binding Context

**$parent:** view model object in parent context, immediately outside the current context

**$parents:** array of all the parent view models

**$root:** topmost parent context, usually the object that was passed to ko.applyBindings

**$component:** If you’re within the context of a particular component template, then $component refers to the viewmodel for that component

**$data:** view model object in current context

**$index:** This is the zero-based index of the current array entry being rendered by a foreach binding.

**$parentContext:** This refers to the binding context object at the parent level. This is different from $parent, which refers to the data (not binding context) at the parent level

