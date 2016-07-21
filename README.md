Android 屏幕适配方案，这篇博客以Web页面设计引出一种适配方案，最终的目的就是可以通过百分比控制控件的大小。当然了，存在一些问题，比如：

    对于没有考虑到屏幕尺寸，可能会出现意外的情况；
    apk的大小会增加；

当然了android-percent-support这个库，基本可以解决上述问题，是不是有点小激动，稍等，我们先描述下这个support-lib。

这个库提供了：

    两种布局供大家使用：
    PercentRelativeLayout、PercentFrameLayout，通过名字就可以看出，这是继承自FrameLayout和RelativeLayout两个容器类；

    支持的属性有：

layout_widthPercent、layout_heightPercent、
layout_marginPercent、layout_marginLeftPercent、
layout_marginTopPercent、layout_marginRightPercent、
layout_marginBottomPercent、layout_marginStartPercent、layout_marginEndPercent。

可以看到支持宽高，以及margin。

也就是说，大家只要在开发过程中使用PercentRelativeLayout、PercentFrameLayout替换FrameLayout、RelativeLayout即可。

是不是很简单，不过貌似没有LinearLayout，有人会说LinearLayout有weight属性呀。但是，weight属性只能支持一个方向呀~~哈，没事，刚好给我们一个机会去自定义一个PercentLinearLayout。

好了，本文分为3个部分：

    PercentRelativeLayout、PercentFrameLayout的使用
    对上述控件源码分析
    自定义PercentLinearLayout
