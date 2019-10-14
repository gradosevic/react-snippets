## Using state in functional components

```jsx
import React, { useState, useEffect } from 'react';

const Counter = (props) =>{
    const [count, setCount] = useState(0);

    return <div>
        <p>You clicked {count} times</p>
        <button onClick={() => setCount(count + 1)}>
            Click me
        </button>
    </div>;
}
export default Counter;
```

## Using state in class components

```jsx
import React from 'react';

class Counter extends Component{
    state = {
        count
    };

    render(){
        return <div>
            <p>You clicked {this.state.count} times</p>
            <button onClick={() => this.setState({count: this.state.count + 1})}>
                Click me
            </button>
        </div>;
    }
}
export default Counter;
```

### A better way to update state

```jsx
this.setState((prevState, props) => {
	return {
		persons: persons,
		count: prevState.count + 1
	}
});
```
```jsx
//immutable way of using state
const options = {...this.state.options};
options[something] = newValue;
```
### Set a new state in dependance of the old state
```jsx
this.setState((prevState) => {
	return {something: !prevState};
});
```
