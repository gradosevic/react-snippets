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

//////////////////////////////////////////////////
//In ./store/reducer.js
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
  return state;
}
export default reducer;
//////////////////////////////////////////////////
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
    onIncrementCounter: dispatch({type: 'INCREMENT'}) 
  };
}

export default connect(mapStateToProps, mapDispatchToProp)(Counter);

```



