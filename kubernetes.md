1、helm（k8s包管理器）
https://developer.aliyun.com/article/1207395
https://helm.sh/zh/docs/

2、kubernetes
k8s基本概念

k8s常用对象

kubernetes中的资源对象可以简单分类为以下几种，这些对象都可以在 YAML 文件中作为一种 API 类型来配置。
| 类别 | 名称 |
| ------------- | ------------- |
| 资源对象 | Pod、ReplicaSet、ReplicationController、Deployment、StatefulSet、DaemonSet、Job、CronJob、HorizontalPodAutoscaling、Node、Namespace、Service、Ingress、Label、CustomResourceDefinition |
| 存储对象 | Volume、PersistentVolume、Secret、ConfigMap |
| 策略对象 | SecurityContext、ResourceQuota、LimitRange |
| 身份对象 | ServiceAccount、Role、ClusterRole |

k8s集群管理
  1）k8s集群对接执行机：
    将执行机上的/root/.kube/config文件替换为k8s集群中的kubeconfig文件
  2）k8s集群日志落盘：
