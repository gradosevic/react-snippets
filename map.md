```jsx
import React, { Component } from 'react';

import Child from './components/Person/Person';

class Program extends Component {
    state = {
        children: [
            {
                name: 'Matt',
                age: 12
            },
            {
                name: 'Alice',
                age: 6
            }
        ]
    };
    onRemoveHandler = (index)=>{
        let children = [...this.state.children]; //copy without mutating original value
        //use {...item} for objects, e.g. let child = {...this.state.children[index]}
        this.state.children.splice(index, 1);
        this.setState(children);
    }
    render(){
        return (
            <div>
                {this.state.children.map((child, index) => {
                    return <Child
                        key={index} //Note: index is not the best solution since the whole list
                        //will be rerendered with new indexes after update. Use custom id instead
                        name={child.name}
                        age={child.age}
                        remove={()=>this.onRemoveHandler(index)}
                        />;
                })}
            </div>
        );
    }

}

export default Program;


```

```jsx
import React, { Component } from 'react';

const Child = (props) =>{
    return <div>
        <p onClick={props.remove}><strong>Child name: {props.name}</strong></p>
        <p>Age: {props.age}</p>
    </div>;
}
export default Child;
```
