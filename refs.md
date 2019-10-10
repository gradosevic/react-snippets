## Using refs
```jsx
import React from 'react';

class Counter extends Component{
    constructor(props){
        super(props);
        this.inputElRef = React.createRef();
    }

    render(){
        return <div>
            <input ref={this.inputElRef} />
            //or use directly without constructor
            <input ref={(inputEl) => this.inputElement = inputEl} />
        </div>;
    }
    componentDidMount(){
        //Usage
        this.inputElRef.current.focus();
    }
}
export default Counter;
```
