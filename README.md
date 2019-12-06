**问: 什么是海报分享?**
答: 就是保存一张图片到手机相册, 这个图片带有自定义内容比如二维码, 文字等; 

**问: 如何实现二维码插入到图片?**
答: 用Canvas绘图; 首先用Canvas新建画布, canvas能把图片插到画布上,再把二维码,文字插到画布上;


# 就这样? No!!! 需要注意两点!!!

**第一点:  canvas保存到本地, 图片会压缩.**
**解决办法:** 放大画布(图片), 比如你最终要保存iphone5(大小320*568)的图片, 就新建一个640*1136的画(也即是乘以2倍), 这样保存到本地就清晰了;

**第二点:  根据第一点放大图后, 开发是640*1136图, 页面显示不下, 这时候就要对图片缩放, 其中zoom和scale可以缩小图片(如: zoom:40%), 但是zoom和scale这两个参数在手机上是无效的, 仅微信开发工具有效!!! 这点请知晓.**
**解决办法:**  开发中画图的时候用zoom/scale缩小画布, 调试好文字和二维码显示在图片上的位置后, 把画布浮动隐藏起来(position:absolute; left: -9999px); 然后用正常的css布局一个页面(用来给用户看), 也就是做两个, canvas做的图片是要保存到本地的, 而利用css定位做的布局是手机中给用户看的;

教程链接: https://blog.csdn.net/qq_40259641/article/details/103420015