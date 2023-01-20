# Setup from scratch

## Create project folder

```bash
mkdir learn-react
cd learn-react
```

## Initialize project

```shell
npm init
```

## Add project directories

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
```

### webpack.config.js

Add following to the rules

```json
{
  test: /\.css$/i,
  use: ["style-loader", "css-loader"],
}
```

