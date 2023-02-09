# Class Components

## Simple Class Component

```jsx
import React from "react"

export default class Greeting extends React.Component {
    render() {
        // Other logic can go here
        return (
            <p>Welcome, {this.props.username}</p>
        )
    }
}
```

## Converting to Class Component

### Function Component

```jsx
import React from "react"

export default function App() {
    const [count, setCount] = React.useState(0)
    
    function add() {
        setCount(prevCount => prevCount + 1)
    }
    
    function subtract() {
        setCount(prevCount => prevCount - 1)
    }
    
    return (
        <div className="counter">
            <button className="counter--minus" onClick={subtract}>–</button>
            <div className="counter--count">
                <h1>{count}</h1>
            </div>
            <button className="counter--plus" onClick={add}>+</button>
        </div>
    )
}

```

### Class component

* Change function keyword to class and extend React.Component
* State is defined as an object and setState is used to update it
* Functions don't need function keyword
* Use render method. State and function need to be referred by this

```jsx
import React from "react"

export default class App extends React.Component {
    state = {
        count: 0
    }
    
    add = () => {
        this.setState(prevState => ({count: prevState.count + 1}))
    }
    
    subtract = () => {
        this.setState(prevState => ({count: prevState.count - 1}))
    }
    
    render() {
        return (
            <div className="counter">
                <button className="counter--minus" onClick={this.subtract}>–</button>
                <div className="counter--count">
                    <h1>{this.state.count}</h1>
                </div>
                <button className="counter--plus" onClick={this.add}>+</button>
            </div>
        )
    }
}
ea
```
