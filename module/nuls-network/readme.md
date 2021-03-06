# 网络模块

## 为什么要有《网络模块》

网络模块保障了去中心化节点间的通讯，为NULS基础模块之一，提供最底层的网络通信、节点发现等服务。区块链的网络基础就是Peer to  Peer,即P2P。P2P网络中的所有参与者，可以是提供服务（server），也可以是资源使用者（client）。P2P网络的特点：去中心化、可扩展性、健壮性、高性价比、隐私保护、负载均衡。

## 《网络模块》要做什么

网络模块是整个系统的基础模块，用来管理节点、节点间的连接及连接的状态、数据的发送与接收。网络模块不涉及复杂的业务逻辑。

* 接收到的网络消息，根据内核模块中的指令服务映射关系，推送消息相应的处理模块中。

* 开放接口供其他模块封装好的消息调用推送到指定的peer节点以及广播到指定的网络组中。

## 《网络模块》在系统中的定位

* 网络模块是底层应用模块，任何需要网络通讯的模块都要通过网络模块来进行消息的收发。
* 网络模块依赖核心模块进行服务接口的治理。
* 网络模块按网络id（魔法参数） 来进行不同网络的构建。
* 网络模块在卫星链中的节点在进行跨链网络组建时，需要链管理模块提供跨链配置信息。
* 网络模块在子链中的节点在进行跨链网络组建时，需要跨链模块提供跨链配置信息。



## 模块配置

```
#本链服务端口
port=18001
#跨链服务端口
crossPort=18002
#魔法参数
packetMagic=55886633
#种子连接节点
selfSeedIps=192.168.1.12:18001
#最大入网连接数
maxInCount=100
#最大出网连接数
maxOutCount=20
```

