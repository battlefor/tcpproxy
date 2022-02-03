# tcpproxy
一个支持ssl加密解密，基于ASIO I/O 的proactor架构模式，高并发，高性能的tcp代理服务器tcpproxy。除了具备基本的tcp代理转发功能，它还可以对tcp协议数据加密转换成ssl协议后转发出去，也可以对ssl协议数据解密后再转发，特别适用于需要安全传输数据保证不会被窃密的的应用场景
