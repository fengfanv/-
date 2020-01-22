# 使用websocket写一个客服聊天系统

一步一步从认识websocket Api 到实现一个客服聊天系统。

#### 作者：Fengfanv

------

### 第一步 使用nodejs-websocket
#### 1、服务端安装npm插件**nodejs-websocket**
```
mkdir Websocket                 //创建项目文件夹
cd Websocket                    
npm install nodejs-websocket    //安装nodejs-websocket
```
#### 2、了解服务端**nodejs-websocket**

```javascript
//创建一个websocket服务
var server = ws.createServer(function(connection){
  //发送字符串信息
  connection.sendText("字符串");
  //发送二进制数据
  connection.sendBinary(Binary);
  //发送信息
  connection.send();
  //监听收听收到的信息
  connection.on("text",function(str){
    console.log("收到消息："+str);
  });
  //监听连接关闭
  connection.on("close",function(code,reason){
    console.log("连接关闭");
  });
  //监听连接错误
  connection.on("error",function(error){
    console.log(error);
  });
});
//设置服务端口号和服务地址
server.listen(host,[host]);
//关闭websocket服务方法
server.close();
//包含所有连接的客户端的数组,可利用它对广播信息
server.connections;
```
#### 3、了解客户端**websocket**
```javascript
var ws=new WebSocket(地址);
//连接服务
ws.onopen=function(){
  console.log("连接成功！");
}
//断开连接
ws.onclose=function(){
  console.log("断开连接！");
}
//监听服务端发送的信息
ws.onmessage=function(e){
  console.log("新消息："+e);
}
//发送消息
ws.send("要发送的消息");
```
