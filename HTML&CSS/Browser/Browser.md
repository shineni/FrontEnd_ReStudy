# Browser

![浏览器.PNG](.\imgs\浏览器.PNG)

![浏览器工作原理.PNG](.\imgs\浏览器工作原理.PNG)

对浏览器的实现者来说，他们做的事情，就是把一个 URL 变成一个屏幕上显示的网页。这个过程是这样的：
- 浏览器首先使用 HTTP 协议或者 HTTPS 协议，向服务端请求页面；
- 把请求回来的 HTML 代码经过解析，构建成 DOM 树；
- 计算 DOM 树上的 CSS 属性；
- 最后根据 CSS 属性对元素逐个进行渲染，得到内存中的位图；
- 一个可选的步骤是对位图进行合成，这会极大地增加后续绘制的速度；
- 合成之后，再绘制到界面上。

## 1. 网络通讯
### 1.1 HTTP协议
HTTP 标准由 IETF 组织制定，跟它相关的标准主要有两份：
- HTTP1.1 https://tools.ietf.org/html/rfc2616
- HTTP1.1 https://tools.ietf.org/html/rfc7234

![HTTP格式.PNG](.\imgs\HTTP格式.PNG)
- HTTP Method（方法）: 最常用的就是GET和POST方法 浏览器通过地址栏访问页面都是 GET 方法。表单提交产生 POST 方法
    - GET
    - POST
    - HEAD
    - PUT
    - DELETE
    - CONNECT
    - OPTIONS
    - TRACE

- HTTP Status code（状态码）和 Status text（状态文本）
    - 1xx：临时回应，表示客户端请继续。
    - 2xx：请求成功。
        - 200：请求成功。
    - 3xx: 表示请求的目标有变化，希望客户端进一步处理。
        - 301&302：永久性与临时性跳转。
        - 304：跟客户端缓存没有更新。
    - 4xx：客户端请求错误。
        - 403：无权限。
        - 404：表示请求的页面不存在。
        - 418：It’s a teapot. 这是一个彩蛋，来自 ietf 的一个愚人节玩笑。（超文本咖啡壶控制协议）
    - 5xx：服务端请求错误。
        - 500：服务端错误。
        - 503：服务端暂时性错误，可以一会再试。

3. HTTP Head(HTTP头)

![RequestandResonseHeader.PNG](.\imgs\RequestandResonseHeader.PNG)

### 1.2 HTTPS
HTTPS 有两个作用，
- 一是确定请求的目标服务端身份，
- 二是保证传输的数据不会被网络中间节点窃听或者篡改。

## 1. HTTP协议
