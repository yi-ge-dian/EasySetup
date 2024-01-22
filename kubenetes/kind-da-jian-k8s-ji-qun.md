# Kind 搭建 k8s 集群

官网文档：[https://kind.sigs.k8s.io/](https://kind.sigs.k8s.io/)

创建一个配置文件

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
networking:
  # WARNING: It is _strongly_ recommended that you keep this the default
  # (127.0.0.1) for security reasons. However it is possible to change this.
  apiServerAddress: "0.0.0.0"
  # By default the API server listens on a random open port.
  # You may choose a specific port but probably don't need to in most cases.
  # Using a random port makes it easier to spin up multiple clusters.
  apiServerPort: 6443
  kubeProxyMode: "ipvs" # specify the model of kube-proxy
```

创建这个集群

```bash
kind create cluster --config .kind-config.yaml --name k8s
```

获得环境中的集群

```bash
kind get cluster
```

删除集群

```bash
kind delete cluster --name k8s
```

查看上下文

```
kubectl config get-contexts
```

删除某个上下文bash

```bash
kubectl config unset contexts.config名字
```

切换上下文

```
kubectl config get-contexts
```
