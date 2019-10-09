## External file styles
Note: External styles are global. Make sure to add unique selectors

###Child.js
```jsx
import React, { Component } from 'react';

import './Child.css';

const Child = (props) =>{
    return <div className="child">
        <p>Child</p>
    </div>;
}
export default Child;
```

### Child.css
```jsx
.child{
    border: 1px solid gray;
    width: 100px;
    padding: 100px;
}
```

## Inline styles
Note: Inline styles are limited to JSX

```jsx
import React, { Component } from 'react';

const Child = (props) =>{
    const style = {
        border: '2px solid black',
        padding: 20,
        'max-width': 100
    };
    return <div style={style}>
        <p>Child</p>
    </div>;
}
export default Child;
```