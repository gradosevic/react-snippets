```jsx
import React, { Component } from 'react';

class Conditions extends Component{
    state = {
        showSomething: true
    };
    render(){
        let checkOutside = '';
        if(this.state.showSomething){
            checkOutside = <p>Checked outside of return expression</p>;
        }
        return <div>
            {this.state.showSomething ? <p>Show if</p>:''}
            <p>Show always</p>
            {!this.state.showSomething ? <p>Show if</p>:<p>Show if not true</p>}
            {checkOutside}
        </div>
    }
}

export default Conditions;
```
