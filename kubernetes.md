# 1、helm
helm是一个k8s的包管理器，可以通过helm命令部署多个应用，而不是依次执行`kubectl apply`命令部署，简化了应用程序的部署、版本控制、可配置性。helm同时引入了内置对象、内置函数、变量、模板、流控制结构语句等内容，使得我们可以仅修改value.yaml来对整个软件配置进行调整。\
[helm入门](https://developer.aliyun.com/article/1207395) \
[helm | docs](https://helm.sh/zh/docs/)

# 2、kubernetes
## k8s基本概念

## k8s常用对象
kubernetes中的资源对象可以简单分类为以下几种，这些对象都可以在 YAML 文件中作为一种 API 类型来配置。
| 类别 | 名称 |
| ------------- | ------------- |
| 资源对象 | Pod、ReplicaSet、ReplicationController、Deployment、StatefulSet、DaemonSet、Job、CronJob、HorizontalPodAutoscaling、Node、Namespace、Service、Ingress、Label、CustomResourceDefinition |
| 存储对象 | Volume、PersistentVolume、Secret、ConfigMap |
| 策略对象 | SecurityContext、ResourceQuota、LimitRange |
| 身份对象 | ServiceAccount、Role、ClusterRole |

### Pod

### 控制器

### Service

### 数据存储

## k8s集群部署
### 1) k8s集群kubeadmin部署
    清理k8s集群信息: \
      清理所有helm部署资源\
      强制删除docker容器\
      清理不再使用的docker卷\
      查询Linux系统`/proc/mounts`文件下当前挂载点信息，并umount`/var/lib/kubelet`和/var/lib/rancher`相关路径，删除k8s和rancher的核心挂载目录
    kubeadmin环境托管rancher：\
      docker run -d --restart=unless-stopped -p 8082:80 -p 8146:443 --privileged rancher/rancher:v2.5.3
### 2) k8s集群rancher部署

### 3）k8s集群对接执行机
    将执行机上的/root/.kube/config文件替换为k8s集群中的kubeconfig文件
### 4）k8s集群日志落盘

## 参考资料
[Kubernetes 中的资源对象 · Kubernetes 中文指南——云原生应用架构实战手册 (jimmysong.io)](https://jimmysong.io/kubernetes-handbook/concepts/objects.html) \
[第二章：入门概念 — 图解K8S documentation (iswbm.com)](https://k8s.iswbm.com/chapters/p02.html#) \
[Kubernetes 文档 | Kubernetes](https://kubernetes.io/zh-cn/docs/home/)
