### Ajax request with axios
```jsx
componentDidMount(){
    axios.get('/posts')
        .then(response => (
             console.log(response);
        ));
}
```
