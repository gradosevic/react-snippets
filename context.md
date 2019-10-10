```jsx
import React from 'react';
const authContext = React.createContext({
    authenticated: false
});
```

```jsx
import React from 'react';
import AuthContext from './auth-context';

class Counter extends Component{
    static contextType = AuthContext;
    render(){
        return <div>
        {this.context.authenticated? 'yes':'no'}
        </div>;
    }
    componentDidMount(){
        console.log(this.context.authenticated);
    }
}
export default Counter;
```

```jsx
import React, {useEffect, useContext} from 'react';
import AuthContext from './auth-context';

const counter = (props) => {
    
    const authContext = useContext(AuthContext);
    
    return(
        <div>{authContext.authenticated}</div>
    );
};
export default counter;
```
