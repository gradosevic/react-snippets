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
import React, { useState, useEffect } from 'react';

class Counter extends Component{
    state = {
        count
    };

    render(){
        return <div>
            <p>You clicked {this.state.count} times</p>
            <button onClick={() => this.setState({count: count + 1})}>
                Click me
            </button>
        </div>;
    }
}
export default Counter;
```
