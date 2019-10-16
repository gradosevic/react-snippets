Component > Action > Reducer > Store >(triggers component subscriptions) Subscription >(passes data as updated props) Component
Reducer changes store directly syncronysly

### Working Redux example
```jsx
const redux = require('redux');
const createStore = redux.createStore;

const initialState = {
  count: 0
};

const rootReducer = (state = initialState, action) => {
    if(action.type === 'INC_COUNTER'){
        return {
            ...state,
            count: state.count + 1
        }
    }
    if(action.type === 'ADD_COUNTER'){
        return {
            ...state,
            count: (state.count + action.value)
        }
    }
    return state;
}

const store = createStore(rootReducer);
console.log('state',store.getState());

//Subscriptions
store.subscribe(() => {
    console.log('subsc', store.getState());
});

//Actions
store.dispatch({type: 'INC_COUNTER'});
store.dispatch({type: 'ADD_COUNTER', value: 10});

console.log('state',store.getState());
```
