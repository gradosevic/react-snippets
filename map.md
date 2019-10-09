```jsx
import React, { useState } from 'react';

import Child from './Child';

function App() {
  const children = [
    {
      name: 'Matt',
      age: 12
    },
    {
      name: 'Alice',
      age: 6
    }
  ];
  return (
    <div className="App">
      {children.map((child) => {
        return <Child name={child.name} age={child.age} />;
      })}
    </div>
  );
}

export default App;

```

```jsx
import React, { Component } from 'react';

const Child = (props) =>{
    return <div>
        <p><strong>Child name: {props.name}</strong></p>
        <p>Age: {props.age}</p>
    </div>;
}
export default Child;
```
