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
