```jsx
import React, { Component } from 'react';

class Conditions extends Component{
    state = {
        showSomething: true
    }
    render(){
        return <div>
            {this.state.showSomething ? <p>Show if</p>:''}
            <p>Show always</p>
            {!this.state.showSomething ? <p>Show if</p>:<p>Show if not true</p>}
        </div>
    }
}

export default Conditions;
```
