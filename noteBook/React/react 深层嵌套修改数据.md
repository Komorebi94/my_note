### react 深层嵌套修改数据

```js
const newArr = this.state.notificationList;
newArr[0]["setList"][0]['notifications'][0]['selected'] = true;
this.setState({
    notificationList: newArr
})
```

