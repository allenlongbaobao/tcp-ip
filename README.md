# TCP/IP 知识点整理

> 这个项目是为了在阅读 《TCP/IP 协议》 一书时整理笔记，留作记录

## 目录

* [TCP 简介](#tcp-简介)
* [TCP 的连接](#tcp-的连接)
* [TCP 超时、重传处理](#tcp-超时、重传处理)
* [TCP 数据流和window管理](#tcp-数据流和window管理)
* [TCP 冲突控制](#tcp-冲突控制)




## TCP 简介
  TCP (Transimission Control Protocol), 属于传输层协议, 它是一种 `connection-oriented, reliable, byte stream service` 的协议，和 UDP 协议经常一起出现，两者之间简单的区别在于 TCP 建立的是`可靠`连接,而 UDP 则是允许丢失数据的情况存在。为了确保传输的`可靠`，TCP 的设计比 UDP 要复杂得多。

  > 如何确保数据可靠传输？
  > * 建立连接、断开连接中使用三次握手和四次挥手用来确保连接的正确建立和断开
  > * 点对点传输，每次传输的数据，它的报文头都会带上 checksum
  > * 任何一端接收到数据，会返回一个确认——ACK，发送端设定一个定时器，如果超过这个时间，ACK 还没有传回，就重传这段数据。另外，TCP 还可以在一系列数据接收之后，一起发送一个 ACK，这样避免了大量的 ACK 传输，降低因丢失 ACK 而不得不重传的概率。
  > * 全双工模式，任何一端发送的数据，都要包含一个 sequence number

#### TCP 和 UDP 的异同

##### 相同点

##### 不同点

  * Tcp 是 byte stream 服务，在传递到 IP 层进行传输前，会将应用数据打包(packetization),协议会把数据打包成它认为最合适的大小，然后传递给 IP 层，这样的包成为 Chunk,而且协议还可以把几个包打到一起（repacketization） 




## TCP 的连接

## TCP 超时、重传处理

## TCP 数据流和window管理

## TCP 冲突控制
