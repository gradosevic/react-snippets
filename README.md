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
    useEffect(() => {
        //Limit calls to only when persons change
    }, [props.persons]);
    useEffect(() => {
        //Runs only once when component did mount. Pass an empty array
    }, []);
    useEffect(() => {
        //For component unmount, return a function
	//pass [] to run on every update cylcle
	//don't pass anything to run on component destroy
	return () => { console.log('component unmounted') };
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
    constructor(props){
	super(props);
	//to set initial state based on props, use contructor
    }
    getDerivedStateFromProps(props, state){
	//do not use it
	//it could be useful in rear situations
    }
    render(){
        return <div>
        <p>Hello from animal!</p>
        {props.children} //adds content between tags sent from parent
        </div>;
    }
    //rendered child components after render()
    componentDidMount(){
	//don't set state here
    }
    getSnapshotBeforeUpdate(){

    }
    componentDidCatch(){

    }
    componentWillUnmount(){

    }
    shouldComponentUpdate(){

    }
    componentDidUpdate(){

    }
}

export default Animal;
```

## Update lifecycle

```jsx
getDerivedStateFromProps(props, state)
shouldComponentUpdate(nextProps, nextState) //we can cancel update process here! (return false)
render()
//update child components
getSnapshotBeforeUpdate(prevProps, prevState)
componentDidUpdate() //you can make http requests here, just don't update state!

//getSnapshotBeforeUpdate can pass some data to componentDidUpdate, e.g.
getSnapshotBeforeUpdate(prevProps, prevState){
	return {message: "m"};
}
componentDidUpdate(prevProps, prevState, snapshot);

```
