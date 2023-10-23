# readme 

v1 使用 broker 来描述，v2 则用 eqmx 这个对象来描述

emqx 对象覆盖了 image 信息，授权信息，配置信息，以及 四个模板，分别是 CoreTemplate, EMQXReplicatntTempalte,  

以及两个 service ，分别是 DashboardService  和  ListenerService

CoreTemplate 描述了 emqx 服务部署的基本信息

names.go 覆盖率 operator 会产生的 k8s objectb

1. coreNameSpace
2.  replicant
3. headless -> k8s 的 headless servier
4. dashboard -》emqx 本身的 dashbaord
5. listerner -> 给 linstener 用的 service，作为一个消息队列有一个 listener 蛮正常的

