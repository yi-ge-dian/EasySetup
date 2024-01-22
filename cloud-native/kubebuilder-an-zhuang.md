# Kubebuilder 安装

官网：[https://book.kubebuilder.io/quick-start](https://book.kubebuilder.io/quick-start)

安装kubebuilder

```bash
# download kubebuilder and install locally.
curl -L -o kubebuilder "https://go.kubebuilder.io/dl/latest/$(go env GOOS)/$(go env GOARCH)" 
chmod +x kubebuilder && mv kubebuilder /usr/local/bin/
```

依赖安装

```bash
go install sigs.k8s.io/controller-tools/cmd/controller-gen@latest
go install sigs.k8s.io/kustomize/kustomize/v4@latest
go install sigs.k8s.io/controller-runtime/tools/setup-envtest@latest
```

* controller-gen 是一个用于生成Kubernetes Operator控制器代码的工具。用于自动生成与自定义资源定义(CRD)相关的控制器代 码。&#x20;
* Kustomize是一个用于Kubernetes部署和配置管理的工具,它的作用是简化和管理基于YAML的应用配置。&#x20;
* setup-envtest是一个便于进行集成测试的工具。





