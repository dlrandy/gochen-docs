### 性能为什么重要
网站的性能影响着UX，从而影响用户的数量；同时也影响着网站的排名。
### 浏览器如何同server通信的？

request:
verb(get) resource protocol
host
accept

response:
protocol statuscode
content-length
content-type



### 提升性能的主要的目的之一是减小**延迟**
延迟是response完全到达所需要的时间。

### Http1.1的线头阻塞问题
是指通常浏览器一次并发请求6个，一旦超出6个，后续的就要等待
前6个里面的某些个完成，才会发起请求。这样会增加页面加载的时间

### http2有回退到http1.1的能力
意思就是http2的server对于只支持http1的浏览器，可以使用
http1进行通信。

### 想测试性能，就要有延迟，否则无法测量性能的

### 提升性能的基本方法
1. 压缩体积
2. compression 适合文本资源的压缩
3. 图片的压缩
  原理是使用重新编码的技术，去掉不必要的数据，但是不会
  明显图片的视觉品质.tinypng
4. 使用测评工具
  - [page speed insight](https://developers.google.com/speed/pagespeed/insights/)
  - google analytics
  - 浏览器的测评工具
    1. timing信息
      TTFB是请求发送的时刻到response的第一个byte到达的时刻
      之间的时间。
  - 渲染性能审计工具
    1. 浏览器如何渲染页面的？
      DOM-》cssOM-》layout-》paint
    2. 使用performance tool
    3. 识别问题event
      最小化浏览器加载和渲染的时间。
      主要是单位帧的时间里执行了太耗CPU的操作就会引起掉帧
    4. 检测函数的执行时间console.time/timeEnd
5. inline asset，对于cache不友好，h2的可以考虑server push

  



