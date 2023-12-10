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

## 一些有趣的细节

## 如何应用代码并将启动 operator
	
