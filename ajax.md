### Ajax request with axios
```jsx
componentDidMount(){
    axios.get('/posts')
        .then(response => (
             console.log(response);
        ))
        .catch(error =>(
             this.setState({error: true});
        ));
}
```

### Register interceptor
```jsx
import axios from 'axios';

axios.interceptors.request.use(request => {
    console.log(request);
    return request;
},
    error => (
        console.log(error); 
        return Promise.reject(error);
));

//Same for response
axios.interceptors.response.use(response => {
    console.log(response);
    return response;
},
    error => (
        console.log(error); 
        return Promise.reject(error);
));
```

### Setting global configuration

```jsx
axios.defaults.baseUrl = 'http://example.com';
axios.defaults.headers.common[Authorization] = 'api token';
axios.defaults.headers.post['Content-Type'] = 'application/json';

```
