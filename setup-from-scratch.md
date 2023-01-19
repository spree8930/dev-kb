# Setup from scratch

## Initialize project

```shell
mkdir learn-react
cd learn-react
npm init -y
```

### Add project directories

```shell
mkdir public src
```

## Initialize repository

<pre class="language-bash"><code class="lang-bash">git init
<strong>touch .gitignore
</strong></code></pre>

### .gitignore

```
node_modules
```

## Install dependencies

```shell
npm install --save-dev @babel/core @babel/cli @babel/preset-env @babel/preset-react
npm install --save-dev webpack webpack-cli webpack-dev-server babel-loader
npm install react react-dom
```

## Configuration

```shell
touch webpack.config.js
touch babel.config.json
```

### webpack.config.js

```javascript
const path = require('path');
module.exports = {
    entry: './src/index.js',
    mode: 'development',
    output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'public'),
    },
    module: {
        rules: [
            {
                loader: 'babel-loader',
                test: /\.js$/,
                exclude: /node_modules/
            }
        ]
    },
    devServer: {
        static: {
            directory: path.join(__dirname, 'public'),
        }
    }
}
```

### babel.config.json

```json
{
    "presets": [
        "@babel/preset-env",
        "@babel/preset-react"
    ]
}
```

## Code

```shell
touch public/index.html
touch src/index.js
```

### index.html

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Learn React</title>
    </head>
    <body>
        <div id="root"></div>
    </body>
    <script src="bundle.js"></script>
</html>
```

### index.js

```javascript
import React from "react";
import ReactDOM from "react-dom/client";

const App = () => {
    return (
        <div>
            Hello World
       </div>
    )
}

const container = document.getElementById('root');
const root = ReactDOM.createRoot(container);
root.render(<App />);
```

## Running the project

Update package.json to include following scripts:

```json
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack",
    "start": "webpack serve",
    "watch": "webpack --watch"
  }
```

Run following to access the app at localhost:8080

```shell
npm run build
npm run start
```

## Adding CSS

```
npm install --save-dev css-loader style-loader
touch src/index.css
```

### webpack.config.js

Add following to the rules

```json
{
  test: /\.css$/i,
  use: ["style-loader", "css-loader"],
}
```

### index.css

```css
body {
    background: #d7f0f3;
}
```

### index.js

```javascript
// import css file
import './index.css'
```

## Add images

```
npm install file-loader --save-dev
touch src/images
```

### webpack.config.js

Add following to the rules:

```json
{
  test: /\.(png|jpe?g|gif)$/i,
  use: [
   {
     loader: 'file-loader',
   },
  ],
}
```

### index.js

```
// import image
import logo from "./images/logo.jpg";
...
<img className="logo" src={logo}></img>
```

## Add SASS

```
npm install sass-loader sass webpack --save-dev
```

### webpack.config.js

Update the css rule as follows:

```
{
  test: /\.s[ac]ss$/i,
  use: ["style-loader", "css-loader", "sass-loader"],
}
```

### index.scss

```css
$bg-color: #d7f0f3;
body {
    background: $bg-color;
}
```

### index.js

```
import './index.scss'
```
