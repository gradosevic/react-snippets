## External file styles
Note: External styles are global. Make sure to add unique selectors

### Child.js
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

## Use CSS classess in array
```jsx
const classes = [];
classes.push('red');
classes.push('bold');
return(
    <div className={classess}
);
```

## Use Radium
```jsx
//Install
npm install radium --save

//wrap App
import Radium from 'radium';
export default Radium(App);

//Use Radium
const style = {
    color: 'red',
    ':hover':{ //radium hover selector
        'color': 'blue'
    },
    '@media (min-width: 500px)': { //radium media queries
        color: 'green'
    }
}

//Note: For media queries we need to wrap our app like this
import Radium, { StyleRoot } from 'radium';
return (
    <StyleRoot><div className="App"></div></StyleRoot>;
);
```

## More...
Check out CSS modules for more

https://github.com/css-modules/css-modules

https://medium.com/nulogy/how-to-use-css-modules-with-create-react-app-9e44bec2b5c2

https://github.com/css-modules/css-modules
