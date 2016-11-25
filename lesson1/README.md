#### 从 Web Server 讲起
* 什么是 Web 服务器

* 传统的 Web 服务器

* Node的 Web 服务器
>Node 所提供的范式跟传统的 Web 服务器不同： 你写的程序就是 Web 服务器。 Node 只是给你提供了一个构建 Web 服务器的框架。

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