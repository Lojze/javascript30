![audio](img/01audio.gif)

## 主题
    
    使用js键盘按下后播放对应按键的声音，并同时产生特效，在按下其他键的时候，之前的键和音取消

## 脑图

![01](img/01.png)

我把这个过程分解成几块，点击，修改，删除

1.  点击：使用keydown事件来监听用户的点击`window.addEventListener('keydown',fun)`。
函数用来处理修改的内容

2.  修改: `fun`函数中用来修改`border`，`播放音频` 这里需要注意的是class，有一个可以单独删除或添加的class。

3.  删除：点击之后删除之前的样式,点击下一个重置audio为0。这里的难点是如何监听动画播放完成？？


## JavaScript语法

### css 部分

1.  transition

>   定义动画速度效果,当我们修改了这个定义了`transition`都会触发这些效果，不论是后加的还是之前有的样式。
[transition 的属性](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)

`transition` 有四个属性，分别是`设置过度效果的css属性名称`,`完成过渡效果需要多少秒或毫秒`,`速度效果的速度曲线`,`过渡效果何时开始`。
*   `transition-property`:`none:默认，没有`,`all：所有属性都将获得过渡效果`,`property:定义应用过渡效果的 CSS 属性名称列表，列表以逗号分隔。`
*   `transition-duration`:规定完成过渡效果需要花费的时间（以秒或毫秒计）。默认值是 0，意味着不会有效果。
*   `transition-timing-function`:
    *   linear	规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。
    *   ease	规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。
    *   ease-in	规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。
    *   ease-out	规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。
    *   ease-in-out	规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。
    *   cubic-bezier(n,n,n,n)	在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。

*   `transition-delay`:规定在过渡效果开始之前需要等待的时间，以秒或毫秒计。
## 探索