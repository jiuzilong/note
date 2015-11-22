# HTTP、Socket与websocket

## 网络协议分层

- 应用层 `HTTP`、`FTP`、`SMTP`、`TELNET`（主要解决如何包装数据）
- 传输层 `TCP`（主要解决数据如何在网络中传输）
- 网络层 `IP`
- 数据链路层
- 物理层

## HTTP
- 应用用在 web 上，包装 `HTTP` 文本信息
- 服务端无法主动向客户端发送数据

## socket

- 基于 `TCP/IP` 的网络协议的一个接口，多用于桌面程序
- **本身并不是协议，而是一个调用接口(API)**

## websocket

- 基于 `HTTP` 协议，只借助 `HTTP` 完成一次握手即可
- 可以双向通信，弥补 `HTTP` 的不足
