```jsx
import React from 'react';

//Relative path will be correctly resolved when using it this way
import logo from '../../logo.png';

const logo (props) => (
    <div>
      <img src={logo} alt="Logo" />
    </div>
);

export default logo;
```
