## useState()
```jsx
import React, { useState } from 'react';

const exampleComponent = (props) => {
  const [ enteredTitle, setEnteredTitle ] = useState('');
  const [ enteredAmount, setEnteredAmount ] = useState('');
  return {
    <div>
      <input type="text" value={enteredTitle} onChange={event => {
        setEnteredTitle(event.target.value)
      }}/>
    </div>
  };
}
export default exampleComponent;
```
### handler
```jsx
import React, { useState } from 'react';

const exampleComponent = (props) => {
  const [ enteredTitle, setEnteredTitle ] = useState('');

  const addSomethingHandler = ingredient => {
    setEnteredTitle(prevTitle => [
      ...prevTitle,
      {id: Math.random().toString(), ...ingredient}
    ])
  const deleteSomethingHandler = ingredeintId => {
    setEnteredTitle(prevengridients => prevengridients.filter(ingredient => {
      ingredient.id !== ingredeintId
    }));
  };
  return {
    <div>
      <Component addSomething={addSomethingHandler} />
      <Component deleteSomething={deleteSomethingHandler} />
    </div>
  };
}
export default exampleComponent;
```
## useEffect()
```jsx
const Person = (props) =>{
    const [count, setCount] = useState(0);

    //Runs every time component re-renders
    useEffect(() => {
    });
     //Runs only once when component did mount. Pass an empty array
    useEffect(() => {
        
    }, []);
    useEffect(() => {
        //Limit calls to only when persons change
    }, [props.persons]);
   
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
