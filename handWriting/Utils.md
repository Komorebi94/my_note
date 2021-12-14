### debounce

```js
function debounce(fn, delay, immediately) {
    let timer = null;
    return (...innerArgs) => {
        timer && clearTimeout(timer);
        if(immediately) {
            let run = !timer;
            timer = setTimeout(() => {
                timer = null;
            }, delay);
            run && fn.apply(this, innerArgs);
        } else {
            timer = setTimeout(() => {
                timer = null;
                fn.apply(this, innerArgs)
            }, delay)
        }
    }
}
```



### throttle

```js
function throttle(fn, delay) {
    let flag = true;
    return (...innerArgs) => {
        if(!flag) return;
        flag = false;
        setTimeout(() => {
            fn.apply(this, innerArgs);
            flag = true;
        }, delay)
    }
}
```



### unique

```js
function unique(arr) {
    return arr.reduce((acc, cur) => {
        return acc.includes(cur) ? acc : [...acc, cur]
    },[])
}

function unique2(arr) {
    const map = new Map();
    return arr.reduce((acc, cur) => {
        const value = map.get(cur);
        if(value) {
            return acc;
        } else {
            map.set(cur, cur);
            return [...acc, cur]
        }
    },[])
}
```

