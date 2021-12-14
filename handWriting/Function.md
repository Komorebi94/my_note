### call

```js
Function.prototype._call = function(context = window, ...args) {
    context.fn = this;
    const result = context.fn(...args);
    delete context.fn;
    return result;
}
```



### apply

```js
Function.prototype._apply = function(context = window, args) {
    context.fn = this;
    const result = args ? context.fn(...args) : context(fn);
    delete context.fn;
    return result;
}
```



### bind

```js
Function.prototype._bind = funciton(context = window, ...args) {
    const fn = this;
    function inner(...innerArgs) {
        const _ctx = this instanceof fn ? this : context;
        return fn.apply(_ctx, args.concat(innerArgs))
    }
    function Temp() {}
    Temp.prototype = fn.prototype;
    inner.prototype = new Temp();
    return inner;
}
```

