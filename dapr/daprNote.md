# dapr

## 1.第01期-Dapr简介与入门

​	Dapr 是一个可移植的、事件驱动的运行时，它使任何开发人员能够轻松构建出弹性的、无状态和有状态的应用程序，并可运行在云平台或边缘计算中，它同时也支持多种编程语言和开发框架，构建块与组件的区别，基于 Sidecar 架构，组件与实现，中间件管道，可观测性，传输安全性。

## 2.第02期-安装与快速入门

[dapr 安装](https://docs.dapr.io/getting-started/install-dapr-cli/) 

[离线安装包](https://v1-7.docs.dapr.io/operations/hosting/self-hosted/self-hosted-airgap)



安装 Dapr 环境，初始化 Dapr 运行时，运行 Dapr Sidecar 实例，离线安装，卸载删除 Dapr 运行时，宿主方式与自宿主，理解 Dapr 架构和 Docker 容器，通过一个简单的示例调用 Dapr 提供的分布式缓存存取接口。



初始化dapr 自宿主 非docker 模式初始化

~~~ powershell
dapr init --slim --from-dir C:\daprbundle
~~~















