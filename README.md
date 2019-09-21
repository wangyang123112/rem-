# rem-
1.媒体查询改变根元素的字体大小  2. js实现动态改变根元素的字体大小
```
!(function(doc, win) {
    var docEle = doc.documentElement,
        evt = "onorientationchange" in window ? "orientationchange" : "resize",
        fn = function() {
            var width = docEle.clientWidth;
            width = width < 320 ? 320 : width;
            width = width > 640 ? 640 : width;
            width && (docEle.style.fontSize = 100 * (width / 640) + "px");
        };
     
    win.addEventListener(evt, fn, false);
    doc.addEventListener("DOMContentLoaded", fn, false);
 
}(document, window));
```
```
/* 媒体查询以@media开头，然后后面可以跟上 判断的条件，比如：screen表示屏幕设备, and是并且的意思， min-width是最小宽度的意思。 */
@media screen and (min-width: 320px) {
    html {font-size: 50px;}
}
 
@media screen and (min-width: 360px) {
    html {font-size: 56.25px;}
}
 
@media screen and (min-width: 400px) {
    html {font-size: 62.5px;}
}
 
@media screen and (min-width: 440px) {
    html {font-size: 68.75px;}
}
 
@media screen and (min-width: 480px) {
    html {font-size: 75px;}
}
 
@media screen and (min-width: 640px) {
    html {font-size: 100px;}
}
```
