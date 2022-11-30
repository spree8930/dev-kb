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

## Controlling text and appearance

### visible and hidden bindings

```html
<div data-bind="visible: myValues().length > 0">
    // code here
</div>

<div data-bind="hidden: !$parents[1].isPaymentActive()">
    // code here
</div>
```

### text binding

```html
<span data-bind="text: displayName"></span>

// Containerless syntax
<select data-bind="foreach: items">
    <option>Item <!--ko text: name--><!--/ko--></option>
</select>
```

### html binding

```html
<div data-bind="html: $data.product().description"></div>
```

### class and css bindings

```html
// The "class" parameter value should be a string 
// that corresponds to the CSS class
<div data-bind="class: profitStatus">
   Profit Information
</div>

// Pass an object in which the property names are CSS classes 
// and their values evaluate to true or false
<div data-bind="css: { profitWarning: currentProfit() < 0, majorHighlight: isSevere }">
```

### style binding

```html
<div data-bind="style: { color: currentProfit() < 0 ? 'red' : 'black' }">
   Profit Information
</div>
```

### attr binding

```html
<a data-bind="attr: { href: '#tab' + displayName(), title: details }">
    Report
</a>
```
