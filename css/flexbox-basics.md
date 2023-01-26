# Flexbox Basics

Flexbox is a one-dimensional layout model ie it deals with layout in one dimension at a time - either as a row or a column

## Set up a container

**index.html**

```html
<html>
<head>
    <title>Learn Flexbox</title>
    <link rel="stylesheet" href="index.css">
</head>
<body>
    <div class="container">
        <div class="item-1">One</div>
        <div class="item-2">Two</div>
        <div class="item-3">Three</div>
    </div>
</body>
</html>
```

**index.css**

```css
body {
    margin: 0;
}
.container {
    border: 3px solid #000;
}

.item-1 {
    background-color: #fff4e1;
    padding: 5px;
}

.item-2 {
    background-color: #ffebb7;
    padding: 5px;
}

.item-3 {
    background-color: #e67a7a;
    padding: 5px;
}
```

<figure><img src="../.gitbook/assets/container-setup.png" alt=""><figcaption><p>Container</p></figcaption></figure>

{% hint style="info" %}
Container and direct children can be any elements like \<ul>\<li> etc and not just div.&#x20;
{% endhint %}

## The flex container

To create a flex container, set display property to `flex` or `inline-flex`. Direct children turn into flex items

* Items display in a row from left to right by default
* Items will stretch to fill the size of the cross axis
* If there are more items than can fit in the container, they will not wrap but overflow by default

<figure><img src="../.gitbook/assets/flex-container.png" alt=""><figcaption><p>display:flex</p></figcaption></figure>

### flex-direction

Main axis is defined by `flex-direction` property and cross-axis runs perpendicular to it. It has four values

#### row

This is the default. Main axis runs in the row direction and elements are placed left to right as shown above

#### row-reverse

Main axis is still in the row direction but start/end lines are switched, so items will be placed right to left

<figure><img src="../.gitbook/assets/row-reverse.png" alt=""><figcaption><p>row-reverse</p></figcaption></figure>

#### column

Main axis runs in column direction and elements are placed from top to bottom

<figure><img src="../.gitbook/assets/column.png" alt=""><figcaption><p>column</p></figcaption></figure>

#### column-reverse

Main axis still runs in column direction but start/end lines are switched, so elements are placed from bottom to top

<figure><img src="../.gitbook/assets/column-reverse.png" alt=""><figcaption><p>column-reverse</p></figcaption></figure>
