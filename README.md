# React Snippets

## Getting started

```javascript
npx create-react-app my-app
cd my-app
npm start
```
For more info: https://create-react-app.dev/docs/getting-started

```javascript
npm i create-react-app -g
create-react-app my-app
cd my-app
npm start
```


## SEO

Use HashRouter and React Helmet
```
react-router-dom
npm install react-helmet
```

# React Components

## Functional component

```jsx
import React from 'react';

const Person = (props) =>{
    return <div>
        <span>This is Person component.</span>
    </div>;
}
export default Person;


import React, { useState, useEffect } from 'react';

//useState & useEffect will fix the state issue
const Person = (props) =>{
    const [count, setCount] = useState(0);

    // Similar to componentDidMount and componentDidUpdate:
    useEffect(() => {
        // Update the document title using the browser API
        document.title = `You clicked ${count} times`;
    });

    return <div>
        <span>This is Person component.</span>
    </div>;
}
export default Person;
```

## Class-based components

```jsx
import React, { Component } from 'react';

class Animal extends Component{
    render(){
        return <div>Hello from animal!</div>;
    }
};

export default Animal;
```
