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
});
```
