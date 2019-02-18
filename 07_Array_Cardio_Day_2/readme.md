
## 主题
    
    使用循环的方式找结果

## 语法

`some`和`find`基本上差不多，经常使用`forEach`，`map`大概的语法应该也猜的出来，

需要注意的是`some`只会返回为`true`的结果，当然它只会返回第一个。
`every`只要没有找到一个，就会返回`false`，全部找到才会返回`true`


`find`和`findIndex`

find:返回找到元素的第一个
findIndex：返回找到元素的位置

删除元素
`splice` 和  `slice`使用它们

`splice`不会修改原数组，他接受3个参数，位置，删除的数量，和原数组。

`slice`：它接受两个参数，开始位置和结束位置
```
const newComments = [
    ...comments.slice(0, index),
    ...comments.slice(index + 1)
];
```
这里面的三个点是 `ES6 中的扩展语法`

