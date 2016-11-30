#### 从 Web Server 讲起
* 什么是 Web 服务器
> A web server is a computer system that processes requests via HTTP, the basic network protocol used to distribute information on the World Wide Web. The term can refer to the entire system, or specifically to the software that accepts and supervises the HTTP requests
> The primary function of a web server is to store, process and deliver web pages to clients. The communication between client and server takes place using the Hypertext Transfer Protocol (HTTP). Pages delivered are most frequently HTML documents, which may include images, style sheets and scripts in addition to text content.
> —— [Wikipedia](https://en.wikipedia.org/wiki/Web_server)
建议读一下这篇文档，虽然中文维基中木有相应条目，但是作为一个Web开发工程师，英文永远是一个标配。

* 传统的 Web 服务器

* Node的 Web 服务器
> Node 所提供的范式跟传统的 Web 服务器不同： 你写的程序就是 Web 服务器。 Node 只是给你提供了一个构建 Web 服务器的框架。
> 在用 Express 构建 Web 服务器时， 大部分工作都是从请求对象开始， 到响应对象终止。 这两个对象起源于 Node， Express 对其进行了扩展。 
> 在浏览器中键入一个 URL（ 或点击一个链接）， 服务器会接收到一个 HTTP GET 请求， 其中的重要信息是 URL 路径和查询字符串。 至于如何响应， 则需要应用程序结合方法、 路径和查询字符串来决定。 对于一个网站来说， 大部分页面都响应 GET 请求。 POST 请求通常用来提交信息到服务器后台（ 例如表单处理）。 服务器将请求中包含的所有信息（ 例如表单） 处理完成之后， 用以响应的 HTML 通常与相应的 GET 请求是一样的。 与服务器通信时， 浏览器只使用 GET 和POST 方法（ 如果没有使用 AJAX）。 ———— 《Node与Express开发》

* 用 Node 快速搭建一个 Wev Server
新建一个 server.js 文件
```
const http = require("http");
  
  http
    .createServer((req, res)=>{
        res.writeHead(200, {"content-type": "text/plain"})
        res.end("Hello World:)")
    })
    .listen(3000)

```
git bash 下 cd 至当 server.js 的目录   
执行 server.js => node server.js  
在浏览器中 输入 http://localhost:3000/  
Hello World:) 是不是已经跃然纸上。 Congradulation，你的第一个 Web Server 已经搭建成功了。