#### 初始代码
```
<div class="father">
  <div class="son">
    我是子元素
  </div>
</div>
```
```
.father {
  background: #ddd;
  padding: 10px;
  .son {
    height: 100px;
    background: red;
  }
}
```
![image](https://raw.githubusercontent.com/happyAgain/happyAgin-CSS/master/clear-both/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202018-08-02%20%E4%B8%8A%E5%8D%881.00.46.png)

#### 我们为子元素添加float为left的属性
```
.father {
  background: #ddd;
  padding: 10px;
  .son {
    height: 100px;
    background: red;
    float: left;
  }
}
```
此时由于子元素脱离了文档流，父元素的高度塌陷。

![image](https://raw.githubusercontent.com/happyAgain/happyAgin-CSS/master/clear-both/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202018-08-02%20%E4%B8%8A%E5%8D%8812.58.10.png)

#### 在尾部增加额外块级元素，并清除浮动
```
.father {
  background: #ddd;
  padding: 10px;
  .son {
    height: 100px;
    background: red;
    float: left;
  }
  &:after {
    content: '';
    display: block;
    clear: both;
  }
}
```
此时我们通过在浮动元素后面增加块级元素，并给此元素增加clear:both的属性，父级元素的高度恢复了。

![image](https://raw.githubusercontent.com/happyAgain/happyAgin-CSS/master/clear-both/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202018-08-02%20%E4%B8%8A%E5%8D%881.00.46.png)

#### 那么为什么clear:both可以使父元素恢复塌陷的高度呢？
*在设置clear元素的上外边距之上增加清除空间，而外边距本身不改变 -- css2.1*

就是说，后面增加的块级元素通过clear这个属性，会把之前float元素所造成的塌陷高度重新加回到自己的外边距上，并且不会改变自己的外边距既margin的值。
