# 如何做一个持久化数据服务的 Operator 开发

## 整体代码结果

## 主要的逻辑

```golang
for _, subReconciler := range []subReconciler{
		&addBootstrap{r},
		&updateStatus{r},
		&syncConfig{r},
		&addSvc{r},
		&addCore{r},
		&addRepl{r},
		&updatePodConditions{r},
		&updateStatus{r},
		&syncPods{r},
		&syncSets{r},
	}
```
## 

addBootstrap

1. 获取 bootstrapAPIKeys
2. 生成 NodeCookieSecret: 来自于 Emqx 本身的 Config
3. 生成 Bootstrap API key Secret
4. 设置和 instance 的关联关系
5. 创建

updateStatus

1. 返回 replicatset
    1. 返回 oldsRsList 
2. 返回 statefuleset
3. 更新 instance 的 stauts 的 core 和 replicat 的状态
3. 商业的驱逐特性
4. status machine 的计算
5. 更新 stauts
QA：
1. Spec 中的 coreTemaplate 和 replicantTemplate 的区别是什么? 看起来了 core 和 replicat 是 Emqx 的概念
2. statusfule set 和 replicat set 的职责和角色

syncConfig
1. 构造 configMap 对象
2. 根据 instance 的 annotation 确认是不是第一次启动，是的话，配置为 replace 模式，则进行配置更新 ( 额，annotataion 中仍了一个完整的 config？
3. 更新完 config 后，基于最新的 config ，再生成一次 configmap 
QA：
1. configmap 的对象是为了谁？

addSvc
1. headlessService
2. dashboar service; service 的配置信息来自于 instance 的 spec: 
3. listen
QA:
headless service 的作用
默认值从哪里来？

addCore

1. 生成 statufulsettet
2. 
## 一些有趣的细节

## 如何应用代码并将启动 operator

