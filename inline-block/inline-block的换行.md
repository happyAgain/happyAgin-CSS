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
