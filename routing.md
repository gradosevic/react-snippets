```npm
npm i --save react-router react-router-dom
```
//Note: only react-router-dom is used, it's wrapper for react-router that is used as a dependency


First, wrap the app with the BrowserRouter component
```jsx
import { BrowserRouter } from 'react-router-dom';

ReactDOM.render(
    <BrowserRouter>
        <App />
    </BrowserRouter>, document.getElementById('root'));
```

### Links

```jsx
<ul>
    <li>
        <NavLink to="/">Home</NavLink>
        <NavLink to={{
            pathname: '/new-post',
            hash: '#submit',
            search: '?q=true',
            activeClassName: "active"
        }}>New Post</NavLink>
        <Link to="relative">Relative</Link>
        <a href="https://example.com/external" target="_blank">External</a>
    </li>
</ul>
```

### Components

```jsx
<Route path="/" exact component={ExampleComponent} />
<Route path="/relative" >Relative page</Route>
<Route path="/:id" exact component={ExampleComponent} />
```
