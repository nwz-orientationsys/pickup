# html中为flash生成一个鼠标点击事件

最近在做一个项目，需要记录网页上的媒体播入事件。

以下是网上找到的两种解决方案。

两种方法的前面都一样：
```
<!-- 1.设置FLASH为底层 -->
<div style="position:absolute; left:0px; top:0px; width:800px; height:600px; z-index:-1"> 
  <object classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000" 
   codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,29,0" 
   width="800" height="600">
    <param name="movie" value="media.swf">
    <param name="quality" value="high">
    <!--2.必须把FLASH设置为透明，如果不设置的话，别的图片是不能够覆盖该flash的，也就不能够实现鼠标点击事件-->
    <param name="wmode" value="transparent"> 
    <embed src="media.swf" quality="high" pluginspage="http://www.macromedia.com/go/getflashplayer" 
      type="application/x-shockwave-flash" width="200" height="115"></embed>
  </object> 
</div>
``` 

这是flash的显示，主要为注释部分，flash的显示级别比较高，必须将它设置为底层显示；显示方式也必须设置为透明，否则也没有效果（不管是方法一还是方法二）。

### 方法1：
用photoshop做一个空的图片，里面没有任何内容，如kong.gif，覆盖到flash上方。
 ```
   <div id=gg1 style="position:absolute; left:0px; top:0px; width:800px; height:600px; z-index:1">
      <img onClick="toantherUrl()" src="kong.gif"/>
   </div>
```

### 方法2：
任意加一张图片，但是要设置其透明度为0，即该图片确实存在，但是把它透明化，不让用户看到（与方法1异曲同工）
```   
   <div id=gg1 style="position:absolute; left:0px; top:0px; width:800px; height:600px; z-index:1; 
     filter:Alpha(Opacity=0)"><!-- filter是设置透明度，如果为0则全透明，100为全显示 -->
      <img onClick="toantherUrl()" src="any.jpg"/>
   </div>
```   
这样flash能够正常显示，鼠标事件也能够正常响应，当然，看起来像是点击了flash，其实点击的覆盖在上面的图片，曲线救国，呵呵。

两种方法都是使用了另外一张图片来实现flash的点击事件，需要注意的地方是：
* flash必须设置参数wmode为transparent；
* 图片要覆盖在flash的上方；
* 不管是方法1还是方法2都必须使图片透明化，不遮盖flash。 

<br />
<br />

[原文链接](https://blog.csdn.net/slowlifes/article/details/7358735)
