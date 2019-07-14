# 工作流实验室保研夏令营引导

## 工具介绍

本次的实验在所依赖的环境及工具包括：

- Ubuntu 16.04

    实验室已为每个用户提供一个远程环境，包含一个64位的Ubuntu 16.04环境，用户的所有程序都需要在该环境中运行

- Kubernetes环境

    实验室所给出的远程环境是可以连接到提供的kubernetes集群的，详细介绍后面给出

- Python/Golang编程工具

    请从上述中选择一个你熟悉的编程语言，完成本地计算机的环境及工具配置，对于Golang语言的使用者，建议本地进行编译后传输到实验室给出的远程环境上使用；对于python语言使用者，建议使用virtualenv工具进行环境的配置，并打包传输至远程环境上使用

- Kubernetes sdk

    要求使用kubernetes提供的sdk或使用kubectl完成编程实验，如何获取权限及操作样例在后面会给出

### 任务提交说明

您所需要完成的每一个任务都会给出它的id号，请在完成实验后，在github上创建属于你自己的账户并上传代码，完成后请在该项目的issue下，发布一个`任务提交`类型的issue，并根据指引，完成您任务的提交

## 实验指南

### 起步

如果您还未曾了解过docker相关的知识，我们希望您可以去查看一下阮一峰关于docker的起步指南，最好的学习来源于实践，我们希望您可以在本地搭建属于自己的docker平台，并在docker hub上传第一个属于你们自己的docker镜像

如果您对kubernetes的相关概念还一无所知，我们推荐你去它的官方网站跟着在线教程走一遍，并在文档中了解相关的概念，在阅读的过程中，我们希望您可以多关注这几个关键词：`pods`、`service`、`deployment`，对这几个概念有所了解将会帮助您更好地去完成接下来的实验

您无需在我们提供的远程环境上部署您自己的kubernetes环境，您所使用的远程环境本身就运行在一个kubernetes集群中，我们对它进行了适当的权限限制，使得您可以在完成实验的同时又不会破坏本地的环境；除此之外，您对kubernetes集群访问的token也被挂载到了您的远程环境中，您可以通过编程等方式来对kubernetes的接口进行调用，并执行相应的操作

### 利用kubernetes官方sdk对pod进行操作

这一部分是为了确保您已经掌握了kubernetes官方提供的sdk的基本操作，在这一部分中，我们将会给出一个样例，告诉你们如何去调用接口以完成操作，后续会提出扩展要求，请根据题目要求完成任务并提交

- [python sample](https://github.com/sysu-workflow-summer-campus/python-demo)

使用python语言调用kubernetes接口并完成获取指定namespace下所有pods及相关信息的操作

- [golang sample](https://github.com/sysu-workflow-summer-campus/golang-demo)

使用python语言调用kubernetes接口并完成创建一个pods的操作

**任务 #1: 请根据给出的样例，部署[nginx镜像](https://hub.docker.com/_/nginx)至一个pod，不要求端口对外部映射**

## 注意事项

- 远程环境的初始密码都是`root`，请在登录后及时修改密码

- 远程环境是临时环境，对cpu及内存均有限制，超出限制的环境将被自动调度删除，删除后会进行重建，但重建后的环境将是一个空的环境，之前的所有配置都将被清空

- 远程环境的`/data`目录在环境被删除重建后仍然保留
