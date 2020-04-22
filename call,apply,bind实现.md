## call,apply,bind代码实现思路

### call实现代码方案及思路
    思路
       a. 获取执行函数实例this,并将其绑定到所传的作用域context上。
       b. 执行函数。
       c. 删除context上的函数。防止误修改原作用域，重要。
       d. return返回值。

```
Function.prototype.myCall = function(){
    const [context, ...params] = arguments;
    context.fn = this;
    let result = context.fn(...params);
    delete context.fn;
    return result;
}
```
