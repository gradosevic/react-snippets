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
