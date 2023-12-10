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

## 一些有趣的细节

## 如何应用代码并将启动 operator

