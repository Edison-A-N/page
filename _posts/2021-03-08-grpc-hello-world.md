---
layout: post
title: grpc hello world
author: Edison
---

### 获取源码
```
https://github.com/grpc/grpc-go.git
```
源码在 ```grpc-go/examples/helloworld```文件夹

### 源码解析
#### proto文件
- 声明使用proto3。这是最新版的格式，具体可以了解[proto3](https://developers.google.com/protocol-buffers/docs/proto3)与[proto2](https://developers.google.com/protocol-buffers/docs/proto)的区别。一般直接使用proto3即可。
```
syntax = "proto3";
```
- 声明包路径，指向了使用proto文件的go包的路径
```
option go_package = "google.golang.org/grpc/examples/helloworld/helloworld";
```
```
option java_multiple_files = true;
option java_package = "io.grpc.examples.helloworld";
option java_outer_classname = "HelloWorldProto";
```
- 声明包名。包名与go的包名一致
```
package helloworld;
```
- 声明服务调用接口。
```
// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply) {}
}
```
- 消息体(message)定义。
```
// The request message containing the user's name.
message HelloRequest {
  string name = 1;
}

// The response message containing the greetings
message HelloReply {
  string message = 1;
}

```

### 参考
[基于go的教程](https://developers.google.com/protocol-buffers/docs/gotutorial)