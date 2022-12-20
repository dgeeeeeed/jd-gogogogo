# 京东App秒杀抢购流程接口分析

京东秒杀，网上的很多工具已经无效了。只能分析app端的底层协议和流程。抓包方式推荐：charles+夜神模拟器

经分析：

秒杀一共分为两个步骤：
第一步是获取跳转链接，第二步是访问跳转链接。

第一步：获取跳转链接

跳转链接是指形如：https://un.m.jd.com/cgi-bin/app/appjmp 的链接，获取该链接，还需要一个前置步骤，即获取token和拼接url。先说获取token，获取token是通过genToken接口获取的，然后将获取到的tokenKey和url拼接起来，得到跳转链接。

第二步：访问跳转链接

拿到跳转链接后，直接将该跳转链接仍给浏览器即可，浏览器会经过两次302跳转得到sekill.action链接，从而渲染出提交订单页面，此时我们需要模拟点击“提交订单”按钮，实现抢购。（可以使用Selenium、Pyppeteer或Playwright等类库 来模拟浏览器）

软件试用

[抢购软件exe试用下载](https://raw.githubusercontent.com/geeeeeeeek/jd-seckill-2022/main/jd%E6%8A%A2%E8%B4%AD%E8%AF%95%E7%94%A8%E7%89%88.exe)


注意：京东茅台抢购，是有门槛的，帐号信用分需104分以上。 可使用京东app扫码查看信用分。
![](https://github.com/geeeeeeeek/jd-seckill-2022/blob/main/fenshu.jpg?raw=true)
  

技术咨询QQ：285126081

更多精彩福利
![image](https://user-images.githubusercontent.com/35225502/208577855-62ae1233-b194-4dc8-8551-3d494bce8c34.png)


