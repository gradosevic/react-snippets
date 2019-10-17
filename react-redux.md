First, install react-redux
```jsx
npm i react-redux --save
```

## Example index.js
```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import { createStore } from 'redux';
import { Provider } from 'react-redux';

import reducer from './store/reducer';

const store = createStore(reducer);

ReactDOM.render(
    <Provider store={store}>
        <App />
    </Provider>, document.getElementById('root'));
```
## Example /store/reducer.js
```jsx
const inititalState = {
  counter: 0
};
const reducer = (state = inititalState, action) => {
  if(action.type == 'INCREMENT'){
    return {
      ..state,
      counter: state.counter+1
    }
  }
  if(action.type === 'MULTIPLY_COUNTER'){
        return {
            ...state,
            count: (state.count * action.by)
        }
    }
  return state;
}
export default reducer;
```

## Example Counter.js container
```jsx
//In container component
import { connect } from 'react-redux';

//Link class container
class Counter extends Component {
  render(){
    return {
      <button onClick={this.props.onIncrementCounter} value={this.props.ctr}></button>
    }
  }
}

//think about state that you want to get and
//actions that you want to dispatch

const mapStateToProps = state => {
  return {
    ctr: state.counter
  };
};

const mapDispatchToProp = dispatch => {
  return {
    onIncrementCounter: () => dispatch({type: 'INCREMENT'}),
    multiplyBy: () => dispatch({type: 'MULTIPLY_COUNTER', by: 10})
  };
}

export default connect(mapStateToProps, mapDispatchToProp)(Counter);

```

## Updating immutable
```jsx
//Updating an array e.g. results = []
const id = 2;
newArray = [...state.results];
newArray.splice(id, 1);
return {
    ...state,
    results: newArray
}

//make a copy using filter 
const newArrayCopy = state.results.filter(result => true);
const filteredArray = state.results.filter((result, index) => index !== id);

```
for more:
https://redux.js.org/recipes/structuring-reducers/immutable-update-patterns

### Extracted action types
## actions.js
```jsx
export const INCREMENT = 'INCREMENT';
export const DECREMENT = 'DECREMENT';

```

## Action consumer
```jsx 
import * as actionTypes from './actions'

switch(action):
    case actionTypes.INCREMENT
        //do stuff
```
