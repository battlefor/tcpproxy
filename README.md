# tcpproxy
一个支持ssl加密解密，基于ASIO I/O 的proactor架构模式，高并发，高性能的tcp代理服务器tcpproxy。除了具备基本的tcp代理转发功能，它还可以对tcp协议数据加密转换成ssl协议后转发出去，也可以对ssl协议数据解密后再转发，特别适用于需要安全传输保证数据不会被窃密的的应用场景

使用方法
------

```C++
./tcpproxy_server.exe [-m proxy mode] [-p port] [-r remote address:port]

温馨提示:以上每个参数都是必须的，缺一不可.

* -m，工作模式
  * 0，表示tcp2tcp模式，对tcp协议数据包直接转发到目标地址
  * 1，表示tcp2ssl模式，对tcp协议数据包经过ssl加密后转发到目标ssl服务器地址
  * 2，表示ssl2tcp模式，对ssl协议数据包经过解密后转发到目标地址
* -p，监听端口号，用来接收对方发来的数据包
* -r，目标地址，地址格式为address:port，必须带上端口，其中，address可以是ip也可以是域名，port是端口号


测试示例命令

./tcpproxy_server.exe -m 1 -p 3200 -r 192.34.23.44:3300
./tcpproxy_server.exe -m 1 -p 3200 -r abcd.com:3300
