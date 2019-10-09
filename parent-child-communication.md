## Parent
```jsx
import React, { useState } from 'react';

import Child from './Child';

function ParentChild() {

    const [getName, setName] = useState('Default name');
    const onChangeHandler  = (event) => {
        setName(event.target.value);
    }
    return (
        <Child changed={onChangeHandler.bind(this)} name={getName} />
    );
}

export default ParentChild;

```

## Child
```jsx
import React, { Component } from 'react';

const Child = (props) =>{
    return <div>
        <p>Child: {props.name}</p>
        <input type="text" onChange={props.changed} />
    </div>;
}
export default Child;
```
