### map

```js
Array.prototype._map = function(fn) {
    const array = this;
    const result = [];
    array.forEach(item => {
        result.push(fn(item));
    })
    return result;
}
```



### filter

```js
Array.prototype._filter = function(fn) {
    const array = this;
    const result = [];
    array.forEach(item =>{
        if(fn(item)) {
            result.push(item)
        }
    })
    return result;
}
```



### reduce

```js
Array.prototype._reduce = function(fn, init) {
    let pre = init, i = 0;
    const array = this;
    if(pre === undefined) {
        pre = array[0];
        i = 1;
    }
    for(i; i < array.length; i++) {
        pre = fn(pre, array[i], i, array)
    }
    return pre;
}
```



### flat

```js
Array.prototype._flat = function() {
    const array = this;
    const isArray = data => Object.prototype.toString.call(data) === '[object Object]';
    const result = [];
    array.forEach(item => {
        if(isArray(item)) {
            result = result.concat(item._flat())
        } else {
            result.push(item)
        }
    })
    return result;
}
```

