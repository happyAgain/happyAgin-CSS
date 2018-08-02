#### 页面某个模块的文字内容是动态的，可能是几个字，也可能是一句话。然后，希望文字少的时候居中显示，文字超过一行的时候居左显示。该如何实现？
```
<div class="box">
  <div class="inline-block">
    我是文案我是文案我是文案我是文案
  </div>
</div>
```
```
.box {
  width: 200px;
  padding: 20px;
  background: #ddd;
  text-align: center;
  .inline-block {
    display: inline-block;
    text-align: left;
  }
}
```
![image](https://raw.githubusercontent.com/happyAgain/happyAgin-CSS/master/inline-block/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202018-08-03%20%E4%B8%8A%E5%8D%881.48.01.png)
![image](https://raw.githubusercontent.com/happyAgain/happyAgin-CSS/master/inline-block/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202018-08-03%20%E4%B8%8A%E5%8D%881.48.28.png)

在inline-block元素为达到最大宽度时，他作为一个内联元素被box的text-align:center居中，当inline-block元素换行时，即已达到最大宽度时，又被自己的text-align:left居左
