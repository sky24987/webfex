## HTTP & RESTful & Nginx

### http状态码有那些？分别代表是什么意思？

100-199 用于指定客户端应相应的某些动作。 
200-299 用于表示请求成功。 
300-399 用于已经移动的文件并且常被包含在定位头信息中指定新的地址信息。 
400-499 用于指出客户端的错误。400    1、语义有误, 当前请求无法被服务器理解。401   当前请求需要用户验证 403  服务器已经理解请求, 但是拒绝执行它。
500-599 用于支持服务器错误。 503 – 服务不可用

详情：http://segmentfault.com/blog/trigkit4/1190000000691919

### 一个页面从输入 URL 到页面加载显示完成, 这个过程中都发生了什么？

分为4个步骤：
（1）, 当发送一个URL请求时, 不管这个URL是Web页面的URL还是Web页面上每个资源的URL, 浏览器都会开启一个线程来处理这个请求, 同时在远程DNS服务器上启动一个DNS查询。这能使浏览器获得请求对应的IP地址。
（2）,  浏览器与远程Web服务器通过TCP三次握手协商来建立一个TCP/IP连接。该握手包括一个同步报文, 一个同步-应答报文和一个应答报文, 这三个报文在 浏览器和服务器之间传递。该握手首先由客户端尝试建立起通信, 而后服务器应答并接受客户端的请求, 最后由客户端发出该请求已经被接受的报文。
（3）, 一旦TCP/IP连接建立, 浏览器会通过该连接向远程服务器发送HTTP的GET请求。远程服务器找到资源并使用HTTP响应返回该资源, 值为200的HTTP响应状态表示一个正确的响应。
（4）, 此时, Web服务器提供资源服务, 客户端开始下载资源。

详情：[从输入 URL 到浏览器接收的过程中发生了什么事情？][7]

### GET和POST的区别, 何时使用POST？

GET：一般用于信息获取, 使用URL传递参数, 对所发送信息的数量也有限制, 一般在2000个字符
POST：一般用于修改服务器上的资源, 对所发送的信息没有限制。

GET方式需要使用Request.QueryString来取得变量的值, 而POST方式通过Request.Form来获取变量的值,
也就是说Get是通过地址栏来传值, 而Post是通过提交表单来传值。
    
然而, 在以下情况中, 请使用 POST 请求：

- 无法使用缓存文件（更新服务器上的文件或数据库）
- 向服务器发送大量数据（POST 没有数据量限制）
- 发送包含未知字符的用户输入时, POST 比 GET 更稳定也更可靠


