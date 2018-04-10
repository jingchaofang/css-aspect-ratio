# css-aspect-ratio

css aspect ratio 长宽比 纵横比

纵横比分为固定纵横比和自适应纵横比

基于width的百分比来设置padding百分比值，把这种方式称之为固定纵横比。一般我们通过width的百分比来计算padding-top或padding-bottom的百分比值，其计算公式如下

```
padding-top = (元素高度 / 元素宽度) * 100%
padding-bottom = (元素高度 / 元素宽度) * 100%
```

```less
.fixed-aspect-rations(@height, @width) {
    padding-bottom: @height / @width * 100%;
    // 或者
    padding-top: @height / @width * 100%;
}
```

```
.container {
    position: relative;
    width: 100%;
    height: 0;
    padding-top: 56.25% // 9 / 16 * 100%
}
.embed {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
```

```
.container {
    position: relative;
    width: 75%;
    &:before {
        content: "";
        display: block;
        width: 100%;
        padding-top: 56.25%;
    }
}
```

纵横比例新方案，采用CSS Grid的方式来处理固定纵横比例


## Related

▲[CSS实现长宽比的几种方案 2017-07-05](https://www.w3cplus.com/css/aspect-ratio.html)

▲[容器长宽比 2017-06-16](https://www.w3cplus.com/css/aspect-ratio-boxes.html)

▲[Web中如何实现纵横比 2017-05-12](https://www.w3cplus.com/css/experiments-in-fixed-aspect-ratios.html)

[Web中内嵌内容实现响应式效果 2014-03-02](https://www.w3cplus.com/responsive/making-embedded-content-work-in-responsive-design.html)

[Making Embedded Content Work In A Responsive iFrame 2014-02-27](https://mobile.smashingmagazine.com/2014/02/making-embedded-content-work-in-responsive-design/)

[embedresponsively.com](http://embedresponsively.com/)

[Using FluidVids.js](https://gomakethings.com/using-fluidvids-js/)

[fluidvids](https://github.com/toddmotto/fluidvids/)

[Flexible Images 2014-01-16](https://www.w3cplus.com/css/flexible-images.html)

[Aspect Ratio Boxes 2017-06-08](https://css-tricks.com/aspect-ratio-boxes/)

[Creating Intrinsic Ratios for Video 2009-05-26](http://alistapart.com/article/creating-intrinsic-ratios-for-video)

[Responsive background images with fixed or fluid aspect ratios 2012-11-06](https://voormedia.com/blog/2012/11/responsive-background-images-with-fixed-or-fluid-aspect-ratios)

[Flexible CSS cover images 2014-01-08](http://nicolasgallagher.com/flexible-css-cover-images/)

[CSS3 Object-fit和Object-position 2013-12-02](https://www.w3cplus.com/css3/css3-object-fit-and-object-position-properties.html)

[热门：响应图片(Responsive Images)技术简介 张鑫旭 2012-02-15](http://www.zhangxinxu.com/wordpress/2012/02/responsive-images-introduce/)
