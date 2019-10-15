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
import { Route, Link, NavLink, Switch, Redirect } from 'react-router-dom';
...
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

### Content & Components

```jsx
<Route path="/" exact component={ExampleComponent} />
<Route path="/relative" >Relative page</Route>
<Route path="/:id" exact component={ExampleComponent} />
<Switch>//Use Switch when there are multiple route matches. only first matched will be used
    <Route path="/something" exact component={ExampleComponent} />
    <Route path="/:id" exact component={ExampleComponent} />
</Switch>

//Nested routes, use first part dynamically e.g. /posts/id, /old-posts/id
<Route path={this.props.match.url + '/:id'} exact component={ExampleComponent} />
```

### Search Query

```jsx
<Link to="/my-path?start=5">Go to Start</Link>
//get it from props.location.search. this will return e.g. start=5

//to get the param use this snippet
componentDidMount() {
    const query = new URLSearchParams(this.props.location.search);
    for (let param of query.entries()) {
        console.log(param); // yields ['start', '5']
    }
}
```

### Redirect

```jsx
<Redirect from="/" to="/posts" />

//conditionaly
if(this.state.submitted){
    redirect = <Redirect to="/posts" />
}
...
//Use in render method
{redirect}
```
