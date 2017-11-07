
iOS 11
=======

这里总结了大家iOS 11，iPhone X 适配问题
-------------------------------------

#点击右上角的 star、watch 按钮，可以收藏本仓库，看到本仓库的更新！
     

iOS 11适配
---------

[简书App适配iOS 11](http://www.jianshu.com/p/26fc39135c34)  
 
[掘金客户端适配iOS11简单记录](https://juejin.im/entry/59bb92ab6fb9a00a681ac051)
 
[iOS 11 安全区域适配总结](http://mp.weixin.qq.com/s/W1_0VrchCO50owhJNmJnuQ)
 
[iOS开发-适配iOS 11](http://www.jianshu.com/p/a356b2ed4ceb)

[适配iOS11&iPhoneX的一些坑 ](https://mp.weixin.qq.com/s?__biz=MjM5OTM0MzIwMQ==&amp;mid=2652552818&amp;idx=1&amp;sn=69db895d4d4078bd83e7e1655fcdd5f1&amp;chksm=bcd2fb7c8ba5726a0d7481ca5960ec3c1600b214f15841542a41c58612ef4866a9551cd82640#rd)
 
[完美适配 iOS11 导航栏](http://www.cocoachina.com/ios/20170919/20597.html)

[腾讯WeTest 你可能需要为你的APP适配iOS11](http://wetest.qq.com/lab/view/326.html)

[iOS 11 适配看这篇还不够？](http://www.jishux.com/plus/view-606748-1.html)

iPhone X 适配
------------

[饿了么 UED iPhone X设计适配指南 & iOS 11新特性](https://zhuanlan.zhihu.com/p/29327102)

[iPhone X 适配](http://www.jianshu.com/p/9796cd3f180e)

[iPhone X 的 UI界面适配官方指南](https://juejin.im/entry/59b938f86fb9a00a5c3c32df)

[iOS11 &amp; iPhone X 适配指南](http://www.10tiao.com/html/216/201709/2652552758/2.html)

[iOS iPhone X 适配启动图片](http://www.cnblogs.com/someonelikeyou/p/7515025.html)

[三分钟弄懂iPhone X 设计尺寸和适配](http://www.zcool.com.cn/article/ZNTU1MTUy.html)

[iPhone X 适配指南 (官方版)](https://developer.apple.com/cn/ios/update-apps-for-iphone-x/)

[随手记在iPhone X上的适配实践总结 ](https://mp.weixin.qq.com/s/vzSUc2YPVIRD8CmkxaDfxg)

[美团iPhone X 刘海打理指北](https://tech.meituan.com/iPhoneX%E5%88%98%E6%B5%B7%E6%89%93%E7%90%86%E6%8C%87%E5%8C%97.html)


2017.9.21 增加iPhone X 上TabBar拉伸的,压缩的问题
------------------------------------
如果是那种自定义TabBar中间是按钮的这种操作，我试了一下，之前中间按钮的高度设置的是TabBar的高度（ CGFloat buttonH = self.frame.size.height;），现在直接赋值，也可以解决这种问题 。CGFloat buttonH = 49;

[TabBar被拉伸的解决方法](https://stackoverflow.com/questions/46214740/ios-11-iphone-x-simulator-uitabbar-icons-and-titles-being-rendered-on-top-coveri)

[ios 11 UITabBar UITabBarItem positioning issue](https://stackoverflow.com/questions/44822558/ios-11-uitabbar-uitabbaritem-positioning-issue)

[奇点在 iPhone X 的 break](https://imtx.me/archives/2374.html)

 2017.9.28 增加界面底部不带TabBar，iPhone X适配的问题
 -------------------------------------------
 
 今天有小伙伴询问了界面底部不带TabBar，iPhone X底部圆角导致，界面不美观，怎么解决。
 
 目前的解决办法：
 
 1.tableView在初始化的时候，Height增加一个宏，判断一下，如果是iPhone X 底部留，20px。
 
 2.保持view的backgroundColor跟tableView一致。
 
     #define IS_IPHONEX (([[UIScreen mainScreen] bounds].size.height-812)?NO:YES)
 
     #define Height (IS_IPHONEX ? ([[UIScreen mainScreen] bounds].size.height-20):([[UIScreen mainScreen] bounds].size.height))
 
         
    



iOS 11获取设备名称
-----------------

    if ([platform isEqualToString:@"iPhone10,1"]) return @"iPhone 8";
    if ([platform isEqualToString:@"iPhone10,4"]) return @"iPhone 8";
    if ([platform isEqualToString:@"iPhone10,2"]) return @"iPhone 8 Plus";
    if ([platform isEqualToString:@"iPhone10,5"]) return @"iPhone 8 Plus";
    if ([platform isEqualToString:@"iPhone10,3"]) return @"iPhone X";
    if ([platform isEqualToString:@"iPhone10,6"]) return @"iPhone X";

