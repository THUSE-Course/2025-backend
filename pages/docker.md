# Docker 简介

## Docker 的作用

<img src="/assets/you-match.png" style="position: absolute; top: 10%; right: 5%; height: 80%; width: auto;">

---

# Docker 的作用

### Docker

Docker 将应用及其所需要的环境打包并交付给其他人使用，使得应用能够在一致的环境下一键运行，而不需要手动配置环境

### 特点

- 更高效的利用系统资源
- 更快速的启动时间
- 更方便持续交付和部署

---

# Docker 中的重要概念：镜像、容器与 Registry

### 镜像（Image）

Docker 镜像是一个特殊的文件系统

- 提供容器运行时所需的程序、库、资源、配置等文件
- 包含一些为运行时准备的一些配置参数
- 不包含任何动态数据，其内容在构建之后也不会被改变

---

# Docker 中的重要概念：镜像、容器与 Registry

### 镜像（Image）

Docker 镜像的构建：Dockerfile

![dockerfile-example](/assets/dockerfile-example.png)

- 语法规范详见：[https://yeasy.gitbook.io/docker_practice/image/dockerfile](https://yeasy.gitbook.io/docker_practice/image/dockerfile)
- 之后使用 docker build 命令构建镜像

---

# Docker 中的重要概念：镜像、容器与 Registry

### 容器（Container）

- 镜像的**实例**：镜像是静态的定义，容器是镜像运行时的实体
- 具有**易失性**：任何保存于容器存储层的信息都会随容器删除而丢失（大作业需要将用户数据保存在持久化存储中）

容器的启动：

- （本地）docker run -d -p 10001:8000 --name &lt;Container Name&gt; &lt;Image&gt;
- （其他部署工具）查阅对应文档...

---

# Docker 中的重要概念：镜像、容器与 Registry

### Registry

概念辨析：仓库（Repository）、注册服务器（Registry）
- 镜像构建完成后，可以很容易的在当前宿主机上运行，但是，如果需要在其它服务器上使用这个镜像，我们就需要一个集中的存储、分发镜像的服务，Docker Registry 就是这样的服务。
- 一个 Docker Registry 中可以包含多个仓库（Repository）；每个仓库可以包含多个标签（Tag）；每个标签对应一个镜像。

---

# Docker 中的重要概念：镜像、容器与 Registry

### Registry

![dockerhub](/assets/dockerhub.png)
概念辨析：Docker Hub; 图中的 python;  python:3.9.16

---

# Dockerfile 编写入门

###

参考 [课程文档 Docker 部分](https://thuse-course.github.io/course-index/deploy/docker/), [2023 酒井科协暑培 Docker 课程](https://summer23.net9.org/sast2023-docker/), [2024 科协算协联合暑培 Docker 课程](https://summer24.net9.org/backend/docker/prerequisites/)

---