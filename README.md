# broadcasting-station
Linux 音频流媒体广播服务器（含客户端代码）

项目描述
在Linux服务器端实现一个基于IPv4的音频广播程序，不断发送音频节目单以及各个频道音频数据。客户端先接收节目单，获取到当前各个频道的描述，并选择一个频道进行收听。

程序的编译和运行方法：
分别在两台同一网络下的主机下make src中的server和client。（修改server端sever_conf.h文件中的默认音频文件路径
DEFAULT_MEDIADIR以及默认网卡DEFAULT_IF）


程序的执行过程：
server端通过组播的方式发送节目单（频道号和各频道音频内容描述），以及各频道音频数据。每秒发送一次。
client端在任意时刻开始接收，先接收节目单数据包，丢弃其他包。打印节目单，由用户选择播放的频道号，接收该频道
的音频数据包，开始播放音频。

