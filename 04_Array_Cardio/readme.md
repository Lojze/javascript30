## 主题
    
    打印结果


## JavaScript语法

### filter(callback[, thisArg])

#### 参数
`callback`：用来测试数组的每个元素的函数。调用时使用参数 (element, index, array)。返回true表示保留该元素（通过测试），false则不保留。
`thisArg`：可选。执行 callback 时的用于 this 的值。

`callback `被调用时传入三个参数：元素的值，元素的索引，被遍历filter的数组
返回为true的结果

[array-MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)


### array.map(callback[, thisArg])

#### 参数

`callback`

原数组中的元素调用该方法后返回一个新数组。它接收三个参数，分别为 `currentValue`、`index`、`array`。

`currentValue`

callback的第一个参数，数组中当前被传递的元素。

`index`

callback的第二个参数，数组中当前被传递的元素的索引。

`array`

callback的第三个参数，调用map()方法的数组，即原数组。

`thisArg`

执行callback函数时this指向的对象。


`map`:与下面的`forEach`挺相似的，只是`map`不会修改原数组。
引用一段找到的资料:
>   `map`方法体现的是数据不可变的思想。该思想认为所有的数据都是不能改变的，只能通过生成新的数据来达到修改的目的，因此直接对数组元素或对象属性进行操作的行为都是不可取的。这种思想其实有很多好处，最直接的就是避免了数据的隐式修改。`immutable.js`是实现数据不可变的一个库，可通过专属的API对引用类型进行操作，每次形成一个新的对象。

>   但具体到项目中还是要看团队的要求，都用或者都不用。单单局部使用是没有效果的。

>   如果使用了`React` + `Redux` 的技术栈，是比较推荐使用的

>   另外有一点，`forEach`和`map`还存在一个编程思想的区别，前者是命令式编程，后者是声明式编程，如果项目的风格是声明式的，比如`React`，那么后者显然更统一。

### arrayObject.sort(sortby)

#### 参数 

*   sortby：可选，规定排序顺序，必须是函数。

>   这里有个疑问，当我们传入参数的时候会按照Unicode字符集中的顺序进行排序，最终的结果与我们期盼的不同。大多数我们会传入一个函数来声明排序的方式。

```
function arr(a,b){
    if(a < b){
        return 1;
    }else if(a > b){
        return -1
    }else{
        return 0
    }
}
上面的判断 当返回1 的时候 执行交换 这样就会把 b放在a的前面,从大到小排序

let list = [1,2,3,20,33,44,0,4,45]
list.sort(arr)

// [45, 44, 33, 20, 4, 3, 2, 1, 0]

还可以简写为
function arr(a,b){
    return b - a;
}

```
>   对象的处理其实与数组的采用的方式处理相同 第5第6例子

sort底层实现代码：
[chromium-v8引擎 array.js  710行开始](https://github.com/v8/v8/blob/ad82a40509c5b5b4680d4299c8f08d6c6d31af3c/src/js/array.js)


###  arr.reduce(callback[, initialValue])

#### 参数

    callback
        执行数组中每个值的函数，包含四个参数：

    accumulator
        累计器累计回调的返回值; 它是上一次调用回调时返回的累积值，或initialValue（见于下方）。

    currentValue
        数组中正在处理的元素。

    currentIndex可选
        数组中正在处理的当前元素的索引。 如果提供了initialValue，则起始索引号为0，否则为1。

    array可选
        调用reduce()的数组

    initialValue可选
        作为第一次调用 callback函数时的第一个参数的值。 如果没有提供初始值，则将使用数组中的第一个元素。 在没有初始值的空数组上调用 reduce 将报错。

>   之前一直把`reduce`当成一个计数的函数来使用，直到做例子8，发现他用来做统计数学方便非常的方便。
