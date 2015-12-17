## 缘由

＝ ＝ ，当然起因是公司的项目的一个需求，然后在网上一顿乱找，感觉都不太合适，然后抽了几个小时时间自己干了一个。使用了一段时间后，感觉还不错，简单封装成jQuery插件，就拿出来分享了，希望给需要的人节省造轮子的时间。

如在使用期间出现bug，请在下面给出的Github中反馈。

### Github

Github:[https://github.com/AxeMea/iFreeLayer](https://github.com/AxeMea/iFreeLayer.js)

Demo:[链接](http://axemea.github.io/javascripts/move-container/move.html)

blog：[链接](http://axemea.github.io/javascript/2015/12/17/move-layer-plugin.html)

### 使用方法

####html结构

html的基础结构如下。

```html
  <div class="container">
	<div class="move-box">
		<section  class="block border top" data-dir="1"></section>
		<section  class="block cross right-top" data-dir="2"></section>
		<section  class="block border right" data-dir="3"></section>
		<section  class="block cross right-bottom" data-dir="4"></section>
		<section  class="block border bottom" data-dir="5"></section>
		<section  class="block cross left-bottom" data-dir="6"></section>
		<section  class="block border left" data-dir="7"></section>
		<section  class="block cross left-top" data-dir="8"></section>
	</div>
</div>
```

html代码中，有两个点是强制要有的。

* data-dir属性，代表8个可操作区域的标志。1－8，代表从上开始，顺时针的顺序。
* className中的block。其他的样式为demo样式，根据实际的设计稿进行相应的定制。


####引用脚本

```javascript
  <script type="text/javascript" src="http://cdn.bootcss.com/jquery/3.0.0-alpha1/jquery.min.js"></script>
  <script type="text/javascript" src="https://rawgit.com/axemea/iFreeLayer.js/master/iFreeLayer.min.js"></script>
```

####初始化

```javascript
$('.move-box').iFreeLayer({
      parent:'.container'
    }).setup();
```

初始化方法只有parent一个可选参数，代表浮动层的可移动区域，也代表它的父节点，如果不配置默认情况下为window。
