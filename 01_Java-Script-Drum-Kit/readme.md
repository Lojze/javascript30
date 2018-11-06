![audio](img/01audio.gif)

## 主题
    
    使用js键盘按下后播放对应按键的声音，并同时产生特效，在按下其他键的时候，之前的键和音取消

## 脑图

![01](img/01.png)

我把这个过程分解成几块，点击，修改，删除

1.  点击：使用keydown事件来监听用户的点击`window.addEventListener('keydown',fun)`。
函数用来处理修改的内容

2.  修改: `fun`函数中用来修改`border`，`播放音频`

3.  删除：点击之后删除之前的样式,点击下一个重置audio为0


## JavaScript语法

## 探索