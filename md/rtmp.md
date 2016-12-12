###rtmp

#####handshake

C0 C1 C2 S0 S1 S2

#####rtmp_connect

客户端发送带宽消息
服务端返回带宽消息
服务端返回连接成功消息

#####rtmp create  stream
客户端发送创建流请求
服务端返回创建成功消息

#####rtmp play
客户端发送播放文件消息 rtmp_play

服务器返回TYPE_CHUNK_SIZE 消息

服务器返回开始播放消息 netstream.plya.START

服务器返回视频信息（TYPE_STREAM_METEDATA）包括大小，宽高，速率等等信息－－文件长度可以在这里推算出来 
