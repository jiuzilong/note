# HTTP、Socket与websocket

## 网络协议分层

- 应用层 `HTTP`、`FTP`、`SMTP`、`TELNET`（主要解决如何包装数据）
- 传输层 `TCP`（主要解决数据如何在网络中传输）
- 网络层 `IP`
- 数据链路层
- 物理层

## HTTP
- 应用用在 web 上，包装 `HTTP` 文本信息
- 服务端无法主动向客户端发送数据，只能使用轮询的方式去实现双向通信（效率低、占资源）
    + 长轮询（long poll）：客户端发起连接，如果没消息，就一直不返回Response给客户端。直到有消息才返回，返回完之后，客户端再次建立连接
    + Ajax 轮询：隔几秒发送一次请求

## socket

- 基于 `TCP/IP` 的网络协议的一个接口，多用于桌面程序
- **本身并不是协议，而是一个调用接口(API)**

## websocket

- 基于 `HTTP` 协议，只借助 `HTTP` 完成一次握手即可
- 可以双向通信，弥补 `HTTP` 的不足

请求
```
GET /chat HTTP/1.1
Host: server.example.com
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Key: x3JJHMbDL1EzLkh9GBhXDw==
Sec-WebSocket-Protocol: chat, superchat
Sec-WebSocket-Version: 13
Origin: http://example.com
```

响应
```
HTTP/1.1 101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept: HSmrc0sMlYUkAGmm5OPpG2HaGWk=
Sec-WebSocket-Protocol: chat
```
