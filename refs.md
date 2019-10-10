## Using refs in class-based Components
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

## Using refs in functional components

```jsx
import React, {useEffect, useRef} from 'react';

const counter = (props) => {
    
    const toggleBtnRef = useRef(null);
    
    useEffect(() => {
        toggleBtnRef.current.click();
    },[]);
    
    return(
        <button ref={toggleBtnRef} />
    );
};
export default counter;
```
