## 为我们的项目创建chart目录
helm create AutoDevOpsPipeLinesCharts

## 安装
## 渲染模板(调试)
```shell
helm install --debug --dry-run /root/AutoDevOpsPipeLinesCharts \
--set environment.upper=Staging \
--set environment.lower=staging \
--set image.registryhost=registry.geekbuying.com:8100 \
--set image.username=devopspipelines \
--set namespace=microservice-autodevopspipeline-v0  \
--set image.version=0.0.1 \
--set replicas=1
```

## 发布版本
```shell
helm install /root/AutoDevOpsPipeLinesCharts \
--set environment.upper=Staging \
--set environment.lower=staging \
--set image.registryhost=registry.geekbuying.com:8100 \
--set image.username=devopspipelines \
--set namespace=microservice-autodevopspipeline-v0  \
--set image.version=0.0.1 \
--set replicas=1
```

## 检视发布

helm get manifest [release name]

## 删除发布

helm delete [release name]

## 其他
helm ls
helm ls --deleted -d
helm del --purge $releaseName